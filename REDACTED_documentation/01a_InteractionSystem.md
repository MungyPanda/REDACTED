
# Purpose

The interaction system manages communication between the player and world interaction objects. It detects valid interactables, validates interaction conditions, calls special interaction logic and routes execution to the appropriate interaction actor while keeping the logic modular and reusable. Since validation is separated from gameplay, the same pipeline can be reused for all interaction types
# Responsibilities

	Detect interactable objects
	Keep track of active interaction targets
	Maintain interaction priority
	Validate conditions
	Route execution to interaction actors
# Out of Scope

	Inventory logic
	Dialogue logic
	Battle logic
	Execution of interaction gameplay
# Key Variables

	CurrentInteractComponent (BP_GeneralInteractComponent type)
	ActiveComponents (Array of BP_GeneralInteractComponent type)
# Execution Flow
![IVFC](../Images/InteractionValidationFC.png)
![Light Version|95]([Images/InteractionValidationFC_light.png](https://github.com/MungyPanda/REDACTED/blob/main/Images/InteractionValidationFC_light.png))
# Communication Architecture

# Routing Logic

# Architecture Overview

# Dependencies

# Design Goals

# Notes
