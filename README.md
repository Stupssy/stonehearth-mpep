# Stonehearth Multiplayer Enhancements

This mod focuses on enhancing Stonehearth's multiplayer capabilities with a primary focus on headless server functionality, game master features, and multiplayer performance optimization.

## Main Features

- **Headless Server Support**: Run a dedicated server without the graphical interface
- **Enhanced Player Roles**: First player becomes host or specify custom host in save files
- **Pre-Camp Joining**: Remote players can join before host player places a camp
- **Multiplayer Settings**: Auto-configuration of multiplayer settings for headless servers
- **Building System Enhancements**: Improved building functionality for remote clients
- **Performance Optimizations**: Reduced lag and improved responsiveness in multiplayer sessions
- **Entity Management**: Smarter entity processing to improve overall game performance
- **Network Traffic Reduction**: Optimized data synchronization between server and clients

## Installation

1. Subscribe to the mod on Steam Workshop (File ID: 1617901275)
   OR download the release and extract to your Stonehearth mods folder
2. For headless server setup, follow the configuration instructions below

## Headless Server Setup

### Using a Save Game

1. Save a game in single player mode
2. Modify the `server_metadata.json` file in the save folder:
   ```json
   {
       "player_id": "develop_1",
       "client_id": "GUID",
       "provider": "develop"
   }
   ```
   Your player_id will be either `develop_1` or `steam_1` depending on your game version

3. Launch the server using the `server.bat` file with the correct save ID

### Using Auto-Generation

1. Edit the `server.bat` file to configure:
   - Server settings (port, IP)
   - World generation parameters (seed, size, biome)
   - Game mode settings

2. Uncomment the desired world generation parameters in `server.bat`

3. Run the batch file to start the headless server

## Commands

- `radiant:client:save_game` - Triggers a save on the server if the client is connected as a host
- `radiant:client:restart` - Restarts the game on the server side
- `radiant:client:load_game_async` - Loads a game on the server without restarting (will disconnect clients)

## Known Issues

- Headless game saving is only possible with pre-loaded save games
- When setting custom IP addresses, avoid using characters that aren't numbers and periods
- Setting `multiplayer.remote_server.ip` with invalid characters can lock up the game

## Development Status

### Completed Features
- ✅ Headless server with auto-generation
- ✅ First player auto-assigned as host
- ✅ Multiplayer settings auto-configuration
- ✅ Pre-camp client joining
- ✅ Client-side multiplayer settings synchronization

### Planned Features
- ⬜ Auto-save functionality
- ⬜ Complete headless game saving support
- ⬜ Game Master mode for story creation
- ⬜ IP address specification in client
- ⬜ Headless server launcher with UI
- ⬜ Dynamic host transfer
- ⬜ Client launcher application
- ⬜ Advanced pathfinding optimization
- ⬜ Entity priority system based on player proximity
- ⬜ Synchronization controls for reduced network load
- ⬜ Resource balancing across settlements
- ⬜ Performance monitoring tools

## Technical Notes

The mod works by overriding key parts of Stonehearth's multiplayer functionality:
- Monkey patches the building client service
- Overrides the host player ID system
- Enhances server metadata handling

### Command Line Arguments

Working arguments:
- `multiplayer.server.port`
- `multiplayer.headless.enabled`
- `multiplayer.headless.saveid`
- `multiplayer.remote_server.enabled`
- `multiplayer.remote_server.port`

See `server.bat` for examples of usage and commented arguments that are not fully implemented.

## Credits

Created by Bolune (Steven Sinakhot)

## License

MIT License - See LICENSE file for details