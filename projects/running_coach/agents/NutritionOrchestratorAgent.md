# Agent Profile: NutritionOrchestratorAgent

## 1. Name

`NutritionOrchestratorAgent`

## 2. Purpose

To act as a specialized sub-orchestrator responsible for coordinating all nutrition and hydration-related activities within the AI Running Coach project. It manages dietary recommendations, food log analysis, and hydration strategies for the user.

## 3. Capabilities

*   **Nutrition Advice Management:** Delegates to `NutritionistAgent` for generating dietary recommendations and analyzing food logs.
*   **Hydration Strategy:** Coordinates with `NutritionistAgent` to provide hydration advice based on training and environmental factors.
*   **Food Log Processing:** Receives and processes user-provided `FoodLog` data, passing it to `NutritionistAgent` for analysis and storing relevant information in the Shared Knowledge Base.
*   **Reporting to Main Orchestrator:** Provides summarized nutrition status and alerts (e.g., significant dietary imbalances) back to the main `OrchestratorAgent`.

## 4. Inputs

*   **High-Level Nutrition Directives from `OrchestratorAgent`:** (e.g., "provide post-run meal advice," "analyze weekly food log").
*   **`FoodLog` from `UserInteractionAgent` (via `OrchestratorAgent`):** User's daily food and drink intake.
*   **`TrainingPlan` (from Shared Knowledge Base):** To understand the user's current and upcoming training load.
*   **User Profile (from Shared Knowledge Base):** User's dietary preferences/restrictions.

## 5. Outputs

*   **Tasks for `NutritionistAgent`:** Specific commands or queries for the specialist nutrition agent.
*   **`NutritionalStatusReport` to `OrchestratorAgent`:** Summaries of dietary adherence, recommendations provided, or critical alerts.
*   **`NutritionalAdvice`:** The generated dietary recommendations (ultimately passed to `UserInteractionAgent` via `OrchestratorAgent`).

## 6. Dependencies

*   **`OrchestratorAgent`:** Receives directives from and reports to the main orchestrator.
*   **`NutritionistAgent`:** For core nutrition advice logic.
*   **Shared Knowledge Base / Data Bus:** To access `TrainingPlan` and `User Profile` data, and to store processed `FoodLog` data.
