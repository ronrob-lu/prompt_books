# Mobs Beaver for Luanti (Minetest / Mineclonia)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/mobs_beaver
- **Mod Name**: `mobs_beaver`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A semi-aquatic beaver mob for Luanti / Minetest / Mineclonia built using the TenPlus1 **Mobs Redo** API.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `mobs`
- **Optional Dependencies**: `default`, `farming`, `flowers`, `lucky_block`, `mcl_core`, `mcl_farming`, `mcl_flowers`, `ethereal`
- **Asset Structure**: `beaver.lua`, `init.lua`, `licence.md`, `mod.conf`, `models`, `readme.md`, `textures`

### System Description
The `mobs_beaver` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Amphibious Semi-Aquatic Life**: Roams naturally on land, walks on riverbanks and beaches, and dives/swims smoothly through water.
- **Natural Animations**:
  - `Stand`: Calm idle posture.
  - `Stand1` (Gnaw): Periodically nibbles and chews on sticks/wood.
  - `Walk` & `Run`: Quadruped locomotion on land.
  - `Fly` (Swim): Fluid swimming strokes while submerged in water.
  - `Jump` & `Attack`: Agile obstacle clearing and defensive attacks when provoked.
  - `Die`: Smooth death sequence.
- **Ecological Interaction**:
  - Beavers follow and can be tamed or bred using saplings, sticks, wood, apples, and carrots.
  - They nibble on dry shrubs, fallen twigs, saplings, and grass in the wild.
- **Standard Mobs Redo Interactions**:
  - **Feeding & Breeding**: Feed 6 suitable items to tame or trigger breeding.
  - **Taming**: Once tamed, can be renamed with nametags.
  - **Protection**: Right-...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `mobs_beaver`
- Registered Nodes/Entities: Derived from `mobs_beaver` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `mobs_beaver` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `mobs_beaver` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity mobs_beaver:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
