# Airliner Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/airliner
- **Mod Name**: `airliner`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: An attachable self-flying airliner with waypoint navigation, airport beacon tracking, Flight Computer GUI, natural 100-block takeoff & landing glide slopes, and automatic shuttle loop for Luanti / Minetest.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `README.md`, `init.lua`, `mod.conf`, `models`, `settingtypes.txt`, `textures`

### System Description
The `airliner` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **High-Speed Long-Distance Airline Flight**: Cruises smoothly across thousands of nodes at 50 m/s at a safe cruising altitude.
- **Natural 100-Block Takeoff**: Rolls 25 nodes down the runway, rotates, and smoothly climbs to cruising altitude over 100 blocks with pitch-up aircraft attitude.
- **Pre-Flight Runway Clearance Check**: Scans the 100-block takeoff corridor for trees, structures, or terrain obstacles; alerts the pilot with `"Runway blocked"` if the path is obstructed.
- **Natural 100-Block Landing Glide Slope**: Transitions into a gentle 100-block descent glide slope, flares before touchdown, and rolls to a smooth halt on the runway.
- **Landing Stuck & Obstruction Recovery**: Detects if the airliner hangs or gets obstructed on landing, alerting players with emergency dismount enabled so they can exit safely onto solid ground.
- **Single-Machine Shuttle Loop**: Reverses route ...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `airliner`
- Registered Nodes/Entities: Derived from `airliner` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `airliner` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `airliner` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity airliner:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
