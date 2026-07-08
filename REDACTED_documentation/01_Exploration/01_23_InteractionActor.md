
# Purpose

General Actor contains overlap events that are needed to initiate the interaction [01_22_ValidationFunctions&Events](01_22_ValidationFunctions&Events.md) which continues to validation [01_21_InteractionValidation](01_21_InteractionValidation.md) as well as functions that are overridden by children to achieve specific gameplay logic based on the type [01_24_InteractionTypes](01_24_InteractionTypes.md) where communication with other systems might be required. Some gameplay system also require the active interactable actor's values and some change them.

# Functions

ExecuteInteraction function is fully overridden by the child and the parent only provides references

FailFeedback function has an input Feedback ID name which is a row name of a data table FeedbackInteraction that is passed by the child to the parent function where it is then used to call a Player Controller function FeedbackWidgetLogic that shows the text on screen

# Responsibilities

	Player overlap
	Execute specific gameplay logic
	Pass values to other systems
	Provide children's values
	Adjust childnren's values

# Dependencies

	Player Controller
	Interact Component
	Other gameplay systems
# Design Goals

	Modular
	Reusable
	Easy to extend
# Notes

This actor is basically used as a base for other types, which can be easily edited and reused. The overlap events are unconditionally present in each and were first set up to consider only one overlapping interaction actor, which led to some difficulties when two of them were overlapping. This was resolved by creating a new array of interaction components in the Player Controller. Then a lot of the logic that was previously present in the component was moved to the actor so that the children could override them and each create their own gameplay logic. If later other references are required for the children to use they can be added accessed via the parent functions. This actor was one of the main features I wanted to focus on as soon as possible because from the start, creating specialized actors for various interactions was not an option.