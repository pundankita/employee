# employee
package empcomp;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class employe {


  
 public static void main(String[] args) {
  List employees = new ArrayList();
  employees.add(new Employee("Ankita","Java Developer",21,"Active"));
  employees.add(new Employee("Priyanka","Network Admin",23,"Active"));
  

  System.out.println("Employes Name");
  Collections.sort(employees, new name());
  printEmployees(employees);
  System.out.println("Employes Age");
  Collections.sort(employees, new age());
  printEmployees(employees);

 }
 
 
 public static void printEmployees(List employees) {
for (Employee e : employees) {
   System.out.println("Name" + e.empname + " Dept " + e.empdept + "Age" +e.age
     + " State " + e.active);
  }
 }

}


class Employee {
 public String empname;
 public String empdept;
 public int age;
 public String active;

 public Employee(String empname,String empdept,int age, String active) {
  this.empname = empname;
  this.empdept = empdept;
  this.age = age;
  this.active = active;
 }

}

class age implements Comparator {
 public int compare(Employee emp1, Employee emp2) {
  int value = 0;
  if (emp1.age> emp2.age)
   value = 1;
  else if (emp1.age < emp2.age)
   value = -1;
  else if (emp1.age == emp2.age)
   value = 0;

  return value;
 }

@Override
public int compare(Object o1, Object o2) {
	// TODO Auto-generated method stub
	return 0;
}
}
// sort by name
class name implements Comparator {
 public int compare(Employee emp1, Employee emp2) {
  return emp1.empname.compareTo(emp2.empname);
 }

@Override
public int compare(Object o1, Object o2) {
	// TODO Auto-generated method stub
	return 0;
}
}
