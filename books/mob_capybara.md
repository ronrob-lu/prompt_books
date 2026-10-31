# Capybara Mob for Luanti (Minetest)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/mob_capybara
- **Mod Name**: `mob_capybara`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A Luanti / Minetest mob mod introducing the **Capybara** using the `mobs_redo` API.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `mobs`
- **Optional Dependencies**: `default`, `farming`, `mcl_core`, `mcl_flowers`, `mobs_animal`
- **Asset Structure**: `README.md`, `capybara.lua`, `init.lua`, `license.md`, `mod.conf`, `models`, `readme.md`, `textures`

### System Description
The `mob_capybara` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Model & Texture**: Uses 3D glTF model (`capybara.gltf`) and custom texture (`texture_capybara.png`).
- **Animations**:
  - `0 - 30`: Stand / Idle
  - `31 - 60`: Walk
  - `61 - 90`: Swim (Surface swimming in water)
  - `91 - 120`: Chill / Lay
- **Physical Dimensions**: 75% scale (`collisionbox = {-0.3, -0.3, -0.3, 0.3, 0.3, 0.3}`).
- **Visual Scale**: `visual_size = {x = 7.5, y = 7.5}`.
- **Behavior**:
  - Completely passive, non-tameable, and non-rideable.
  - Drops nothing on death.
  - Floats on surface water (head remains above water level).
  - Eats wild plants (`default:junglegrass`, `default:grass_2`, `default:grass_3`, `default:grass_4`, `default:papyrus`, and MineClone 2 equivalents).
  - Enjoys chilling near wooden structures near rivers, swamps, and jungles.
- **Compatibility**: Supports Minetest Game (`default`) and MineClone 2 (`mcl_*`).

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `mob_capybara`
- Registered Nodes/Entities: Derived from `mob_capybara` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `mob_capybara` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `mob_capybara` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity mob_capybara:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
