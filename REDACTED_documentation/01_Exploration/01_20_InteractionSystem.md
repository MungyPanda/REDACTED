# Purpose

The interaction system manages communication between the player and world interaction objects. It detects valid interactable world objects, validates conditions [01_21_InteractionValidation](01_21_InteractionValidation.md), calls special interaction logic [01_30_Handler](01_30_Handler.md) and routes execution to the appropriate actor [01_23_InteractionActor](01_23_InteractionActor.md) and specialized systems while keeping the logic modular and reusable.
# Responsibilities

	Detect available interactions
	Track active interaction components
	Validate interaction conditions
	Route execution to interaction actors and systems
	Provide consistent flow
# Communication

![ICFC](../Images/InteractionCommunicationFC.png)
<details> 
	<summary>light version</summary> 
	<br> 
	<img src="(https://github.com/MungyPanda/REDACTED/blob/main/Images/InteractionCommunicationFC_light.png)">
</details>

# Architecture Flow

![VARCH](InteractionValidationARCH.png)
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

Designed to support additional interaction types by extending the base interaction actor without modifying logic and extending the validation to support more checks if required
# Design Goals

	Reusable
	Modular
	Easy to extend
	Minimal coupling
	Consistent flow

# Notes

This system was the first main focus of this project as it was a shift from the battle system that started off based on tutorials. Since learning through this media was borderline ineffective, something else had to come into focus. Learning through trial and mostly error was better and creating things almost from scratch makes it feel more personal, even though this system is quite basic. The currently working types are important though and a valuable part of any such game. Connecting them together, adding and removing features and mainly making them reusable and designer friendly, so that an actor could be placed, its details edited and from that point it would work as intended, were extremely fun and rewarding.