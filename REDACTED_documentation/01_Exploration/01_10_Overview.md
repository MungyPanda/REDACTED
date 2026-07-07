# Purpose

Handles all non-combat gameplay while the player freely moves around and explores the world. Including player movement, interaction with world objects, transitioning into and communicating with specialized gameplay systems.

These gameplay system base their flow on data passed to them from either the [01_20_InteractionSystem](01_20_InteractionSystem.md) or via the Player Controller. Loose coupling is preferred so that references are used only when required.

# Responsibilities

Character movement
World interaction detection and initiation [01_20_InteractionSystem](01_20_InteractionSystem.md)
Battle initiation
Transition to specialized systems

	Inventory
	Dialogue
	Menus
	Shops (TBD)
	Cutscenes (TBD)

# Architecture

State driven gameplay
Data driven interactions
Specialized systems communicating through managers
Player Controller

# Main Systems

	Movement
	Interaction
	Dialogue
	Inventory
	Menu
	Handler

# Design Goals

	Modular
	Reusable
	Data driven
	Easy to extend
	Designer Friendly

# Future Improvements

Reduce coupling between gameplay systems
Replace communication with generic interfaces where necessary
Improve toolset for designers
