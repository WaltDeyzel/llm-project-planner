# Project: AI Running Coach

## 1. Project Goal

To create a personalized AI-powered running coach that assists users with their training, nutrition, and overall progress. The system will analyze data from various sources to provide holistic and actionable advice.

## 2. Key Features

*   **Personalized Training Plans:** Generate and adapt running plans based on user goals, fitness level, and progress.
*   **Nutrition Guidance:** Provide dietary recommendations based on training load and user-provided food logs.
*   **Strength Training Integration:** Suggest strength workouts that complement the running plan.
*   **Progress Tracking & Analysis:** Ingest and analyze data from Garmin, user logs, and other sources to track progress and identify trends.
*   **Injury Prevention & Management:** Offer advice on preventing and managing common running-related injuries.
*   **Natural Language Interface:** Allow users to interact with the coach through a conversational interface.

## 3. Potential Agents

We can envision a multi-agent system to handle the different aspects of this project. Here is a potential breakdown:

*   **`TrainingPlannerAgent`:** Responsible for creating and adjusting running schedules.
*   **`NutritionistAgent`:** Provides advice on diet and hydration.
*   **`StrengthCoachAgent`:** Recommends strength training exercises.
*   **`DataAnalysisAgent`:** Ingests and analyzes all incoming data (Garmin, user logs).
*   **`UserInteractionAgent`:** Manages the conversational interface with the user.
*   **`InjuryPreventionAgent`:** Provides information and exercises for injury prevention.
*   **`OrchestratorAgent`:** Coordinates the other agents and manages the overall user experience.

## 4. Data Sources & Model

*   **Garmin Data:**
    *   Running activities (distance, pace, heart rate, cadence, etc.).
    *   Sleep data.
    *   Stress levels.
    *   *Action Item:* Research and document the process for Garmin data integration (e.g., via API).
*   **User-Provided Data:**
    *   **`DailyJournal`:** A simple log for the user to record:
        *   Subjective feeling (energy levels, mood).
        *   Muscle soreness.
        *   Injury reports (pain level, location).
    *   **`FoodLog`:** A log of meals and snacks.
*   **Data Schema:** *Action Item: Define a structured format (e.g., JSON schema) for storing this data.*
*   **Shared Knowledge Base / Data Bus:** *Action Item: Define a mechanism for agents to access and share information beyond direct input/output passing, such as a message queue or a centralized datastore.*
*   **Cross-Agent Data Models:** *Action Item: Explicitly document clear data models for all information passed between agents (e.g., `TrainingPlan` object structure, `NutritionalAdvice` format).*

## 5. High-Level Orchestration

To manage complexity and distribute the coordination load, we will introduce the concept of **Sub-Orchestrators**. The main `OrchestratorAgent` will delegate high-level tasks to these specialized sub-orchestrators, which will then manage their respective domains.

1.  User provides their goal (e.g., "run a half-marathon in 3 months").
2.  Main `OrchestratorAgent` tasks a relevant **Sub-Orchestrator** (e.g., `TrainingOrchestratorAgent`, `NutritionOrchestratorAgent`, `InjuryOrchestratorAgent`) to manage the request.
3.  User logs their runs, and Garmin data is synced. This data is processed by `DataAnalysisAgent` and stored in the Shared Knowledge Base.
4.  `DataAnalysisAgent` processes new data from the Shared Knowledge Base and flags any interesting trends or deviations, updating the Shared Knowledge Base.
5.  User asks, "What should I eat after my long run?"
6.  Main `OrchestratorAgent` routes the query to the `NutritionOrchestratorAgent`, providing relevant context from the Shared Knowledge Base.
7.  `NutritionOrchestratorAgent` delegates to `NutritionistAgent` to provide a recommendation based on the user's recent activity and data from the Shared Knowledge Base.

This refined orchestration aims to distribute the coordination load and enhance scalability. We have now defined `TrainingOrchestratorAgent`, `NutritionOrchestratorAgent`, and `InjuryOrchestratorAgent` as examples of sub-orchestrators.
