# AI-driven-Personalized-Nutrition-Plan
Créez une application de nutrition personnalisée alimentée par l'IA qui génère des plans de repas et des recommandations en fonction des besoins de santé et des préférences alimentaires des utilisateurs.
class PersonalizedNutritionPlan:
    def __init__(self):
        self.user_preferences = {
            'health_needs': [],
            'food_preferences': [],
            'diet_restrictions': []
        }
        self.meal_plans = {
            'low_carb': ['Grilled salmon with avocado salad', 'Chicken Caesar salad without croutons'],
            'high_protein': ['Beef stir-fry with broccoli', 'Quinoa and black bean salad'],
            'vegetarian': ['Stuffed bell peppers', 'Lentil soup with spinach']
        }

    def get_user_preferences(self):
        print("Please enter your health needs (e.g., weight loss, muscle gain): ")
        self.user_preferences['health_needs'] = input().split(', ')

        print("Please enter your food preferences (e.g., vegan, seafood): ")
        self.user_preferences['food_preferences'] = input().split(', ')

        print("Please enter any diet restrictions (e.g., gluten-free, nut-free): ")
        self.user_preferences['diet_restrictions'] = input().split(', ')

    def generate_nutrition_plan(self):
        # Simplified logic to select meal plan
        if 'weight loss' in self.user_preferences['health_needs']:
            selected_plan = 'low_carb'
        elif 'muscle gain' in self.user_preferences['health_needs']:
            selected_plan = 'high_protein'
        else:
            selected_plan = 'vegetarian'

        # Filtering based on food preferences and restrictions could be added here
        return self.meal_plans[selected_plan]

    def display_meal_plan(self):
        self.get_user_preferences()
        plan = self.generate_nutrition_plan()
        print("\nBased on your inputs, here is your personalized nutrition plan:")
        for meal in plan:
            print(f"- {meal}")

if __name__ == "__main__":
    nutrition_plan_app = PersonalizedNutritionPlan()
    nutrition_plan_app.display_meal_plan()
