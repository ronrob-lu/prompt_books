# free_miners

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/free_miners
- **Mod Name**: `free_miners`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A Minetest mod that spawns a player-like Miner NPC to automate mining operations. The Miner mines a defined area layer-by-layer, deposits harvested materials into chests, automatically handles tool wear by crafting or retrieving replacement tools, and relocates to mine adjacent areas when done.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `mcl_core`, `mcl_chests`, `mcl_tools`
- **Asset Structure**: `LICENCE.md`, `README.md`, `crafting.lua`, `init.lua`, `inventory.lua`, `items.lua`, `miner.lua`, `mod.conf`

### System Description
The `free_miners` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
* **3D Flight & Navigation:** Navigates via direct 3D flying vectors rather than needing complex stair construction.
* **Layer-by-Layer Mining:** Systematically clears a 14x14x7 area block-by-block, returning to the chest after each layer to deposit items.
* **Smart Inventory & Chest Handling:**
  * Deposits mined items to chest networks.
  * Dynamically crafts new chests if existing ones run out of space.
  * Drops off any excess blocks/items and retains or retrieves necessary tools.
* **Auto-Crafting & Tool Retrieval:** Automatically retrieves materials from chests to craft wood/stone tools (pickaxes, shovels, axes) when current ones break.
* **Sword Vulnerability:** Miner NPCs can be killed in-world using a sword or normal weapons.
* **Multi-Game Compatibility:** Dynamically resolves item names and crafting recipes for both standard **Minetest Game** (`default:`) and **MineClone2** (...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `free_miners`
- Registered Nodes/Entities: Derived from `free_miners` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `free_miners` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `free_miners` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity free_miners:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
