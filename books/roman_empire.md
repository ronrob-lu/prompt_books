# Roman Empire — Luanti / Minetest Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/roman_empire
- **Mod Name**: `roman_empire`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: **Author:** ronrob-lu

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `ephesus`
- **Optional Dependencies**: `default`, `doors`, `mg_villages`
- **Asset Structure**: `init.lua`, `licence.md`, `mod.conf`, `readme.md`, `settingtypes.txt`

### System Description
The `roman_empire` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Roman Temples** — Rectangular buildings with full colonnaded porticos
  (`ephesus:marble_column` + `ephesus:hat_column`) on the facade.
- **Roman Villas** — Multi-room structures with marble floors, decorated
  doorways and courtyard columns.
- **Roman Porticos** — Long open colonnaded halls with a marble roof.
- **Standalone Column Groups** — Single or grouped columns topped with capitals (`ephesus:hat_column` / `ephesus:medium_column_top`) standing alone or on pedestals.
- **Ruins Mode (default: ON)** — Randomly erodes the upper height of generated structures to look like ancient Roman ruins. Includes strict gravity/support checks so no floating or hanging blocks remain suspended in mid-air. Can be easily turned off to spawn full, intact buildings.
- **Configurable Logging (default: ON)** — Log mapgen generation and spawning to `debug.txt` and server console. Can be toggled on/off ...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `roman_empire`
- Registered Nodes/Entities: Derived from `roman_empire` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `roman_empire` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `roman_empire` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity roman_empire:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
