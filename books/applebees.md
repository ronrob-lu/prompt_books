# Menotics Applebee

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/applebees
- **Mod Name**: `applebees`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A high-performance Minetest mod introducing a self-replicating NPC species powered by a Goal-Oriented Action Planning (GOAP) / FSM hybrid architecture.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`, `farming`, `beds`
- **Optional Dependencies**: `player_api`
- **Asset Structure**: `LICENSE.md`, `README.md`, `actions.lua`, `brain.lua`, `building.lua`, `init.lua`, `mod.conf`, `npc.lua`

### System Description
The `applebees` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Autonomous Survival**: NPCs independently forage for food (Apples) and building materials (Wood, Cotton).
- **Settlement Construction**: NPCs will harvest wood and craft their own `3x4` structural homes, complete with a bed.
- **Farming Cycle**: If resources are scarce, NPCs will plant saplings and cotton seeds to sustain their growth.
- **Self-Replication**: A "Thronglet"-style replication mechanic. Once an NPC has a home and acquires exactly 9 Apples, they biologically split, spawning a new NPC.
- **Siege Mode**: When trapped or out of space, NPCs will actively mine through obstructing blocks to escape and expand.
- **Performance Focused**: Built with Luanti/Minetest tick rates in mind. Uses lightweight A*/Line-of-Sight mechanics and updates environmental awareness periodically rather than every frame. Cap set to 100 NPCs by default to prevent server crashing.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `applebees`
- Registered Nodes/Entities: Derived from `applebees` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `applebees` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `applebees` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity applebees:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
