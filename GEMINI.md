# GEMINI.md: Project Planner

## Directory Overview

This directory serves as a workspace for planning and detailing LLM (Large Language Model) and agent-based software projects. The primary goal is to design the architecture, define the agents, and specify the data models for various project ideas, rather than implementing the projects themselves.

The structure is designed to keep project plans organized and to manage a library of reusable, common agent profiles.

## Key Files and Structure

*   `projects/`: This is the main directory containing individual subdirectories for each project idea.
    *   `projects/<project_name>/`: Each project has its own folder.
    *   `projects/<project_name>/README.md`: The central planning document for a project, outlining its goals, features, agent architecture, and data requirements.
    *   `projects/<project_name>/agents/`: Contains detailed profiles for agents that are *specific* to that project.
*   `common_agents/`: This directory is intended to hold profiles for agents that are generic and can be reused across multiple projects.
    *   `CritiqueAgent.md`: An agent designed to critique individual agent profiles.
    *   `GitAgent.md`: An agent designed to streamline Git operations.
    *   `ArchitectureAgent.md`: An agent designed to critique the overall multi-agent system architecture of a project.
*   `GEMINI.md`: This file, providing context for our interactions.

## Usage

The primary workflow involves:

1.  **Brainstorming a Project:** We start by discussing a new project idea.
2.  **Creating a Project Plan:** I create a new directory in `projects/` and populate a `README.md` with the project's high-level details.
3.  **Defining Agents:** We flesh out the roles of different agents, creating detailed profiles for them in the appropriate `agents/` directory (either project-specific or common). This now includes the concept of **sub-orchestrators** to manage complexity and distribute coordination load within a project.
4.  **Architectural Review:** We use the `ArchitectureAgent` to assess the overall multi-agent system design, and the `CritiqueAgent` to refine individual agent profiles.
5.  **Detailing Data and Orchestration:** We specify the data schemas and the high-level interaction patterns between the agents, including the hierarchical orchestration with sub-orchestrators.

My role is to act as the "Planner Agent," assisting in the creation and organization of all these planning documents.
