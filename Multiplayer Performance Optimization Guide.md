# Stonehearth Multiplayer Performance Optimization

This guide explains the multiplayer performance optimizations implemented in the Stonehearth Multiplayer Enhancements mod and provides tips for achieving the best possible performance in multiplayer sessions.

## Performance Features

The mod implements several optimization strategies to improve multiplayer performance:

### Entity Prioritization System

Entities in the game world are assigned priority levels based on their importance and proximity to players:

- **Priority 1**: Entities close to players (full updates)
- **Priority 2**: Entities within player working areas (frequent updates)
- **Priority 3**: Neutral entities in the world (periodic updates)
- **Priority 4**: Distant entities (minimal updates)
- **Priority 5**: Inactive entities (rare updates)

This system ensures that computational resources are focused on the most relevant game elements.

### Pathfinding Optimization

The mod improves pathfinding performance through several techniques:

- Reduced recalculation frequency for distant entities
- Lower precision pathfinding for non-critical entities
- Batched pathfinding calculations to reduce overhead
- Optimized path caching for frequently traveled routes

### Synchronization Control

Network traffic is optimized by:

- Throttling updates based on entity priority
- Batching network updates to reduce overhead
- Prioritizing critical gameplay elements
- Compressing data when appropriate

### Resource Allocation

The mod intelligently balances processing resources:

- Dynamic adjustment based on player count and activity
- Balanced processing across multiple settlements
- Background processing for non-essential tasks
- Adaptive processing based on server performance

## Optimization Tips for Server Hosts

### Hardware Recommendations

For the best multiplayer experience, we recommend:

- **CPU**: Quad-core processor or better (higher frequency preferred)
- **RAM**: Minimum 8GB, 16GB recommended for larger games
- **Network**: Wired connection with at least 5Mbps upload speed
- **Storage**: SSD recommended for faster save/load operations

### Server Configuration

Optimize your server.bat file with these settings:

```bat
SET server_port=57094
SET max_players=4       # Adjust based on your server capacity
SET entity_limit=2000   # Lower for better performance
SET update_rate=30      # Balanced setting for most servers
```

### World Settings

When generating a new world, consider these performance-friendly settings:

- **World Size**: Smaller worlds (8x8 to 10x10) perform better
- **Biome**: Temperate biomes generally have fewer entities
- **Features**: Reduce the number of generated landmarks and structures
- **Wildlife**: Consider reducing wildlife spawn rates

## Client-Side Performance Tips

Players connecting to multiplayer servers can improve their experience by:

1. **Graphics Settings**: Reduce view distance and particle effects
2. **Game Settings**: 
   - Disable ambient creatures
   - Reduce maximum number of visible citizens
   - Turn off weather effects if experiencing lag
3. **Gameplay Habits**:
   - Build compact settlements rather than sprawling ones
   - Avoid excessive stockpile creation
   - Regularly clean up unused items
   - Limit the number of active crafters and workers

## Performance Monitoring

The mod includes basic performance monitoring tools:

- `/perfstats` - Displays current server performance statistics
- `/entitycount` - Shows the number of entities by priority level
- `/networkusage` - Displays network traffic information

Use these commands to identify potential performance bottlenecks.

## Known Performance Issues

- Large numbers of pathfinding entities (workers, soldiers) can still cause lag spikes
- Extreme terrain modification can temporarily reduce performance
- Very large save files (50MB+) may cause longer load times
- Connecting more than 8 players simultaneously is not recommended

## Troubleshooting Performance Problems

If you experience persistent performance issues:

1. Check server logs for entity count warnings
2. Verify that no player has an excessive number of citizens or items
3. Consider resetting specific areas with performance problems
4. Ensure all players have the latest version of the mod
5. Try reducing the game simulation speed during high-activity periods

## Future Performance Improvements

Planned performance enhancements include:

- Advanced multi-threading for pathfinding calculations
- Improved entity culling for distant objects
- Smarter AI task batching
- Optimized rendering for client-side performance
- Memory usage optimizations for long play sessions

We're continuously working to improve multiplayer performance. Please share your feedback and performance reports on our Steam Workshop page or GitHub repository.