# Java Fundamentals Cheatsheet

## Data Types:
**Primitive data types represent the actual content of the data that is stored in the memory.**  
**Reference data types represent a reference to the location of the actual data stored in memory.**  
<br>
**Primitive Data Types:**
- Integral:
    - Byte: 1 byte.
    - Short: 2 bytes.
    - Integer: 4 bytes.
    - Long: 8 bytes.
- Floating:
    - Float: 4 bytes.
    - Double: 8 bytes.
- Char: 2 bytes per character.
- Boolean: 1 bit.  
**Reference Data Types:**  
- String.

## Value Types:
- Private: Can only be accessed within the same class.
- Protected: Can only be accessed within the same class within its child classes.
- Public: Can be accessed by any other classes.
- Default: Can be accessed by classes within the same package.
- Static: Is an **add on** type which is to be used when you want to set it to static.

## Classes:
### Class Declaration:
```java
classType class ClassName{}
i.e. public class ClassName{}
```
Class names should be a noun and have the first letter capitalised.
### Main Method Declaration:
```java
public static void main(String[] args){}
```

## Methods:
### Constructor:
```java
public ClassName(){}
```
- The constructor is a special method is used to create an object.
- The constructor's name must be exactly the same to the class name.
- There is no return data type, not even void.
- Initiates the instance variables for the object's attributes.
### Regular Method:
```java
methodType [static] returnType methodName(){}
```
- The method type is the value type of the method as explained above.
- Include the `static` keyword if you wish to set the method to static.
- The return type is the type of value you want to return or `void` if you are not returning any values.
### toString() Method:
The toString() method is to be used to convert a primitive data type into a string object.
```java
public String toString(){}
```
Example:
```java 
public static void main(String[] args){
    int x=5;
    System.out.print(x.toString());
}
```
This would return `5`.
### Method Overloading:
Method overloading is when you have 2 or more methods with the same name but with a different signature.  
A signature of a method is determined by the number, data type and order of the parameters.  
i.e. `method(int, boolean)`
## Managing Inputs:
### Scanner Class:
Using the scanner class is one way to get user inputs in Java.
The scanner class is located in the `java.util` package.  
To import it: `import java.util.Scanner;`.
```java
String input;
Scanner sc=new Scanner(System.in);
input=sc.nextLine();
sc.close();
```
You can also scan to get any type of value in particular like the next boolean, etc.
### Split() Method:
The split method allows you to split a string to isolate certain elements.  
You input your delimiters in the split method (using `[]` if you have multiple).  
Example usage:  
```java
String github="github.com/daylamtayari";
String[] words2=new String[2];
words2=github.split(".");
String[] words=new String[3];
words=github.split("[./]");

//Result:
words:  |github|com|daylamtayari|
words2: |github|com/daylamtayari|
```

## Static and Non-Static Elements:
- A static method or variable is directly related with a class not an object.
- With a static variable, only 1 copy will be shared by all objects of the same class.
- You do not need to call the object when calling static methods.
- We can **not** override static methods but we can override non-static methods.
### Static Methods:
- Can call another static method.
- Can call a static variable.
- Can NOT call a non-static method.
- Can NOT call an instance variable.
### Non-Static Methods:
- Can call another non-static method.
- Can call an instance variable.
- Can call a static method.
- Can call a static variable.

## Arrays:
### Regular Arrays:
#### Declaring:
Java regular arrays are fixed length.  
You can declare arrays the following ways:
```java
//Regular arrays:
String[] arr;
String[] arr1=new String[7];
String[] arr2={"github.com/daylamtayari", "tayari.gg"};

//2D arrays:
String[][] arr2D;
String[][] arr2D1=new String[5][6];
int[][] arr2D2={{1,2},{1-1,1-2,1-3}};
```

#### Accessing and Modifying an Array Element:
```java
//Regular arrays:
String github=arr2[0];
String fullLink="https://github.com/daylamtayari";
arr[0]=fullLink;

//2D arrays:
int num1=arr[0][0];
num1: 1
int num3=arr[1][2];
num3: 1-3
```
#### Array Length:
```java
int length=arr2.length;
```
#### Looping through an Array:
```java
//Using a for-loop:
for(int i=0;i<arr2.length;i++){
    System.out.println(arr2[i]);
}

//Using a for-each-loop:
for(String i: arr2){
    System.out.println(arr[i]);
}
```
<br> 

### ArrayLists:
ArrayLists need to be imported to use them. They are located in the `java.util` package.  
To import them: `import java.util.ArrayList;`  
#### Declaring ArrayLists:
```java
ArrayList<String> al=new ArrayList<String>();
```
#### Adding a Value:
The `.add()` method will append the value to the end of the ArrayList.  
To add the value to a specific index do `.add([index], [value]);`.
```java
//To append a value to the end of the list:
al.add("github.com/daylamtayari");

//To add at a specific index:
al.add(0,"tayari.gg");
```
#### Accessing and Modifying a Value:
```java
String website=al.get(0);

al.set(0, "https://tayari.gg");
```
#### Removing a Value:
```java
al.remove(0);
al.clear();
```
#### ArrayList Length:
```java
al.size();
```
#### Looping Through an ArrayList:
```java
for(int i=0;i<al.size();i++){
    System.out.println(al.get(i));
}
```


## Abstract Methods:
- An abstract method is a method with only the header and no method body that is called in it's child classes. i.e. `public void abstract();`.
- Any class that have one or more abstract methods must be declared as abstract.
### Super Keyword:
The super keyword is used to construct or call methods from your parent class.  
`Super` is a reference variable that points to your parent class.  
For constructors: `super([parameters of the parent's class constructor]);`.  
For constructors, the super keyword must be the first line of the child class's constructor.  
For methods: `super.methodName([method parameters]);`.
### Method overriding:
Method overriding is when the child class inherits a method from the parent class but uses a different method body.
The method in the parent **and** in the child class must have the same signature **and** same return data type.  
```java
class Parent{
    public void test(){
        System.out.print("parent");
    }
}
class Child extends Parent{
    public void test(){
        System.out.print("child");
    }
}
```
