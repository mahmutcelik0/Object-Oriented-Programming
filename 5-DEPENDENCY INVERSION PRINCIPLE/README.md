## 5-) Dependency Inversion Principle
***High-level modules should not depend on the low-level module but both should depend on the abstraction. Because the abstraction does not depend on detail but the detail depends on abstraction***

- High-level modules/classes should not depend on low-level modules/classes. Both should depend upon abstractions.
- Abstractions should not depend upon details. Details should depend upon abstractions.

The above lines simply state that if a high module or class will be dependent more on low-level modules or class then your code would have tight coupling and if you will try to make a change in one class it can break another class which is risky at the production level. So always try to make classes loosely coupled as much as you can and you can achieve this through *abstraction*. The main motive of this principle is decoupling the dependencies so if class A changes the class B doesn’t need to care or know about the changes.You can consider the real-life example of a TV remote battery. Your remote needs a battery but it’s not dependent on the battery brand. You can use any XYZ brand that you want and it will work. So we can say that the TV remote is loosely coupled with the brand name. Dependency Inversion makes your code more reusable.

EXAMPLE:

()

```java
public class WindowsMachine  
{  
//functionality   
}
```

It is worth, if we have not keyboard and mouse to work on Windows. To solve this problem, we create a constructor of the class and add the instances of the keyboard and monitor. After adding the instances, the class looks like the following:

```java
public class WindowsMachine  
{  
public final keyboard;  
public final monitor;  
public WindowsMachine()  
{  
monitor = new monitor();  //instance of monitor class  
keyboard = new keyboard(); //instance of keyboard class  
}  
}
```

Now we can work on the Windows machine with the help of a keyboard and mouse. But we still face the problem. Because we have tightly coupled the three classes together by using the new keyword. It is hard o test the class windows machine.

To make the code loosely coupled, we decouple the WindowsMachine from the keyboard by using the Keyboard interface and this keyword.

**Keyboard.java**

```java
public interface Keyboard   
{   
//functionality  
}
```

**WindowsMachine.java**

```java
public class WindowsMachine  
{  
private final Keyboard keyboard;  
private final Monitor monitor;  
public WindowsMachine(Keyboard keyboard, Monitor monitor)   
{  
this.keyboard = keyboard;  
this.monitor = monitor;  
}  
}
```

In the above code, we have used the dependency injection to add the keyboard dependency in the WindowsMachine class. Therefore, we have decoupled the classes.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fd4851ea-2d36-4fd3-b430-559877351c21/Untitled.png)
