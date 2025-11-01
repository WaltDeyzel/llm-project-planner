# Agent Profile: InjuryPreventionAgent

## 1. Name

`InjuryPreventionAgent`

## 2. Purpose

To help the user prevent and manage common running-related injuries by providing information, exercises, and proactive warnings.

## 3. Capabilities

*   **Injury Information:** Provide information about common running injuries (e.g., runner's knee, shin splints, plantar fasciitis), including symptoms and causes.
*   **Rehab and Prehab Routines:** Suggest mobility, stretching, and strengthening exercises to prevent injuries or aid in recovery.
*   **Risk Assessment:** Identify potential injury risks based on:
    *   Sudden increases in training load (from `DataAnalysisAgent`).
    *   User-reported pain or soreness (from `DailyJournal`).
*   **Modification Suggestions:** Recommend modifications to the training plan (e.g., reducing intensity, cross-training) when injury risk is high.

## 4. Inputs

*   **`AnalysisSummary` and `DataAlerts` from `DataAnalysisAgent`:** To identify sudden changes in training load.
*   **`DailyJournal` from user:** To get reports of pain, soreness, or discomfort.
*   **Queries from `UserInteractionAgent`:** Specific questions from the user about an injury.

## 5. Outputs

*   **`InjuryWarning`:** An alert sent to the `OrchestratorAgent` when a high injury risk is detected.
*   **`RehabPlan`:** A set of recommended exercises and actions for the user.
*   **`InformationalContent`:** Articles or videos about specific injuries.

## 6. Dependencies

*   **`DataAnalysisAgent`:** For data-driven risk assessment.
*   **`UserInteractionAgent`:** To communicate with the user.
*   **`TrainingPlannerAgent`:** To suggest modifications to the training plan.
*   **`StrengthCoachAgent`:** To request and coordinate rehab exercises.
