<div align="center">

# VR Block-Based Programming Environment

### An interactive visual-programming system built from scratch in Unity

A virtual-reality environment where users construct and execute programs by arranging interactive programming blocks.

</div>

---

## Overview

This project was developed as my Bachelor of Software Engineering Honours thesis at the University of Queensland.

The system explores how fundamental programming concepts can be represented and manipulated inside virtual reality. Users create programs by interacting with visual blocks representing instructions such as movement, loops, conditional statements and functions.

![Demonstration of the VR programming environment](docs/images/demo.gif)

## Core Features

* Interactive programming blocks in virtual reality
* Sequential instruction execution
* Movement commands
* Loop blocks
* Conditional `if` blocks
* Reusable functions
* Block connection and ordering
* Visual representation of program flow
* Program execution within the VR environment
* Immediate visual feedback

## Example Program

A user could construct a program resembling:

```text
Move Forward
Repeat 4 Times
    Turn Right
    Move Forward
End Loop
```

The connected blocks are interpreted and executed by the environment, causing the controlled object or character to perform the corresponding actions.

## Motivation

Traditional programming is generally represented through text on a two-dimensional screen.

This project investigated whether programming concepts could instead be represented as physical, spatial objects that users could:

* Pick up
* Move
* Connect
* Reorder
* Execute
* Debug visually

The goal was to explore a more tangible and interactive approach to understanding program structure and control flow.

## System Architecture

```text
VR user interaction
        ↓
Block selection and placement
        ↓
Block connection graph
        ↓
Program validation
        ↓
Instruction interpretation
        ↓
Runtime execution
        ↓
Visual feedback in the environment
```

## Programming Concepts Implemented

### Sequential Execution

Blocks execute in their connected order.

### Loops

Loop blocks execute an enclosed sequence multiple times.

### Conditional Logic

Conditional blocks execute instructions only when their condition is satisfied.

### Functions

Users can group reusable behaviour into functions and invoke it from another part of the program.

### Movement Instructions

Movement blocks translate programming instructions into visible actions inside the virtual environment.

## Technical Challenges

The project required solutions for:

* Representing program logic as physical VR objects
* Determining block execution order
* Supporting nested control-flow structures
* Validating block connections
* Translating block arrangements into executable behaviour
* Providing understandable feedback when a program was invalid
* Designing interactions suitable for VR controllers

## Technologies

* Unity
* C#
* Virtual-reality interaction systems
* ShaderLab
* GLSL
* HLSL
* Visual programming
* Custom program interpretation

## Repository Structure

```text
├── Assets/                 # Scripts, scenes, prefabs and resources
├── Packages/               # Unity package configuration
├── ProjectSettings/        # Unity project settings
├── docs/
│   └── images/             # Screenshots and demonstration media
├── .gitignore
└── README.md
```

## Running the Project

### Requirements

* Unity `[insert version]`
* `[Insert supported VR headset or runtime]`
* `[Insert OpenXR, SteamVR or other dependencies]`

### Setup

1. Clone this repository.
2. Open the project through Unity Hub.
3. Use Unity version `[insert version]`.
4. Connect a supported VR headset.
5. Open the primary scene at `[insert scene path]`.
6. Enter Play Mode or create a local build.

## Thesis Outcomes

Add your actual thesis findings here, including:

* What you tested
* Number and type of participants, if applicable
* Usability findings
* Technical results
* Conclusions about visual programming in VR

## Limitations

* `[Hardware or headset limitations]`
* `[Interaction limitations]`
* `[Programming-language limitations]`
* `[Study or evaluation limitations]`

## Future Development

Potential extensions include:

* Additional data types and variables
* Nested functions
* More advanced debugging tools
* Collaborative programming in VR
* Saving and loading programs
* Program export to a traditional language
* Improved accessibility and onboarding

## Author

**Lachlan McDonald**
Bachelor of Software Engineering (Honours), University of Queensland

[LinkedIn](https://www.linkedin.com/in/lachlanmcdonaldtech)
