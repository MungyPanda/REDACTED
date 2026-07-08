
# Door

## Purpose

Barriers that can be opened and start locked or unlocked. May execute special logic via [01_30_Handler](01_30_Handler.md) 

## Key Variables

	Door Mesh - (Static Mesh type)
	Frame Mesh - (Static Mesh type)
	Closed Rotation - (Rotator type)
	Open Rotation - (Rotator type)
	Handler Values - (STR Interaction Values Handler type)
	Lock Values - (STR Interaction Values Lock type)

## Type Specific Logic

### Execute Interaction

-> OpenDoor event changes the door mesh rotation from closed to open using timeline and lerp as well as destroys the collision component as a way to prevent other interaction triggers

-> Player Controller function InteractionToExploration is called to swap back to full exploration

### Fail Feedback

-> The parent function receives the row name of data table InteractionFeedback from Lock Values

# Pickup

## Purpose

When interacted with add certain items from the pickup values array into the inventory via the Player Controller

## Key Variables

	Pickup Values - (Array of STR Interaction Values Pickup types)
	Niagara Asset - (Niagara System type)

## Type Specific Logic

### Execute Interaction

-> Change Game State to PickUpUI for pickup specific resolution

-> Player Controller function AddToInventory which takes the pickup values array

# Dialogue

## Purpose

Actor that provides the player with text based information and flavour. Multiple variations based on the [01_40_Dialogue](01_40_Dialogue.md) manager setup. May also execute special logic via [01_30_Handler](01_30_Handler.md)

## Key Variables

	Character Mesh - (Skeletal Mesh type)
	Anim Class - (Object type)
	Handler Values - (STR Interaction Values Handler type)
	Dialogue Values - (STR Interaction Values Dialogue type)

## Type Specific Logic

### Execute Interaction

-> Change Game State to DialogueUI for dialogue specific resolution

-> Player Controller function DialogueWidgetCreation is called

-> Dialogue manager is accessed via Game Instance to call function DialogueLineStart which takes the Dialogue ID from Dialogue Values

# Chest

## Purpose

A container that when interacted with will add certain items from the pickup values array into the inventory via the Player Controller

## Key Variables

	Chest Bottom Mesh - (Static Mesh type)
	Chest Top Mesh - (Static Mesh type)
	Closed Rotation - (Rotator type)
	Open Rotation - (Rotator type)
	Pickup Values - (Array of STR Interaction Values Pickup types)
	Lock Values - (STR Interaction Values lock type)

## Type Specific Logic

### Execute Interaction

-> Change Game State to PickUpUI for pickup specific resolution

-> Player Controller function AddToInventory which takes the pickup values array

### Fail Feedback

-> The parent function receives the row name of data table InteractionFeedback from Lock Values


