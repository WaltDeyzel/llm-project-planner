# Agent Profile: TrainingOrchestratorAgent

## 1. Name

`TrainingOrchestratorAgent`

## 2. Purpose

To act as a specialized sub-orchestrator responsible for coordinating all training-related activities within the AI Running Coach project. It manages the lifecycle of training plans, strength workouts, and injury prevention strategies for the user.

## 3. Capabilities

*   **Training Plan Management:** Delegates to `TrainingPlannerAgent` for plan generation and adaptation.
*   **Strength Workout Integration:** Coordinates with `StrengthCoachAgent` to schedule and provide strength training routines.
*   **Injury Prevention Oversight:** Works with `InjuryPreventionAgent` to integrate injury risk assessments and preventative measures into the training schedule.
*   **Progress Monitoring (Training Focus):** Receives training-specific insights from `DataAnalysisAgent` and uses them to inform training adjustments.
*   **Reporting to Main Orchestrator:** Provides summarized training status and alerts back to the main `OrchestratorAgent`.

## 4. Inputs

*   **High-Level Training Directives from `OrchestratorAgent`:** (e.g., "create marathon plan," "adjust weekly mileage").
*   **`AnalysisSummary` and `DataAlerts` (training-specific) from `DataAnalysisAgent`:** Performance data relevant to training.
*   **User Feedback (training-specific) from `UserInteractionAgent` (via `OrchestratorAgent`):** Reports on workouts, fatigue, etc.

## 5. Outputs

*   **Tasks for Specialist Training Agents:** (e.g., to `TrainingPlannerAgent`, `StrengthCoachAgent`, `InjuryPreventionAgent`).
*   **`TrainingStatusReport` to `OrchestratorAgent`:** Summaries of training progress, plan changes, or critical alerts.
*   **`TrainingPlan`:** The generated or adapted training plan (ultimately passed to `UserInteractionAgent` via `OrchestratorAgent`).

## 6. Dependencies

*   **`OrchestratorAgent`:** Receives directives from and reports to the main orchestrator.
*   **`TrainingPlannerAgent`:** For core training plan logic.
*   **`StrengthCoachAgent`:** For strength training integration.
*   **`InjuryPreventionAgent`:** For injury-related assessments and recommendations.
*   **`DataAnalysisAgent`:** For training-relevant data insights.
