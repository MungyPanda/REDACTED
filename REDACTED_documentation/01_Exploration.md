# Purpose

Handles all non-combat gameplay while the player freely moves around and explores the world. Including player movement, interaction with world objects, transitioning into specialized gameplay systems
# Responsibilities

Character movement
World interaction detection and initiation [01a_InteractionSystem](01a_InteractionSystem.md)
Battle initiation
Transition to specialized systems

	Inventory
	Dialogue
	Menus
	Shops (TBD)
	Cutscenes (TBD)
# Out of Scope

Exploration communicates and delegates responsibilities to dedicated systems

	Inventory management
	Dialogue management
	Battle Logic
	Save/Load system
# Architecture

State driven gameplay
Data drive interactions
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