# Luanti-Ollama-NPC

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/llm_npc_core
- **Mod Name**: `llm_npc_core`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A complete, modular software suite that enables autonomous NPCs in Luanti (Minetest) worlds, controlled by a local Ollama Large Language Model (LLM). This system allows NPCs to perceive their environment, make decisions based on personality prompts, and execute actions like moving, digging, building, and interacting with the world.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `.gitignore`, `README.md`, `__pycache__`, `config.json`, `llm_npc_core`, `npc_brain.py`, `prompt_template.txt`

### System Description
The `llm_npc_core` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `llm_npc_core` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `llm_npc_core`
- Registered Nodes/Entities: Derived from `llm_npc_core` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `llm_npc_core` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `llm_npc_core` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity llm_npc_core:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
