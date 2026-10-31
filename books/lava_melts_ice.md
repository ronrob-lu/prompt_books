# lava\_melts\_ice

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/lava_melts_ice
- **Mod Name**: `lava_melts_ice`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A lightweight [Minetest](https://www.minetest.net/) / [Luanti](https://www.luanti.org/) mod that adds realistic thermal interactions between lava and cold nodes.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`
- **Optional Dependencies**: `default`
- **Asset Structure**: `LICENSE`, `README.md`, `init.lua`, `mod.conf`

### System Description
The `lava_melts_ice` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
In vanilla Minetest, lava does not interact with ice nodes at all. This mod bridges that gap by registering ABMs (Active Block Modifiers) that check for lava in all six orthogonal directions and apply the appropriate transformation when contact is detected.

### Interactions

| Node Touched by Lava    | Result               |
|-------------------------|----------------------|
| `default:ice`           | `default:water_flowing` |
| `default:dirt_with_snow`| `default:dirt`       |
| `default:snow` (layers) | *(handled by default game — unchanged)* |

---

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `lava_melts_ice`
- Registered Nodes/Entities: Derived from `lava_melts_ice` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `lava_melts_ice` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `lava_melts_ice` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity lava_melts_ice:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
