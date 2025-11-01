# Agent Profile: UserInteractionAgent

## 1. Name

`UserInteractionAgent`

## 2. Purpose

To serve as the primary interface between the user and the AI coaching system, managing the conversational flow and translating user requests into actionable tasks for other agents.

## 3. Capabilities

*   **Natural Language Understanding (NLU):** Interpret user messages, questions, and commands.
*   **Dialog Management:** Maintain the context of the conversation and manage the back-and-forth interaction.
*   **Information Presentation:** Present information from other agents to the user in a clear and understandable way.
*   **Data Collection:** Prompt the user for subjective feedback (e.g., `DailyJournal` entries) and log their responses.
*   **Request Routing:** Route user requests to the appropriate agent via the `OrchestratorAgent`.

## 4. Inputs

*   **User Messages:** Text or voice input from the user.
*   **Outputs from other agents:** Information to be presented to the user (e.g., `TrainingPlan`, `NutritionalAdvice`).

## 5. Outputs

*   **Formatted User Requests:** Structured requests sent to the `OrchestratorAgent` (e.g., `{ intent: 'get_workout', date: 'today' }`).
*   **User-Facing Messages:** Text, charts, and other UI elements to display to the user.
*   **`DailyJournal` and `FoodLog` entries:** User-provided data to be stored.

## 6. Dependencies

*   **`OrchestratorAgent`:** To send user requests and receive information to present.
*   All other agents (indirectly) as it is the conduit for information flow to the user.
