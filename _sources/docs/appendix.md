# Appendix

#### Google Python Style Docstring Examples 

```class Employee: 
"""Class to represent an employee. 
Attributes: 
first_name: str 
First name of employee 
last_name: str 
Last name of employee 
id_number: int 
Employee identification number. Must be unique. 
date_hired: str 
The date the employee was hired 
pto: int|float 
The current balance of paid time off for the employee 
position: str 
The employee's title or role in the company 
manager_id: int 
The employee ID of the manager who supervises the employee 
""" 
def __init__( 
self, 
11
first_name: str, 
last_name: str, 
id_number: int, 
date_hired: str = None, 
pto: float = None, 
position: str = None, 
manager_id: int = None, 
): 
self.first_name = first_name 
self.last_name = last_name 
self.name = f"{first_name} {last_name}" 
self.id = id_number 
self.date_hired = date_hired 
self.pto = pto 
self.position = position 
self.manager_id = manager_id 
def set_manager(self, manager_id: int): 
"""Change the employee's manager by setting a new manager ID. 
Note that this method does not check for existing ids and 
it should actually find the max id and increment by one. 
Args: 
manager_id: int 
""" 
# TODO: find max id and assign next integer instead 
if not isinstance(manager_id, int): 
raise ValueError('Manager id must be an integer') 
else: 
self.manager_id = manager_id 
def summary(self): 
"""Return a summary of the employee's information. 
Returns: 
String of employee information. 
""" 
out = f'{self.name}, {self.id}, {self.date_hired}, {self.pto}, {self.position}, {self.manager_id}' 
return out 
```


#### Issue Template Sample Listing Tests as Part of the Task 

```{image} ../images/tests_as_part_of_issue.png
```
