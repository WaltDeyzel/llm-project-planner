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

## 5. High-Level Orchestration

1.  User provides their goal (e.g., "run a half-marathon in 3 months").
2.  `OrchestratorAgent` tasks the `TrainingPlannerAgent` to create a plan.
3.  User logs their runs, and Garmin data is synced.
4.  `DataAnalysisAgent` processes the new data and flags any interesting trends or deviations.
5.  User asks, "What should I eat after my long run?"
6.  `OrchestratorAgent` routes the query to the `NutritionistAgent`.
7.  `NutritionistAgent` provides a recommendation based on the user's recent activity.

This is a starting point. We can now begin to flesh out each of these sections in more detail. What would you like to focus on first? For example, we could start by defining the `TrainingPlannerAgent` in more detail.
