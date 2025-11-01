# Agent Profile: OrchestratorAgent

## 1. Name

`OrchestratorAgent`

## 2. Purpose

To act as the central coordinator of the multi-agent system. It receives requests, delegates tasks to the appropriate specialist agents, and ensures a cohesive and intelligent response.

## 3. Capabilities

*   **High-Level Task Delegation:** Receive inputs from the `UserInteractionAgent` and `DataAnalysisAgent` and route them to the appropriate **Sub-Orchestrator** (e.g., `TrainingOrchestratorAgent`, `NutritionOrchestratorAgent`, `InjuryOrchestratorAgent`) or specialist agent if no sub-orchestrator exists for that domain.
*   **Global State Management:** Maintain a high-level understanding of the user's overall state, goals, and recent interactions across all domains.
*   **System-Wide Agent Coordination:** Synthesize information from multiple sub-orchestrators and specialist agents to fulfill complex, cross-domain requests. For example, to generate a daily briefing, it would query the `TrainingOrchestratorAgent` for the day's workout, the `NutritionOrchestratorAgent` for post-workout meal advice, and the `DataAnalysisAgent` for a summary of last night's sleep.
*   **Global Priority Management:** Handle system-wide alerts and warnings (e.g., `InjuryWarning`, `DataAlert`) and determine the appropriate course of action, potentially involving multiple sub-orchestrators.

### Decision/Delegation Criteria

The `OrchestratorAgent` uses the following criteria to decide which sub-orchestrator or specialist agent to delegate tasks to and how to prioritize actions:

1.  **Intent Recognition:** Analyze user requests (from `UserInteractionAgent`) to identify the primary intent (e.g., "get training plan," "ask nutrition question," "report injury").
2.  **Domain Mapping:** Map the identified intent to the appropriate sub-orchestrator (e.g., training intents -> `TrainingOrchestratorAgent`, nutrition intents -> `NutritionOrchestratorAgent`, injury intents -> `InjuryOrchestratorAgent`) or specialist agent if no sub-orchestrator exists for that domain.
3.  **Contextual Relevance:** Consider the current user state, recent activities, and goals to determine the most relevant sub-orchestrator or specialist agent.
4.  **Data Availability:** Check if necessary data is available (e.g., from `DataAnalysisAgent` or Shared Knowledge Base) before delegating a task that requires it.
5.  **Alert Priority:** Prioritize critical alerts (e.g., `InjuryWarning`, `DataAlert` indicating overtraining) over routine requests, routing them to the relevant sub-orchestrator or specialist.
6.  **Sequential Dependencies:** Understand and manage the order of operations when a request requires input from multiple sub-orchestrators or agents in sequence.
7.  **Load Balancing (Future Consideration):** In a high-volume scenario, consider distributing tasks among multiple instances of sub-orchestrators or specialist agents.

## 4. Inputs

*   **Formatted User Requests from `UserInteractionAgent`:** The primary driver of action.
*   **`AnalysisSummary` and `DataAlerts` from `DataAnalysisAgent`:** Proactive triggers for action.
*   **Outputs from all other agents:** Information to be synthesized or passed to other agents.

## 5. Outputs

*   **Tasks for specialist agents:** Specific commands or queries for each agent (e.g., "`TrainingPlannerAgent`, generate a 12-week marathon plan").
*   **Synthesized responses:** Cohesive answers to be sent to the `UserInteractionAgent` for presentation to the user.

## 6. Dependencies

*   This agent is the central hub and is connected to all other agents in the system.
