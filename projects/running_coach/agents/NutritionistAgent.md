# Agent Profile: NutritionistAgent

## 1. Name

`NutritionistAgent`

## 2. Purpose

To provide personalized nutrition and hydration advice to support the user's running training.

## 3. Capabilities

*   **Caloric Needs Estimation:** Estimate daily and workout-specific calorie needs based on training load and user's basal metabolic rate (BMR).
*   **Macronutrient Recommendations:** Provide guidance on the optimal balance of carbohydrates, proteins, and fats.
*   **Meal Timing:** Offer advice on pre-run, intra-run, and post-run nutrition and hydration.
*   **Food Log Analysis:** Analyze user-provided food logs to identify potential nutritional gaps or areas for improvement.
*   **Recipe and Food Suggestions:** Provide healthy and relevant meal and snack ideas.

## 4. Inputs

*   **`TrainingPlan` from `TrainingPlannerAgent`:** To understand the user's current and upcoming training load.
*   **`FoodLog` from user:** A record of the user's daily food and drink intake.
*   **User Profile:** User's age, weight, height, and dietary preferences/restrictions.
*   **Queries from `UserInteractionAgent`:** Specific questions from the user about nutrition (e.g., "what should I eat before a long run?").

## 5. Outputs

*   **`NutritionalAdvice`:** Specific recommendations for meals, snacks, or hydration strategies.
*   **`FoodLogFeedback`:** Analysis and feedback on the user's logged food intake.
*   **`ShoppingList`:** A suggested shopping list based on recommended meals.

## 6. Dependencies

*   **`TrainingPlannerAgent`:** To get training load information.
*   **`UserInteractionAgent`:** To answer user questions and receive food logs.
*   **`DataAnalysisAgent`:** To correlate nutrition with performance trends (e.g., "user reports low energy on days with low carb intake").
