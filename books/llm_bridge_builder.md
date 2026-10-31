# LLM Bridge Builder

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/llm_bridge_builder
- **Mod Name**: `llm_bridge_builder`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: Autonomous bridge-building NPC mod for **Luanti / Minetest** (MineClone2 / Mineclonia compatible).

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `README.md`

### System Description
The `llm_bridge_builder` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Zero external mod dependencies** — Complete `ky_materials` nodes and textures are bundled.
- **Autonomous NPC lifecycle** — Wander → Scan Coast → Plan with AI → Build → Rest → Repeat.
- **Smart coastline detection** — Walks outward in N/S/E/W directions to find where land meets water, then casts a ray across to find the opposite coast (up to 200 blocks away). Always picks the shortest crossing.
- **Multi-bridge per landmass** — Each landmass can have up to 4 bridges (one per cardinal direction). A second bridge in the same direction is never built.
- **Height-aware bridge design** — The LLM receives both coast ground levels and water Y. It designs a full column-by-column elevation profile with gradual ramps (max 1 block/column) so bridges connect smoothly even when one coast is higher than the other.
- **5 bridge types** — Stone Arch, Wooden Plank, Rope Suspension, Fortified Stone, L...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `llm_bridge_builder`
- Registered Nodes/Entities: Derived from `llm_bridge_builder` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `llm_bridge_builder` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `llm_bridge_builder` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity llm_bridge_builder:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
