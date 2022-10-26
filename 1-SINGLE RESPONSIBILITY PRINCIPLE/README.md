## 1-) Single Responsibility Principle

***every Java class must perform a single functionality***

This principle states that “*a class should have only one reason to change*” which means every class should have a single responsibility or single job or single purpose. Take the example of developing software. The task is divided into different members doing different things as front-end designers do design, the tester does testing and backend developer takes care of backend development part then we can say that everyone has a single job or responsibility.

Most of the time it happens that when programmers have to add features or new behavior they implement everything into the existing class which is completely wrong. It makes their code lengthy, complex and consumes time when later something needs to be modified. Use *layers* in your application and break God classes into smaller classes or modules.

EXAMPLE:

Suppose, **Student** is a class having three methods namely **printDetails(), calculatePercentage(),** and **addStudent().** Hence, the Student class has three responsibilities to print the details of students, calculate percentages, and database. By using the single responsibility principle, we can separate these functionalities into three separate classes to fulfill the goal of the principle.

Student. java **→ Without Single Responsibility principle** 

```java
public class Student  
{  
	public void printDetails();  
	{  
	//functionality of the method  
	}  
	public void calculatePercentage();  
	{  
	//functionality of the method  
	}  
	public void addStudent();  
	{  
	//functionality of the method  
	}  
}
```

The above code snippet violates the single responsibility principle. To achieve the goal of the principle, we should implement a separate class that performs a single functionality only.

Student. java → With **Single Responsibility** principle

```java
public class Student  
{  
	public void addStudent();  
	{  
	//functionality of the method  
	}  
}
```

**PrintStudentDetails.java**

```java
public class PrintStudentDetails  
{  
	public void printDetails();  
	{  
	//functionality of the method  
	}  
}
```

**Percentage.java**

```java
public class Percentage  
{  
	public void calculatePercentage();  
	{  
	//functionality of the method  
	}  
}
```

Hence, we have achieved the goal of the single responsibility principle by separating the functionality into three separate classes.
