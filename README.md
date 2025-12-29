# python-dictionary
employees = {
    "Ravi": 45000,
    "Anita": 72000,
    "Karthik": 52000,
    "Priya": 38000,
    "Suresh": 61000
}
print("Original Employee Salaries:")
print(employees)
updated_salaries = dict(
    map(lambda item: (item[0], int(item[1] * 1.10)), employees.items())
)
print("\nSalaries after 10% hike:")
print(updated_salaries)
eligible_employees = dict(
    filter(lambda item: item[1] >= 50000, updated_salaries.items())
)

print("\nEmployees with salary >= 50,000:")
print(eligible_employees)
total_salary = reduce(lambda x, y: x + y, updated_salaries.values())

print("\nTotal Salary Expense:")
print(total_salary)

def deposit(balance, amount):
    return balance + amount

def withdraw(balance, amount):
    if amount <= balance:
        return balance - amount
    else:
        print("Insufficient Balance")
        return balance

def display(acc_no, name, balance):
    print("Account No :", acc_no)
    print("Name       :", name)
    print("Balance    :", balance)

import bank_module

acc_no = 1001
name = "Suresh"
balance = 25000

balance = bank_module.deposit(balance, 5000)
balance = bank_module.withdraw(balance, 3000)

bank_module.display(acc_no, name, balance)
