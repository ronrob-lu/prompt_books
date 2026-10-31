# Mobs MKPT (`mob_mkpt`)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/mob_mkpt
- **Mod Name**: `mob_mkpt`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A mob mod for **Luanti** (formerly Minetest) that introduces the MKPT NPC mob, powered by the [Mobs Redo](https://content.minetest.net/packages/TenPlus1/mobs/) API.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `mobs`
- **Optional Dependencies**: `default`
- **Asset Structure**: `README.md`, `init.lua`, `mod.conf`, `models`, `textures`

### System Description
The `mob_mkpt` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Custom 3D Model**: GLTF mesh (`mkpt.gltf`) with custom textures.
- **Custom Animations**: Walking, standing, and an occasional idle waving animation.
- **NPC Behavior**:
  - Neutral / NPC type (does not attack players unprovoked).
  - Defends itself if attacked (dogfight melee combat).
- **Spawn Egg**: Included spawn egg item (`MKPT`) for creative mode and spawning.

---

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `mob_mkpt`
- Registered Nodes/Entities: Derived from `mob_mkpt` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `mob_mkpt` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `mob_mkpt` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity mob_mkpt:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
