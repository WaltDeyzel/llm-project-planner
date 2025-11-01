# Agent Profile: TrainingPlannerAgent

## 1. Name

`TrainingPlannerAgent`

## 2. Purpose

To create, manage, and dynamically adapt personalized running training plans based on the user's goals, performance data, and subjective feedback.

## 3. Capabilities

*   **Plan Generation:** Generate a multi-week training plan based on a target race distance (e.g., 5k, 10k, half-marathon, marathon) and a target completion time or goal (e.g., "finish the race," "run under 2 hours").
*   **Plan Adaptation:** Modify the training plan based on:
    *   Missed or modified workouts.
    *   User's subjective feedback (e.g., feeling fatigued, high energy).
    *   Performance trends identified by the `DataAnalysisAgent`.
*   **Workout Specification:** Define the specifics for each workout, including:
    *   Type (e.g., easy run, long run, interval training, tempo run).
    *   Duration or distance.
    *   Pace targets (e.g., heart rate zone, pace range).
*   **Taper and Recovery:** Incorporate taper periods before races and recovery weeks into the training plan.

## 4. Inputs

*   **User Goals:** Target race distance, goal time, race date.
*   **User Fitness Level:** Current weekly mileage, recent race times, self-assessed fitness level.
*   **Analysis from `DataAnalysisAgent`:** Summaries of recent performance, fatigue warnings, progress trends.
*   **Feedback from `UserInteractionAgent`:** User's subjective feelings, reports of missed workouts.

## 5. Outputs

*   **`TrainingPlan`:** A structured data object (e.g., JSON) representing the full training plan, including daily workouts.
*   **`WorkoutModification`:** A notification and updated workout details when the plan is adjusted.
*   **Queries to other agents:** Requests for information (e.g., asking the `DataAnalysisAgent` for the user's current 5k PR).

## 6. Dependencies

*   **`DataAnalysisAgent`:** To receive performance data and analysis.
*   **`UserInteractionAgent`:** To receive user feedback and goals.
*   **`OrchestratorAgent`:** To receive high-level directives and report plan creation/modification.
