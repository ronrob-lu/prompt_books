# Beaver Damage (`beaver_damage`)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/beaver_damage
- **Mod Name**: `beaver_damage`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A realistic, ultra-low overhead environmental simulation mod for **Luanti / Minetest / Mineclonia / VoxeLibre**.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `mcl_core`, `mcl_mobs`, `mobs_animal`, `animalia`, `petz`, `mobs`
- **Asset Structure**: `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`

### System Description
The `beaver_damage` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
### 1. Dynamic Beaver Detection & Dual-Trigger Architecture
- Scans `minetest.registered_entities` on startup for any entity matching `*:beaver` or containing `beaver`.
- **Dual Triggering**: Hooks entity `on_step` and runs a lightweight fallback scanner to ensure beaver ticks execute reliably even if other mob mods monkey-patch or replace step methods.
- If no beaver mobs are installed, the mod idles with **zero CPU and RAM overhead**.

### 2. Smart, Ultra-Low RAM & CPU Architecture
- **No Heavy Polling**: Active beavers run on staggered, jittered timers (30–60s), eliminating tick spikes.
- **Microsecond Early-Exit**: Checks player distance and line-of-sight (`minetest.line_of_sight`) first. If any player is looking or nearby, the tick immediately yields.

### 3. Tree Felling
- Identifies living trees near beavers.
- **Tree vs. Structure Validation**: Strictly requires a vertical trunk ...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `beaver_damage`
- Registered Nodes/Entities: Derived from `beaver_damage` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `beaver_damage` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `beaver_damage` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity beaver_damage:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
