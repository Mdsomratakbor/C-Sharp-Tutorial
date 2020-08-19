### 1. What is C#? Write its features?
`C# is an object-oriented programming language that was developed by Microsoft in 2000. It is supported by different operating systems. C# is the primary language that is used to create .Net software applications. It allows us to create Windows UI apps, backend services, controls, libraries, android apps, and even blockchain applications. C# works on the concept of classes and objects just like Java.`
**Some of the C# features are as follows:**

- Follows structured approach
- Parameters passing is easy
- Code can be compiled on a different platform
- Open-source
- Object-oriented
- Flexible and scalable 

### 2. Explain what are classes and objects in C#?

` C# is an object-oriented language and classes are its foundation. A class generally depicts the structure of data, how data is stored and managed within a program. A class has its own properties, methods, and other objects that define the class.`

`Objects are the real-world entity having some characteristics and is created using the class instance. These classes define the type of the defined object.`

`For example, if we consider a program that covers the object related to the book. We call the class a Book which has two properties: name and the author. In real programming, Vedas is an object and an instance of the class Book.`



### 3. What difference between Convert.toString and .toString() method?

`Here both the methods are used to convert the string but the basic difference between them is: "Convert" function handles NULLS, while "i.ToString()" does not it will throw a NULL reference exception error. So as good coding practice using "convert" is always safe.`

### 4. Describe the different C# classes in detail?

**here are 4 types of classes that we can use in C#:**

- **Static Class:** It is the type of class that cannot be instantiated, in other words, we cannot create an object of that class using the new keyword and the class members can be called directly using their class name.
- **Abstract Class:** Abstract classes are declared using the abstract keyword. Objects cannot be created for abstract classes. If you want to use it then it must be inherited in a subclass. You can easily define abstract or non-abstract methods within an Abstract class. The methods inside the abstract class can either have an implementation or no implementation.
- **Partial Class:** It is a type of class that allows dividing their properties, methods, and events into multiple source files, and at compile time these files are combined into a single class.
- **Sealed Class:**  One cannot inherit a sealed class from another class and restricts the class properties. Any access modifiers cannot be applied to the sealed class.

### 5. Explain different access modifiers in C#?

`These are the keywords that help to define the accessibility of class, member, and data type in the program. These keywords are used to restrict the use of some data manipulation done by other classes. There are 4 types of access modifiers- public, private, protected, and internal. These modifiers define 6 other accessibility levels when working together- public, protected, internal, protected internal, private, and private protected.`