# 🚀 Sky Doodles: Majestic Horizons! ☁️✈️

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/sky_doodles
- **Mod Name**: `sky_doodles`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: Welcome to **Sky Doodles**, the ultimate Luanti (Minetest) mod that brings your skies to life with autonomous, decorative airplanes! Transform your empty, silent skies into a bustling, dynamic horizon without lifting a finger.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`, `models`, `textures`

### System Description
The `sky_doodles` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `sky_doodles` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `sky_doodles`
- Registered Nodes/Entities: Derived from `sky_doodles` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `sky_doodles` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `sky_doodles` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity sky_doodles:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
