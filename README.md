<div align="center">

# CubeCoder VR

### A complete VR block-based programming environment and controlled honours study

Users physically grab, arrange and connect programming blocks, then execute the spatial program to guide a character through five progressively harder puzzle levels.

![Unity](https://img.shields.io/badge/Unity-2021.3.8f1-000000?logo=unity&logoColor=white)
![C%23](https://img.shields.io/badge/C%23-Custom%20Runtime-512BD4?logo=csharp&logoColor=white)
![OpenXR](https://img.shields.io/badge/XR-OpenXR%20%7C%20Oculus-5A45FF)
![Study](https://img.shields.io/badge/User%20Study-31%20Participants-0A7E8C)

**[Watch the demonstration](https://www.youtube.com/watch?v=SXKN5MoZjaQ)**

</div>

---

## Evidence snapshot

| Area | Evidence |
|---|---:|
| Study participants | **31** |
| Experimental / control | **16 / 15** |
| Progressive levels | **5** |
| Programming concepts | Sequence, conditionals, loops and functions |
| Mean learning improvement | **+4.53** vs **+1.23** points |
| Between-group learning comparison | **p = 0.0947**, weak exploratory evidence |
| User-experience comparison | No significant difference, **p = 0.3515** |

The study did not prove that visual embellishments improve learning. The primary contribution is the design, implementation and controlled evaluation of a novel VR programming environment.

## Video and project media

[![Watch CubeCoder VR](https://img.youtube.com/vi/SXKN5MoZjaQ/hqdefault.jpg)](https://www.youtube.com/watch?v=SXKN5MoZjaQ)

![In-game demonstration](docs/images/demo.gif)

## Project overview

CubeCoder VR was the software artefact for my University of Queensland Bachelor of Software Engineering (Honours) thesis:

> **The Effect of Visual Embellishments in Virtual Reality on Learning**

The project combines:

1. a custom visual-programming system where executable algorithms are assembled from physical 3D blocks; and
2. a controlled study comparing versions with and without additional success/failure visual effects.

A custom runtime interprets the spatial block arrangement and translates it into visible movement and interactions inside obstacle-based levels.

## Research design

The thesis asked:

1. Do responsive visual embellishments improve user experience in a VR educational game?
2. Do they improve learning outcomes?

The experimental condition added fireworks after successful completion and sequential bridge explosions after failure. The control condition retained the same learning content and gameplay without those effects.

Each participant completed:

```text
Consent and background information
              ↓
Seven-question programming pre-test
              ↓
VR tutorial
              ↓
10–15 minute CubeCoder session
              ↓
Simulator Sickness Questionnaire
              ↓
Player Experience of Need Satisfaction
              ↓
Seven-question programming post-test
```

The pre/post instrument had a maximum score of 35.

## Study results

| Measure | With embellishments | Without embellishments | Result |
|---|---:|---:|---|
| Mean PENS score | 5.80 | 5.54 | No significant difference, p = 0.3515 |
| Mean total simulator-sickness score | 592.74 | 731.73 | No significant difference, p = 0.3585 |
| Mean pre-test | 18.13 / 35 | 19.33 / 35 | Descriptive baseline |
| Mean post-test | 22.66 / 35 | 20.57 / 35 | Descriptive result |
| Mean improvement | +4.53 | +1.23 | Weak exploratory evidence, p = 0.0947 |

The learning result is hypothesis-generating, not conventionally statistically significant.

## What users can program

| Concept | Implementation |
|---|---|
| Sequence | Blocks execute in tray order |
| Movement | Direction and movement blocks drive the character |
| Conditionals | World-aware conditions select behaviour |
| Loops | While-style blocks repeat while a condition remains true |
| Functions | A secondary tray defines a reusable sequence called from the main program |

Example spatial program:

```text
Move Forward
While Can Move
    Move Forward
End While
Turn Right
Call Function
```

## Core engineering features

- physical block grabbing, placement, connection and reordering;
- spatial code and function trays;
- holographic input slots for compound blocks;
- custom block interpreter;
- coroutine-based sequential execution;
- maximum-iteration protection for loops;
- world-aware condition evaluation;
- reusable functions;
- five distinct puzzle environments;
- execution highlights, errors and success/failure feedback.

## Architecture

```text
VR controllers
      ↓
XR grab and placement interactions
      ↓
Code blocks + connection slots
      ↓
Code tray and function tray
      ↓
Structural checks and execution order
      ↓
Custom C# interpreter
      ↓
Map and character controller
      ↓
Movement, collision and level feedback
```

## Five-level progression

| Level | Programming focus |
|---|---|
| Tutorial Island | VR interaction and basic sequencing |
| Conditional Cave | `if` logic and obstacle avoidance |
| Crystal Conditions | world-state conditions and `while` blocks |
| Function Fortress | reusable functions |
| Algorithm Altar | integrated final puzzle |

## Participant feedback

Frequently praised:

- visual environments and sense of exploration;
- physical representation of programming logic;
- puzzle-based learning;
- multiple valid solutions.

Frequently criticised:

- motion sickness during locomotion and turning;
- execute/reset controls being too close;
- destructive reset rather than iterative edit/rerun;
- unclear symbols and compound-block inputs;
- collision bugs and frame-rate drops.

These observations informed recommendations for teleportation/comfort locomotion, clearer onboarding, separated controls and non-destructive program testing.

## Technology

- Unity `2021.3.8f1`
- C#
- XR Interaction Toolkit `2.3.2`
- OpenXR `1.4.2`
- Oculus XR `3.0.2`
- TextMesh Pro
- Universal Render Pipeline and Shader Graph
- coroutines, physics, prefabs and scene-based level design

## Running the project

Requirements:

- Unity Hub and Unity `2021.3.8f1`;
- OpenXR-compatible headset/runtime;
- PC capable of running the Unity VR project.

Clone the repository and add it through Unity Hub:

```bash
git clone https://github.com/Lukeyone/VR-Block-Based-Programming-Environment-Thesis.git
```

Open a gameplay scene under `Assets/Scenes/`, verify XR plug-in settings and enter Play Mode.

## Limitations

- small convenience sample;
- variable prior coding, gaming and VR experience;
- imperfect condition balance;
- one embellishment intensity;
- simulator sickness and locomotion discomfort;
- older Unity/XR stack;
- deliberately limited programming language;
- research prototype rather than supported product.

## Portfolio context

This project demonstrates:

- substantial Unity/C# software engineering;
- custom language/runtime design;
- spatial human-computer interaction;
- bounded loop execution and world-state logic;
- experimental design and quantitative analysis;
- honest interpretation of non-significant findings;
- translation of participant feedback into product recommendations.

## Author

**Lachlan McDonald**  
Bachelor of Software Engineering (Honours), The University of Queensland

[Portfolio](https://lukeyone.github.io) · [LinkedIn](https://www.linkedin.com/in/lachlanmcdonaldtech) · [Email](mailto:lachlanmcdonald2000@gmail.com)
