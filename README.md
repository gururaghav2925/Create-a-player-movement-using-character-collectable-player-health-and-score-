# EX NO : 2  Player Movement, Collectables, Health, and Score System in Unreal Engine

## Aim
To implement a basic player controller using the Character class in Unreal Engine, with movement controls, collectable items, a health system, and a score display.

## Procedure

### 1. Create Player Character with Movement
- Create a **Blueprint Class** based on `Character` (e.g., `BP_PlayerCharacter`).
- Add a **Camera** and **Spring Arm** for third-person or first-person view.
- In the **Event Graph**, add input bindings for movement:
  - **MoveForward**, **MoveRight** using `InputAxis` events.
  - Use `Add Movement Input` for directional movement.

### 2. Create Collectable Item
- Create a new **Actor Blueprint** (e.g., `BP_Collectable`).
- Add a **Static Mesh** and **Sphere Collision** component.
- On `BeginOverlap` with player:
  - Destroy the collectable.
  - Call a custom event or function on the player to increment score or health.

### 3. Implement Health System
- In `BP_PlayerCharacter`, add a **Health** variable (e.g., `float`, default: 100).
- Create a **TakeDamage** function to subtract from Health.
- Optionally, implement logic to handle 0 health (e.g., death or respawn).

### 4. Implement Score System
- Add a **Score** variable (`int`) in `BP_PlayerCharacter`.
- When a collectable is picked up, increase the score.
- Display score using **UMG Widget**:
  - Create a `Widget Blueprint` (e.g., `W_HUD`).
  - Add **Text Blocks** bound to Health and Score variables.

### 5. Setup Game Mode
- Create a new **Game Mode Blueprint**.
- Set `BP_PlayerCharacter` as the default pawn.
- Set the HUD widget in the Game Mode’s BeginPlay using `Create Widget` and `Add to Viewport`.

## Output

![21cd18e5-9ec4-4564-924c-8e07f8b1b762](https://github.com/user-attachments/assets/b5a5b22e-1e24-4d4b-a100-373233dcfab6)

![9a6c0693-3ee8-4bd8-94a7-09de2a134f1c](https://github.com/user-attachments/assets/5b28f376-6367-4cc8-aee3-3e7628045efe) 


![7995e34b-0a95-4501-bd08-f099c79d6312](https://github.com/user-attachments/assets/ab1c690c-3d5b-4de9-b9b0-44cbf849ef2e)



## Result
A working prototype was developed with:
- Player movement using the Character class.
- Collectable items that increase score or health.
- A dynamic health system with logic for damage.
- On-screen UI displaying player health and score.

This system forms the basis for more advanced gameplay mechanics in Unreal Engine.
