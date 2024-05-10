# Personal-Finance-Manager
class PersonalFinanceManager:
    def __init__(self):
        self.income = 0
        self.expenses = 0
        self.savings_goal = 0
        self.budget = {}

    def add_income(self, amount):
        self.income += amount

    def add_expense(self, category, amount):
        if category not in self.budget:
            self.budget[category] = 0
        self.budget[category] += amount
        self.expenses += amount

    def set_savings_goal(self, amount):
        self.savings_goal = amount

    def view_summary(self):
        print("Income: ${}".format(self.income))
        print("Expenses: ${}".format(self.expenses))
        print("Savings Goal: ${}".format(self.savings_goal))
        print("Budget:")
        for category, amount in self.budget.items():
            print(" - {}: ${}".format(category, amount))
            
if __name__ == "__main__":
    finance_manager = PersonalFinanceManager()

    finance_manager.add_income(3000)
    finance_manager.add_expense("Food", 200)
    finance_manager.add_expense("Rent", 1000)
    finance_manager.add_expense("Transportation", 150)
    finance_manager.set_savings_goal(1000)

    finance_manager.view_summary()
