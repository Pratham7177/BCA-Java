1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-

ANSWER CODE
class Employee:
    def __init__(self, name, eid, basic_salary):
        self.name = name
        self.eid = eid
        self.basic_salary = basic_salary

    def calculate_gross_salary(self):
        hra = 0.20 * self.basic_salary
        da = 0.25 * self.basic_salary
        ma = 300
        gross_salary = self.basic_salary + hra + da + ma
        return gross_salary

employees = [
    Employee("John", 101, 25000),
    Employee("Alice", 102, 30000),
    Employee("Nancy", 103, 18000),
    Employee("Nick", 104, 22000),
    Employee("Neo", 105, 28000),
    Employee("Nina", 106, 24000),
    Employee("Nathan", 107, 20000)
]

print("Employees whose name starts with 'N':")
for emp in employees:
    if emp.name.lower().startswith('n'):
        print("Name:", emp.name, "Gross Salary:", emp.calculate_gross_salary())

print("\nEmployee with Eid 107:")
for emp in employees:
    if emp.eid == 107:
        print("Eid:", emp.eid, "Gross Salary:", emp.calculate_gross_salary())

count = 0
for emp in employees:
    if emp.basic_salary > 20000:
        count += 1

print("\nTotal number of employees with salary more than 20000/-:", count)
