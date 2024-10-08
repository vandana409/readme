# readme
test papers
def add_employee(salaries):
    name = input("Enter employee name: ")
    salary = float(input("Enter employee salary: "))
    salaries[name] = salary

def calculate_average(salaries):
    if not salaries:
        return 0
    return sum(salaries.values()) / len(salaries)

def find_high_low(salaries):
    if not salaries:
        return None, None
    highest = max(salaries, key=salaries.get)
    lowest = min(salaries, key=salaries.get)
    return highest, lowest

def main():
    salaries = {}
    
    while True:
        add_employee(salaries)
        cont = input("Do you want to add another employee? (yes/no): ").strip().lower()
        if cont != 'yes':
            break

    avg_salary = calculate_average(salaries)
    highest, lowest = find_high_low(salaries)
    
    print("\nEmployee Salaries:")
    for name, salary in salaries.items():
        print(f"{name}: ${salary:.2f}")
    
    print(f"\nAverage Salary: ${avg_salary:.2f}")
    print(f"Highest Salary: {highest} - ${salaries[highest]:.2f}")
    print(f"Lowest Salary: {lowest} - ${salaries[lowest]:.2f}")

if __name__ == "__main__":
    main()
