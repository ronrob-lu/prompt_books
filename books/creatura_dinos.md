# Dinos - Luanti / Minetest Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/creatura_dinos
- **Mod Name**: `creatura_dinos`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: Animated dinosaurs mod for **Luanti / Minetest**, powered by the **Creatura** mob API.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `creatura`
- **Optional Dependencies**: `default`
- **Asset Structure**: `LICENSE`, `README.md`, `apatosaurus.lua`, `convert_all_dinos.py`, `dino_animations.json`, `init.lua`, `mod.conf`, `models`

### System Description
The `creatura_dinos` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
This mod adds 6 animated prehistoric dinosaurs to Luanti/Minetest:

1. **Apatosaurus** (`dinos:apatosaurus`) - Giant gentle sauropod herbivore with massive health.
2. **Parasaurolophus** (`dinos:parasaurolophus`) - Peaceful duck-billed hadrosaur that lives in herds.
3. **Stegosaurus** (`dinos:stegosaurus`) - Plated herbivore that defends itself with a spiked tail attack when threatened.
4. **T-Rex** (`dinos:trex`) - Massive apex predator carnivore that hunts players and other entities.
5. **Triceratops** (`dinos:triceratops`) - Horned territorial herbivore that charges enemies when provoked.
6. **Velociraptor** (`dinos:velociraptor`) - Fast, agile pack hunter that attacks in groups.

Each dinosaur features fully animated models with smooth transitions:
- `idle`: Standing and ambient movement
- `walk`: Walking motion
- `run`: Fast running motion
- `attack`: Striking / biting animation
- `...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `creatura_dinos`
- Registered Nodes/Entities: Derived from `creatura_dinos` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `creatura_dinos` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `creatura_dinos` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity creatura_dinos:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
