# Agent Profile: OrchestratorAgent

## 1. Name

`OrchestratorAgent`

## 2. Purpose

To act as the central coordinator of the multi-agent system. It receives requests, delegates tasks to the appropriate specialist agents, and ensures a cohesive and intelligent response.

## 3. Capabilities

*   **Task Delegation:** Receive inputs from the `UserInteractionAgent` and `DataAnalysisAgent` and route them to the correct specialist agent (e.g., a nutrition question goes to the `NutritionistAgent`).
*   **State Management:** Maintain a high-level understanding of the user's current state, goals, and recent interactions.
*   **Agent Coordination:** Synthesize information from multiple agents to fulfill complex requests. For example, to generate a daily briefing, it would query the `TrainingPlannerAgent` for the day's workout, the `NutritionistAgent` for post-workout meal advice, and the `DataAnalysisAgent` for a summary of last night's sleep.
*   **Priority Management:** Handle alerts and warnings (e.g., `InjuryWarning`, `DataAlert`) and determine the appropriate course of action.

## 4. Inputs

*   **Formatted User Requests from `UserInteractionAgent`:** The primary driver of action.
*   **`AnalysisSummary` and `DataAlerts` from `DataAnalysisAgent`:** Proactive triggers for action.
*   **Outputs from all other agents:** Information to be synthesized or passed to other agents.

## 5. Outputs

*   **Tasks for specialist agents:** Specific commands or queries for each agent (e.g., "`TrainingPlannerAgent`, generate a 12-week marathon plan").
*   **Synthesized responses:** Cohesive answers to be sent to the `UserInteractionAgent` for presentation to the user.

## 6. Dependencies

*   This agent is the central hub and is connected to all other agents in the system.
