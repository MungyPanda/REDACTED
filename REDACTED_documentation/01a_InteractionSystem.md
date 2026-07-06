# Purpose

The interaction system manages communication between the player and world interaction objects. It detects valid interactable world objects, validates conditions, calls special interaction logic and routes execution to the appropriate actor and specialized systems while keeping the logic modular and reusable
# Responsibilities

	Detect available interactions
	Track active interaction components
	Validate interaction conditions
	Route execution to interaction actors and systems
	Provide consistent flow
# Out of Scope

	Battle logic
	Inventory logic
	Dialogue logic
# Communication

![ICFC](../Images/InteractionCommunicationFC.png)
<details> 
	<summary>light version</summary> 
	<br> 
	<img src="https://github.com/MungyPanda/REDACTED/blob/main/Images/InteractionCommunicationFC_light.png">
</details>
# Architecture Flow

![VARCH](../Images/InteractionValidationARCH.png)
<details> 
	<summary>light version</summary> 
	<br> 
	<img src="https://github.com/MungyPanda/REDACTED/blob/main/Images/InteractionValidationARCH_light.png">
</details>
# Dependencies

	Player Controller
	General Interaction Component
	General Interaction Actor
	Game Instance
	Inventory System
	Dialogue System
	Handler System

# Extensibility

Designed to support additional interaction types by extending the base interaction actor without modifying logic
# Design Goals

	Reusable
	Modular
	Easy to extend
	Minimal coupling
	Consistent flow