# Jules Mod for Luanti / Minetest

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/jules
- **Mod Name**: `jules`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: dedicated to google jules deprecation

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`, `mobs`
- **Optional Dependencies**: `default`
- **Asset Structure**: `LICENSE.md`, `README.md`, `google-jules.png`, `init.lua`, `jules.png`, `mod.conf`, `screenshot.png`, `textures`

### System Description
The `jules` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
### 1. Jules Monster Mob (`jules:jules`)
- Powered by the **Mobs Redo** (`mobs`) API.
- Aggressive monster mob that roams the world, attacking players and hostile intruders.
- Vulnerable to water and lava damage, and cannot swim or float (sinks in liquids).
- Drops Google Font letter blocks (`jules:block_g`, `jules:block_o`, `jules:block_l`, `jules:block_e`) and mese crystal fragments when defeated.
- Broadcasts a memorial message to the server chat upon death:
  > *"Goodbye Jules! You were the most loved tool in the world."*

### 2. Spawn Egg
- Creative / inventory spawn egg (`jules:jules` / "Spawn Jules") allowing players to spawn Jules anytime.
- Uses a custom spotted purple egg texture (`jules_egg.png`).

### 3. Natural Spawning
- Jules spawns naturally in the Luanti world at an incredibly high frequency across land at all times (day and night)!
- Spawns across all land nodes includi...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `jules`
- Registered Nodes/Entities: Derived from `jules` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `jules` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `jules` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity jules:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
