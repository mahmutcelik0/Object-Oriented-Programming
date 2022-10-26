## 3-) LISKOV'S Substitution Principle

***“Derived or child classes must be substitutable for their base or parent classes”. if class A is a subtype of class B, then we should be able to replace B with A without interrupting the behavior of the program.***

This principle ensures that any class that is the child of a parent class should be usable in place of its parent without any unexpected behavior.

You can understand it in a way that a farmer’s son should inherit farming skills from his father and should be able to replace his father if needed. If the son wants to become a farmer then he can replace his father but if he wants to become a cricketer then definitely the son can’t replace his father even though they both belong to the same family hierarchy.

One of the classic examples of this principle is a rectangle having four sides. A rectangle’s height can be any value and width can be any value. A square is a rectangle with equal width and height. So we can say that we can extend the properties of the rectangle class into square class. In order to do that you need to swap the child (square) class with parent (rectangle) class to fit the definition of a square having four equal sides but a derived class does not affect the behavior of the parent class so if you will do that it will violate the Liskov Substitution Principle.

It extends the open-close principle and also focuses on the behavior of a superclass and its subtypes. We should design the classes to preserve the property unless we have a strong reason to do otherwise

EXAMPLE:

**Student.java**

```java
public class Student   
{  
	private double height;  
	private double weight;  
	public void setHeight(double h)   
	{   
	height = h;   
	}  
	public void setWeight(double w)   
	{   
	weight= w;   
	}  
	...  
}  
public class StudentBMI extends Student  
	{  
	public void setHeight(double h)   
	{  
	super.setHeight(h);  
	super.setWeight(w);  
	}  
	public void setWeight(double h)   
	{  
	super.setHeight(h);  
	super.setWeight(w);  
	}  
}
```

The above classes doesn’t support the Liskov substitution principle because the StudentBMI class has extra constraints i.e. height and weight that must be the same. Therefore, the Student class (base class) cannot be replaced by StudentBMI class (derived class).
