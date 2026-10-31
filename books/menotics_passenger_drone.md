# Menotics Passenger Drone (Glass UFO Edition)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/menotics_passenger_drone
- **Mod Name**: `menotics_passenger_drone`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: a luanti menotics passenger drone

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`
- **Optional Dependencies**: `default`
- **Asset Structure**: `.gitignore`, `README.md`, `init.lua`, `menotics_passenger_drone`, `mod.conf`, `models`, `textures`

### System Description
The `menotics_passenger_drone` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Automated Flight**: The UFO automatically shuttles between Terminal blocks placed in the world, waiting **20 seconds** at each terminal.
- **Passenger Seat (Glass Dome)**: Players can right-click the UFO to enter its glass cabin. The passenger's body sits inside the dome, visible to other players thanks to alpha-transparent graphics! Press **Sneak (Shift)** or right-click the UFO again to dismount.
- **Dynamic 3D Pathfinding**:
  - Flies in a straight line if there is a clear line of sight.
  - If a wall or hill is in the way, it calculates vertical bypasses (flying up to 15 nodes higher to clear the obstacle) or horizontal perpendicular bypasses (flying around structures).
  - Works both in open fields and under ceilings.
- **Collision Recovery**: If blocked during flight, it announces `[Drone] Collision detected...`, backs up slightly, and recalculates a bypass path automatically.
...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `menotics_passenger_drone`
- Registered Nodes/Entities: Derived from `menotics_passenger_drone` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `menotics_passenger_drone` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `menotics_passenger_drone` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity menotics_passenger_drone:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
