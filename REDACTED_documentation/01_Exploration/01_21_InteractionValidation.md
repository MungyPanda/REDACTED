# Purpose

Validation makes sure the player is overlapping a valid interactable world object and runs through multiple checks to then execute the correct owner's function [01_23_InteractionActor](01_23_InteractionActor.md). Since validation is separated from gameplay, the same pipeline can be reused for all interaction types and additional features can be added.
# Responsibilities

	Detect interactable objects
	Keep track of active interaction targets
	Maintain interaction priority
	Validate conditions
	Route execution to interaction actors
# Key Variables

	CurrentInteractComponent (BP_GeneralInteractComponent type)
	ActiveComponents (Array of BP_GeneralInteractComponent type)
# Execution Flow

![IVFC|472](InteractionValidationFC.png)
<details> 
	<summary>light version</summary> 
	<br> 
	<img src="https://github.com/MungyPanda/REDACTED/blob/main/Images/InteractionValidationFC_light.png">
</details>

# Communication Architecture

Player Controller owns the current interact component reference and the array of all overlapped
Interaction references are registered through collision overlap
Player Controller calls component when interaction starts
Interaction actors execute their own gameplay, communicating with Player Controller or managers
# Routing Logic

## Target Selection (actor overlap)

Overlapping logic happens inside of the Interaction Actor [01_23_InteractionActor](01_23_InteractionActor.md) and uses specific functions [01_24_ActorFunctions](01_24_ActorFunctions.md) as well as communication with the Player Controller

Interaction actors contain collision spheres
OnBeginOverlap component that belongs to the specific interaction actor is added to array
Interaction chosen based on priority
OnEndOverlap component is removed from the array and latest is again set
If there’s no active component, current interact component is set to none
## Validation (E pressed)

Function CanInteract() [01_22_ValidationFunctions](01_22_ValidationFunctions.md) inside of the current interact component is called
Special action handler lock is checked
If required special action is executed via handler
Key item lock is checked
If required inventory is checked for the item and quantity
## Execution (after validation)

Specific component owner interaction action or fail feedback is executed [01_24_ActorFunctions](01_24_ActorFunctions.md) based on the results of validation. Interaction system does not participate in gameplay logic, only validates and tells the interaction actor [01_23_InteractionActor](01_23_InteractionActor.md) what should follow next
# Dependencies

	Player Controller
	Interaction component
	Interaction actors
	Collision overlap events
# Design Goals

	Modular
	Actor independent
	Extendable
	Reusable flow
	Data driven configuration
# Notes

The component's validation inside of the component is a nice feature that can be separated from the actor itself to make sure this can be reused for others. Some interaction types might not require this feature at present but realistically every interaction may include a special action, for example a cutscene, spawn item, etc. that are not directly connected to the interaction flow. At the beginning every interaction type had it's own interaction component and most of the logic was kept there while the actor only took care of the visual setup and passing information that was edited via the details panel. Later, when revisiting this system, a lot of the logic was moved to the general actor, since interaction execution and fail feedback as of right now are actually interaction type specific and the components could be culled and only the general one used for the purposes of validation.