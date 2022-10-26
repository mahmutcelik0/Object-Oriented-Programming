## 4-) Interface Segregation Principle
***do not force any client to implement an interface which is irrelevant to them***

***main goal is to focus on avoiding fat interface and give preference to many small client-specific interfaces***

This principle is the first principle that applies to Interfaces instead of classes in SOLID and it is similar to the single responsibility principle. It states that “*do not force any client to implement an interface which is irrelevant to them”.* 

Here your main goal is to focus on avoiding fat interface and give preference to many small client-specific interfaces. You should prefer many client interfaces rather than one general interface and each interface should have a specific responsibility.

Suppose if you enter a restaurant and you are pure vegetarian. The waiter in that restaurant gave you the menu card which includes vegetarian items, non-vegetarian items, drinks, and sweets. In this case, as a customer, you should have a menu card which includes only vegetarian items, not everything which you don’t eat in your food. Here the menu should be different for different types of customers. The common or general menu card for everyone can be divided into multiple cards instead of just one. Using this principle helps in reducing the side effects and frequency of required changes.

EXAMPLE:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9a3107a6-791c-487d-ac19-c46c0c9db978/Untitled.png)

Suppose, we have created an interface named **Conversion** having three methods **intToDouble(), intToChar(),** and **charToString()**.
(Below interface doesn’t support Interface Segregation Principle)

```java
public interface Conversion  
{  
public void intToDouble();  
public void intToChar();  
public void charToString();  
}
```

The above interface has three methods. If we want to use only a method intToChar(), we have no choice to implement the single method. To overcome the problem, the principle allows us to split the interface into three separate ones.

```java
public interface ConvertIntToDouble  
{  
public void intToDouble();  
}   
public interface ConvertIntToChar  
{  
public void intToChar();  
}  
public interface ConvertCharToString   
{  
public void charToString();  
}
```

Now we can use only the method that is required. Suppose, we want to convert the integer to double and character to string then, we will use only the methods **intToDouble()**
 and **charToString().**

```java
public class DataTypeConversion implements ConvertIntToDouble, ConvertCharToString   
{  
public void intToDouble()  
{  
//conversion logic  
}  
public void charToString()  
{  
//conversion logic  
}  
}
```
