# breakdance_npc

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/breakdance_npc
- **Mod Name**: `breakdance_npc`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A [Minetest/Luanti](https://www.luanti.org/) mod by **ronrob-lu** that adds Spanish breakdancer NPCs to your world. They stand idle until a **`ve_radio:radio`**, **`djdeck:mixer`**, **`djdeck:turntable`**, or **`djdeck:loudspeaker`** block appears nearby — then they start dancing!

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `ve_radio`, `djdeck`
- **Asset Structure**: `README.md`, `init.lua`, `mod.conf`, `models`, `textures`

### System Description
The `breakdance_npc` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **25 randomised Spanish names** (male & female)
- **4 distinct visual styles** (outfits: green/blue, red/orange, purple/gold, cyan/white)
- **13 baked dance animations** across three genres:
  - *Shuffle* — T-Step, Running Man, Heel-Toe, Side Step, Glide
  - *Breakdance* — Six-Step, Windmill, Flare, Baby Freeze, Swipe, Headspin
  - *Streetdance* — The Wave, The Cabbage Patch
- Automatically **detects `ve_radio:radio`, `djdeck:mixer`, `djdeck:turntable`, or `djdeck:loudspeaker`** within 10 nodes
- **Random move selection** — a new move is chosen every second while the radio is active
- NPCs are **invincible** and **static** (decorative)
- Right-click any dancer to see their **name, style & current move**
- Animations baked at **15 fps** into the B3D model

---

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `breakdance_npc`
- Registered Nodes/Entities: Derived from `breakdance_npc` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `breakdance_npc` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `breakdance_npc` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity breakdance_npc:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
