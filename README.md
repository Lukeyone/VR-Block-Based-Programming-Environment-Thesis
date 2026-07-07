<div align="center">

# VR Block-Based Programming Environment

### An embodied visual-programming puzzle system built in Unity for a Software Engineering Honours thesis

Build programs by physically grabbing, arranging, connecting and executing code blocks in virtual reality, then watch those programs control a character through obstacle-based levels.

![Unity](https://img.shields.io/badge/Unity-2021.3.8f1-000000?logo=unity&logoColor=white)
![C%23](https://img.shields.io/badge/C%23-Programming-512BD4?logo=csharp&logoColor=white)
![OpenXR](https://img.shields.io/badge/XR-OpenXR%20%7C%20Oculus-5A45FF)
![Thesis](https://img.shields.io/badge/Project-Honours%20Thesis-0057B8)

</div>

---

## Video demonstration

<div align="center">

<a href="https://www.youtube.com/watch?v=SXKN5MoZjaQ">
  <img src="https://img.youtube.com/vi/SXKN5MoZjaQ/hqdefault.jpg" width="720" alt="Watch the VR Block-Based Programming Environment demonstration">
</a>

**[Watch the full demonstration on YouTube](https://www.youtube.com/watch?v=SXKN5MoZjaQ)**

</div>

![In-game demonstration of the VR programming environment](docs/images/demo.gif)

## Overview

This project was developed as my **Bachelor of Software Engineering (Honours)** thesis at **The University of Queensland**.

The system investigates how programming logic can be represented as tangible objects in a three-dimensional environment. Instead of typing code, a user constructs a program by picking up colour-coded blocks, placing them into a spatial code tray and connecting blocks through input/output slots. A custom runtime then interprets the arrangement and executes the resulting behaviour inside a level.

The prototype combines:

- A VR interaction system for grabbing and positioning code blocks
- A custom visual-programming model and execution engine
- Grid-based character movement and obstacle detection
- Puzzle levels that teach sequencing and control flow
- Immediate visual and UI feedback during execution

## What the user can program

| Concept | Implementation in the environment |
|---|---|
| **Sequence** | Blocks execute in the order in which they are arranged in the code tray |
| **Movement** | Forward movement and directional/turning blocks control the level character |
| **Conditionals** | Conditional blocks query the current world state, such as whether movement is possible |
| **Loops** | While-style blocks repeatedly execute a connected action while a condition remains true |
| **Functions** | A separate function tray lets users define reusable behaviour and invoke it from the main program |

A program can resemble:

```text
Move Forward
While Can Move
    Move Forward
End While
Turn Right
Call Function
```

The program is assembled spatially, interpreted at runtime and translated into visible actions on the level map.

## Core features

- **Physical code construction** — grab, move, connect, reorder and remove programming blocks using VR controllers
- **Spatial code tray** — arranges blocks into an executable sequence and highlights valid placement areas
- **Holographic input slots** — show where conditions and actions can be attached to compound blocks
- **Custom interpreter** — converts the physical block arrangement into runtime behaviour
- **Timed execution** — actions run sequentially through coroutines rather than completing simultaneously
- **Loop protection** — while blocks include a maximum-iteration guard to prevent unbounded execution
- **World-aware conditions** — condition blocks inspect the map state before selecting a branch or continuing a loop
- **Reusable functions** — users can build a secondary function sequence and call it from the main program
- **Puzzle progression** — levels include start tiles, goals, obstacles, limited block inventories and inter-level teleporters
- **Execution feedback** — messages, highlights and visual effects communicate program state and errors

## System architecture

```text
VR controllers
      ↓
XR grab and placement interactions
      ↓
Code blocks + input/output slots
      ↓
Code tray and function tray
      ↓
Structural checks and execution ordering
      ↓
Custom block interpreter
      ↓
Map and character controller
      ↓
Movement, collision checks and level feedback
```

### Block model

The execution system is organised around specialised block types:

- **Executable blocks** perform actions and expose an action-completion duration.
- **Conditional blocks** return a Boolean result based on the environment.
- **Compound blocks** accept connected condition/action blocks through spatial slots.
- **Function blocks** execute a reusable sequence stored in a separate tray.

For example, the movement condition accesses a central map tracker to determine whether the character can move. A while block repeatedly invokes its connected executable block, waits for the action to complete and stops when its condition becomes false or its iteration limit is reached.

### World and level layer

The programmed character operates on a level map containing:

- Walkable paths
- Obstacles and walls
- Start and goal tiles
- Direction indicators
- Level-transition teleporters
- Per-level block limits and instructional UI

This connects abstract control-flow concepts to immediately visible consequences in the environment.

## Technology stack

- **Unity 2021.3.8f1 (LTS)**
- **C#**
- **Unity XR Interaction Toolkit 2.3.2**
- **OpenXR Plugin 1.4.2**
- **Oculus XR Plugin 3.0.2**
- **TextMesh Pro**
- **Universal Render Pipeline / Shader Graph**
- Unity coroutines, physics, prefabs and scene-based level design

## Running the project

> **Repository size:** this is a complete Unity VR project containing scenes, models, textures, prefabs and other source assets, so the clone is large.

### Requirements

- Unity Hub
- **Unity 2021.3.8f1**
- An OpenXR-compatible VR headset and runtime
- A machine capable of running a Unity PCVR project
- Git installed locally

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/Lukeyone/VR-Block-Based-Programming-Environment-Thesis.git
   ```

2. Add the cloned directory as a project in Unity Hub.
3. Open it with **Unity 2021.3.8f1** and allow Unity to restore the packages.
4. Confirm that the appropriate XR provider is enabled under **Project Settings → XR Plug-in Management**.
5. Connect and start the headset runtime.
6. Open a gameplay scene from `Assets/Scenes/` — for example, `Alternate Level 1.unity` — and enter Play Mode.

XR configuration can vary between headsets and runtime versions. The project includes both OpenXR and Oculus XR packages, but local plug-in settings may still need to be adjusted for the target device.

## Repository structure

```text
├── Assets/
│   ├── Scenes/              # Gameplay and alternate level scenes
│   ├── Scripts/             # Block execution, map, interaction and UI logic
│   ├── Prefabs/             # Code blocks, character and reusable scene objects
│   ├── Materials/           # Block colours and environment materials
│   └── ...                  # Models, textures, audio and XR assets
├── Packages/
│   └── manifest.json        # Unity and XR package dependencies
├── ProjectSettings/         # Unity editor, rendering and XR configuration
├── docs/images/             # README demonstration media
├── .gitignore
└── README.md
```

## Engineering challenges addressed

- Mapping a program's abstract syntax to physical, movable VR objects
- Preserving execution order while blocks are freely repositioned
- Designing input/output connections that remain understandable in 3D space
- Supporting nested control-flow concepts without a conventional text parser
- Synchronising code execution with visible character movement
- Preventing infinite loops in a user-constructed program
- Connecting conditional logic to live world state and collision information
- Communicating invalid configurations and runtime state through VR-friendly feedback
- Balancing the number of available blocks across progressive puzzle levels

## Academic and project status

This repository is an **academic research prototype**, not a production programming platform. It was designed to explore embodied visual programming and to support an honours-level investigation into programming interactions in VR.

The project reached a playable level-based prototype with sequential instructions, conditionals, loops, functions, instructional UI and visual-feedback variants. Development was completed in 2023; the repository is preserved as a portfolio and research artefact.

## Limitations

- The project depends on an older Unity LTS and XR package configuration.
- VR input and rendering behaviour may require adjustment on newer runtimes or headsets.
- The programming language intentionally supports a limited set of commands and control-flow structures.
- The prototype is scene-driven and was designed for a controlled thesis evaluation rather than general-purpose authoring.
- The repository contains large Unity assets and is not distributed as a lightweight packaged release.

## Potential future work

- Variables, values and additional data types
- Nested compound blocks and more advanced functions
- Step-through execution, breakpoints and richer debugging tools
- Saving, loading and sharing programs
- Exporting visual programs to a conventional language
- Collaborative multi-user programming
- Accessibility improvements and alternative input methods
- Updated OpenXR configuration and standalone-headset support

## Author

**Lachlan McDonald**  
Bachelor of Software Engineering (Honours), The University of Queensland

[LinkedIn](https://www.linkedin.com/in/lachlanmcdonaldtech) · [GitHub](https://github.com/Lukeyone) · [Video demo](https://www.youtube.com/watch?v=SXKN5MoZjaQ)
