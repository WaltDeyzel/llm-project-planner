# Agent Profile: StrengthCoachAgent

## 1. Name

`StrengthCoachAgent`

## 2. Purpose

To recommend strength training workouts that complement the user's running plan, with a focus on improving running economy, preventing injuries, and building overall strength.

## 3. Capabilities

*   **Workout Generation:** Create personalized strength training routines based on the user's fitness level, available equipment, and the phase of their running plan.
*   **Exercise Library:** Maintain a library of exercises with instructions, images, or videos.
*   **Workout Scheduling:** Suggest optimal days and times for strength training to avoid conflicts with key running workouts.
*   **Form and Technique Guidance:** Provide tips on proper form for recommended exercises.

## 4. Inputs

*   **`TrainingPlan` from `TrainingPlannerAgent`:** To understand the user's running schedule and intensity.
*   **User Profile:** User's experience with strength training, available equipment (e.g., dumbbells, resistance bands, bodyweight only).
*   **Injury Reports from `InjuryPreventionAgent`:** To modify routines to avoid aggravating existing injuries.

## 5. Outputs

*   **`StrengthWorkout`:** A structured data object (e.g., JSON) containing a list of exercises, sets, reps, and rest periods.
*   **`ExerciseDemonstration`:** Links or embedded content showing how to perform an exercise.

## 6. Dependencies

*   **`TrainingPlannerAgent`:** To align strength workouts with the running plan.
*   **`InjuryPreventionAgent`:** To get information about the user's injuries.
*   **`UserInteractionAgent`:** To present the workouts to the user.
