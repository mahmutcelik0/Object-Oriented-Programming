## 2-) Open Closed Principle

*the module should be open for extension but closed for modification*

This principle states that “*software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification*” which means 

***you should be able to extend a class behavior, without modifying it.***

Suppose developer A needs to release an update for a library or framework and developer B wants some modification or add some feature on that then developer B is allowed to extend the existing class created by developer A but developer B is not supposed to modify the class directly. Using this principle separates the existing code from the modified code so it provides better stability, maintainability and minimizes changes as in your code.

Suppose, **VehicleInfo** is a class and it has the method **vehicleNumber()** that returns the vehicle number.

**VehicleInfo.java**

```java
public class VehicleInfo  
{  
	public double vehicleNumber(Vehicle vcl)   
	{  
		if (vcl instanceof Car)   
		{  
			return vcl.getNumber();  
		if (vcl instanceof Bike)   
		{  
			return vcl.getNumber();  
		}  
}
```

If we want to add another subclass named Truck, simply, we add one more if statement that violates the open-closed principle. The only way to add the subclass and achieve the goal of principle by overriding the **vehicleNumber()** method, as we have shown below.

**VehicleInfo.java**

```java
public class VehicleInfo   
{  
	public double vehicleNumber()   
	{  
	//functionality   
	}  
	}  
	public class Car extends VehicleInfo   
	{  
		public double vehicleNumber()   
		{  
		return this.getValue();  
		}  
		public class Car extends Truck   
		{  
		public double vehicleNumber()   
		{  
		return this.getValue();  
}
```

Similarly, we can add more vehicles by making another subclass extending from the vehicle class. the approach would not affect the existing application.
