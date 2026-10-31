# Menotics Delivery Drone Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/menotics_delivery_drone
- **Mod Name**: `menotics_delivery_drone`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: a luanti mod for a delivery drone

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`
- **Optional Dependencies**: `default`
- **Asset Structure**: `.gitignore`, `README.md`, `init.lua`, `mod.conf`, `sounds`, `textures`

### System Description
The `menotics_delivery_drone` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Autonomous Navigation**: Drones automatically fly between placed mese lamps in a patrol pattern
- **Persistent Inventory**: 32-slot inventory that saves items even when the drone is deactivated
- **Hover Effect**: Smooth hovering animation when waiting at lamp positions

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `menotics_delivery_drone`
- Registered Nodes/Entities: Derived from `menotics_delivery_drone` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `menotics_delivery_drone` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `menotics_delivery_drone` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity menotics_delivery_drone:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
