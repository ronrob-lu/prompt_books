# escalator — Luanti (Minetest) Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/escalator
- **Mod Name**: `escalator`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A fully functional escalator system that transports **players, NPCs, and mobs**

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `stairs`, `mobs_redo`, `mobs_monster`, `default`, `mcl_stairs`, `mcl_core`
- **Asset Structure**: `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`, `screenshots`, `settingtypes.txt`, `textures`

### System Description
The `escalator` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
| Feature | Detail |
|---|---|
| **Controller block** | `escalator:controller` – place at the base of a staircase |
| **Auto-detection** | Direction and orientation detected automatically from stair layout |
| **Transport** | Moves players and mobs via velocity override |
| **Legacy mob support** | Positional nudge for mobs without `set_velocity` |
| **Performance** | Scans only the active stair-path; no global entity sweeps |
| **Tunable** | All speeds and lengths configurable via the settings panel |
| **Cross-gamepack** | Works with MTG, VoxeLibre/MineClone2, and any game with stair nodes |

---

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `escalator`
- Registered Nodes/Entities: Derived from `escalator` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `escalator` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `escalator` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity escalator:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
