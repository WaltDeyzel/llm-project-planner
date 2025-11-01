# Agent Profile: InjuryOrchestratorAgent

## 1. Name

`InjuryOrchestratorAgent`

## 2. Purpose

To act as a specialized sub-orchestrator responsible for coordinating all injury prevention and management activities within the AI Running Coach project. It manages injury risk assessment, provides preventative and rehabilitative routines, and integrates with the training schedule.

## 3. Capabilities

*   **Injury Risk Assessment:** Delegates to `InjuryPreventionAgent` to assess injury risks based on data and user reports.
*   **Routine Provision:** Coordinates with `InjuryPreventionAgent` to provide prehab and rehab routines.
*   **Training Plan Modification:** Works with `TrainingOrchestratorAgent` (via main `OrchestratorAgent`) to suggest modifications to the training plan when injury risk is high or an injury is present.
*   **User Reporting:** Processes user reports of pain or discomfort, passing them to `InjuryPreventionAgent` for analysis.
*   **Reporting to Main Orchestrator:** Provides summarized injury status and critical warnings back to the main `OrchestratorAgent`.

## 4. Inputs

*   **High-Level Injury Directives from `OrchestratorAgent`:** (e.g., "assess injury risk," "provide rehab exercises").
*   **`DailyJournal` (injury-related) from `UserInteractionAgent` (via `OrchestratorAgent`):** User reports of pain, soreness, or discomfort.
*   **`AnalysisSummary` and `DataAlerts` (injury-related) from `DataAnalysisAgent`:** Data indicating potential injury risks (e.g., sudden training load spikes).

## 5. Outputs

*   **Tasks for `InjuryPreventionAgent`:** Specific commands or queries for the specialist injury agent.
*   **`InjuryStatusReport` to `OrchestratorAgent`:** Summaries of injury risk, recommendations provided, or critical warnings.
*   **`RehabPlan`:** The generated rehabilitative or preventative routines (ultimately passed to `UserInteractionAgent` via `OrchestratorAgent`).

## 6. Dependencies

*   **`OrchestratorAgent`:** Receives directives from and reports to the main orchestrator.
*   **`InjuryPreventionAgent`:** For core injury prevention and management logic.
*   **`DataAnalysisAgent`:** For injury-relevant data insights.
*   **Shared Knowledge Base / Data Bus:** To access relevant user data and training plans.
