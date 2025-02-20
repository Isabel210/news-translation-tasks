---
标题：C#类手册——带有代码示例的类类型
日期：2025年2月6日 下午3:27:56.141 GMT
作者：Isaiah Clifford Opoku（伊萨克·克利福德·奥普库）
作者网址：https://www.freecodecamp.org/news/author/Clifftech/
原始网址：https://www.freecodecamp.org/news/classes-in-c-sharp-handbook-with-examples/
译者：Isabel Albert 210（伊莎贝尔·艾伯特210）
校对：
---

类是C#面向对象编程的基本构建块。它们允许您通过将相关的数据和函数分组来创建可重用和模块化的代码。

<!-- 更多 -->

不同类型的类有不同的用途。例如，在构建应用程序时，组织你的逻辑以使代码更容易导航是有帮助的。

你可以将代码分组或分离到类中，并且通过继承，你可以根据需要使用不同的类。类有助于封装你的代码，使你能够在其他应用程序部分重用你的逻辑。类有许多功能，我们将详细探讨其中的一些。

在这份指南中，我们将探讨C#中的各种类类型以及如何使用它们创建高效且可维护的代码。

## **先决条件**

在我们继续之前，您应该具备以下条件：

1.  **C#基础知识**: 你应该了解C#语法和基本的编程构造，如变量、循环和条件。
    
2.**熟悉面向对象编程（OOP）概念**：你应该知道如何使用类、对象、继承、多态、封装和抽象。
    
3.**熟悉访问修饰符**：您应该了解公共、私有、内部和受保护的访问修饰符。
    
4.**C#IDE/环境经验**：您应该能够使用Visual Studio等IDE编写和运行C#程序。
    

如果你想了解更多关于C#的信息，你可以看看我的YouTube频道：[CliffTech][1]。

## 目录

-[C Sharp中的静态类][2]
    
-[C Sharp密封类][3]
    
-【C Sharp混凝土等级】[4]
    
-[C Sharp中的抽象类][5]
    
-[C Sharp中的单人课][6]
    
-[C Sharp中的通用类][7]
    
-[C Sharp中的内部类][8]
    
-[C Sharp中的嵌套类][9]
    
-[C Sharp的部分课程][10]
    
-[结论][11]

我们将讨论的第一类是静态类。让我们潜入水中。

## C Sharp中的静态类

静态类是C#中的一种特殊类型的类，旨在提供不依赖于实例数据的相关实用方法和属性的集合。

C#中的静态类是一种独特的类，旨在容纳不依赖于实例数据的相关实用方法和属性的集合。

与常规类不同，静态类不能实例化，并且它们只包含静态成员。这一特性意味着它们不能被继承，这使得它们非常适合组织不需要面向对象编程特性的无状态方法。

本质上，当我们提到无状态分组时，它意味着不需要创建实例来调用静态方法——你可以直接使用类或方法名。这种方法提供了一种清晰有效的方法来管理实用程序函数，增强了代码组织和可访问性。

### C中静态类的示例

下面是一个C#中静态类的示例：

```
namespace StaticClasses
{
// Define a static class
    public static class MathUtils
    {
        // Static method to add two numbers
        public static int Add(int a, int b)
        {
            return a + b;
        }

        // Static method to subtract two numbers
        public static int Subtract(int a, int b)
        {
            return a - b;
        }

       // Static method to multiply two numbers
        public static int Multiply(int a, int b)
        {
            return a * b;
        }
    }
}
```

在这个例子中：
-MathUtils类被定义为static，这意味着它不能被实例化。
    
-它包含三个静态方法：“加法”、“减法”和“乘法”。
    
-这些方法可以直接在“MathUtils”类上调用，而无需创建实例。
    
在使用它之前，您需要在“Program.cs”中调用它。当你创建任何C#应用程序时，入口点是“Program.cs”。你需要去那里并确保调用这些类，以便你可以执行它们。这就是我们将在本节其余部分所做的。

### 如何在`Program.cs中使用静态方法`

现在，您可以使用`MathUtils`类中定义的静态方法，如下所示：

```

 // program.cs
namespace StaticClasses
{
    class Program
    {
        static void Main(string[] args)
        {
             // Call static methods from the MathUtils class
            int sum = MathUtils.Add(5, 3);
            // Call the static method Subtract from the MathUtils class
            int difference = MathUtils.Subtract(5, 3);

            // Call the static method Multiply from the MathUtils class
            int product = MathUtils.Multiply(5, 3);

            // Display the results of the sum method
            Console.WriteLine($"Sum: {sum}"); // Output: 8
            // Display the results of the difference method
            Console.WriteLine($"Difference: {difference}"); // Output: 2
            // Display the results of the product method
            Console.WriteLine($"Product: {product}");  // Output: 15
        }
    }
}
```

### 何时使用静态类与方法

要决定何时在C#中使用静态类或方法，请考虑以下准则：

1.**在以下情况下使用静态类：**
    
-您需要一组不需要任何实例数据的实用程序或辅助方法。
        
-方法和属性是无状态的，可以在不创建对象的情况下全局访问。
        
-您希望对不绑定到特定对象状态的相关函数进行分组。
        
-您需要确保类不能被实例化或继承。
        
2.**在以下情况下使用静态方法：**
    
-您有一个主要基于实例的类，但您需要一些不依赖于实例数据的方法。
        
-该方法执行的任务独立于任何对象状态，并且可以在没有实例的情况下执行。
        
-您希望在类中提供一个实用函数，该函数可以在不创建该类对象的情况下访问。
        

通过适当地使用静态类和方法，您可以增强代码组织，通过避免不必要的对象创建来提高性能，并确保某些功能在整个应用程序中易于访问。


### C中静态类要记住的要点

-**无法实例化**：您无法从静态类创建对象。
    
-**只有静态成员**：静态类只能有静态成员。它们不支持实例方法或字段。
    
-**默认密封**：静态类是自动密封的，因此不能被继承。
    
-**实用程序和辅助方法**：静态类通常用于对不需要对象状态的相关实用程序或辅助方法进行分组。
    

静态类有助于清晰简单地组织和访问实用程序方法和属性，这使得它们对于创建高效和可维护的代码非常重要。

## C Sharp密封类

密封类是C#中一种特殊类型的类，不能被继承。您可以使用它们来防止其他类从它们派生，这对于创建不可变类型或确保类的行为保持不变非常有用。

通过密封一个类，您可以确保它不能被修改或扩展，这使得它在您想要提供特定实现而不允许进一步更改的情况下非常有用。

### C中密封类的示例

以下是C#中一个密封类的示例：


```
namespace SealedClasses
{

    // Define an abstract class
    public abstract class Shape
    {
        // Abstract method to calculate the area
        public abstract double CalculateArea();
    }

     // Define a sealed class
    public sealed class Rectangle : Shape
    {

        //  Properties
        public double Width { get; }
        public double Height { get; }

        // Constructor
        public Rectangle(double width, double height)
        {
            Width = width;
            Height = height;
        }

       // Implement the CalculateArea method
        public override double CalculateArea()
        {
            return Width * Height;
        }
    }
}
```

在这个例子中：

-Shape类是一个抽象基类，具有抽象方法CalculateArea（）。
    
-“Rectangle”类继承自“Shape”，并为“CalculateArea（）”提供了一个实现。
    
-Rectangle类是密封的，这意味着它不能从继承。这确保了类的实现不能被修改或扩展。
    

### 如何在.cs程序中使用密封矩形类

以下是如何在“Program.cs”文件中使用“Rectangle”类：

```
namespace SealedClasses
{
    class Program
    {
        static void Main(string[] args)
        {
            Rectangle rectangle = new Rectangle(5, 3);
            double area = rectangle.CalculateArea();

            Console.WriteLine($"Area of the rectangle: {area}"); // Output: Area of the rectangle: 15
        }
    }
}
```

在这个例子中，`Rectangle `类被密封，以确保其行为不能通过继承而改变。这保证了`Rectangle `类的`CalculateArea（）`实现保持不变，这有助于保持一致的行为。

### 何时使用密封类

密封类在以下情况下特别有用：

1.**框架开发**：在开发框架或库时，您可能会使用密封类来锁定某些不打算由用户扩展的类。这有助于保持对框架行为的控制，并确保用户不会通过扩展这些类来引入错误或不一致。
    
2.**防止继承**：如果一个类被设计为不需要进一步定制或扩展的特定实现，那么密封它可以防止其他开发人员创建可能改变其预期功能的子类。
    
3.**最终确定类设计**：当一个类的设计已经完成，并且预计不会有进一步的更改或扩展时，密封它可以向其他开发人员发出信号，表明该类应该按原样使用。
    
4.**避免重写**：在重写方法可能导致不正确行为或安全问题的情况下，密封类可以确保其方法不能被重写，从而保留原始逻辑和功能。
    

### 关于密封类需要记住的要点

-**无继承**：密封类不能被继承，确保它们的行为保持不变。
    
-**防止修改**：防止进一步继承，避免意外更改或扩展。
    
-**不可变和特定**：密封类对于创建不可变类或需要特定、不可更改的实现时很有用。
    

### 密封类与静态类

您可能会想知道，如果静态类已经密封，为什么我们需要密封类。主要区别在于：

-**静态类**是密封的，不能实例化。它们用于对静态方法和属性进行分组。
    
-**密封类**可以实例化，但不能继承。这允许创建受保护的对象，以防止进一步的子类化。
    

密封类在创建可以直接使用的类时提供了灵活性，而没有通过继承进行修改的风险。

## C Sharp混凝土等级

在C#的“面向对象编程”中，具体类是必不可少的。它们是完全实现的类，您可以使用它们直接创建对象。

与“抽象类”或“接口”不同，具体类具有其所有方法和属性的完整实现，这使得它们对大多数C#应用程序来说是通用和基础的。

具体的类不是抽象的。它包括其所有成员（方法、属性、字段等）的完整实现，可用于创建对象。这些类表示应用程序中的真实实体或概念，封装数据（存储在字段或属性中）和行为（由方法定义）。

### 示例：在C中定义具体类

下面是一个C#中具体类的简单示例：
```


// Define a concrete class
public class Animal
{
    public void Speak()
    {
        Console.WriteLine("The animal makes a sound.");
    }
}

// Define a derived class that inherits from the Animal class
public class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("The dog barks.");
    }
}
```

在这个例子中，`Animal`类是一个具体的类，它有一个方法`Speak`，表示任何动物发出的通用声音。“Dog”类继承自“Animal”，并添加了一个“Bark”方法来表示狗特有的声音。“Animal”和“Dog”都是具体的类，因为它们可以被实例化并用于创建对象。

### 如何实例化和使用具体类

以下是如何在“Program.cs”文件中使用“Dog”类：
```

// program.cs
class Program
{
    static void Main(string[] args)
    {
        // Create an instance of the Dog class
        Dog myDog = new Dog();

        // Call the inherited method
        myDog.Speak(); // Output: The animal makes a sound.

        // Call the method defined in the Dog class
        myDog.Bark();  // Output: The dog barks.
    }
}
```

在这个例子中，我们创建了一个名为“myDog”的“Dog”类的实例。我们首先调用从Animal类继承的Speak方法，然后调用Dog类的Bark方法。这展示了具体类如何同时包含继承行为和唯一行为。

### 真实世界示例：产品的混凝土类

为了说明具体类的实际应用，请考虑以下“Product”类的示例：

```
// Define a concrete class for a product
public class Product
{
    // Data properties
    public string Name { get; set; }
    public decimal Price { get; set; }

    // Method to display product information
    public void DisplayInfo()
    {
        Console.WriteLine($"Product: {Name}, Price: {Price:C}");
    }
}
```

这个“Product”类是一个具有属性“Name”和“Price”的具体类，用于存储有关产品的信息。“DisplayInfo”方法提供了一种显示产品详细信息的方法。

#### 如何使用“产品”类

以下是如何使用“Product”类：

```
class Program
{
    static void Main(string[] args)
    {
        // Create an instance of the Product class
        Product product = new Product
        {
            Name = "Laptop",
            Price = 1299.99m
        };

        // Display product information
        product.DisplayInfo(); // Output: Product: Laptop, Price: $1,299.99
    }
}
```
在这种情况下，“Product”类用于创建“Product”对象。调用`DisplayInfo`方法以显示产品的名称和价格。这演示了如何使用具体类来建模和处理真实世界的数据。

### 关于混凝土课要记住的要点

-**可实例化**：可以实例化具体的类，允许您创建表示应用程序中特定实体或概念的对象。
    
-**完整实现**：与抽象类或接口不同，具体类提供了所有方法和属性的完整实现。
    
-**常用**：它们是C#中最常见的类类型，用于定义具有特定行为和数据的对象。
    

具体的类对于C#开发至关重要，使您能够定义和使用在应用程序中建模真实世界实体的对象。了解如何有效地使用具体类对于构建健壮的面向对象软件至关重要。

## C Sharp中的抽象类

在C#中，抽象类是一个强大的特性，它允许您在不提供完整实现的情况下为其他类定义蓝图。它们作为基类，不能直接实例化，但可以被其他类继承，这些类将为其中定义的抽象方法提供特定的实现。这种设计有助于加强相关类之间的一致性，同时允许在实现某些行为时具有灵活性。

### “立即”是什么意思？

在探索抽象类之前，让我们先阐明实例化类的含义。实例化是从类创建对象的过程。当你在C#中使用“new”关键字时，你正在创建该类的实例（或对象）。

但是抽象类不能直接实例化。它们必须由提供抽象方法实现的非抽象（具体）类继承。

### 理解抽象类和抽象方法

**抽象类**是不能直接从中创建对象的类。它们充当其他类的模板。它们既可以有完整的方法，也可以有没有主体的方法（抽象方法）。抽象类有助于为相关类设置通用接口和共享行为。

**另一方面，抽象方法**是抽象类中没有主体的方法。从抽象类继承的任何非抽象类都必须为这些方法提供一个主体。这确保了所有子类都有一个一致的接口。

### 真实世界示例：银行账户管理

让我们探索一个真实世界的例子来说明C#中抽象类和抽象方法的概念。

```
using System;

// define an abstract class
namespace AbstractClasses
{
    // Abstract class
    public abstract class BankAccount
    {
        // Properties
        public string AccountNumber { get; private set; }
        public decimal Balance { get; protected set; }

        // Constructor
        public BankAccount(string accountNumber, decimal initialBalance)
        {
            AccountNumber = accountNumber;
            Balance = initialBalance;
        }

        // Abstract methods
        public abstract void Deposit(decimal amount);
        public abstract void Withdraw(decimal amount);
        public abstract void DisplayAccountInfo();
    }

    // Derived class: SavingsAccount
    public class SavingsAccount : BankAccount
    {
        private decimal interestRate;

        public SavingsAccount(string accountNumber, decimal initialBalance, decimal interestRate)
            : base(accountNumber, initialBalance)
        {
            this.interestRate = interestRate;
        }

        // Implementing abstract methods
        public override void Deposit(decimal amount)
        {
            Balance += amount;
            Console.WriteLine($"Deposited {amount} to Savings Account {AccountNumber}. New Balance: {Balance}");
        }

        public override void Withdraw(decimal amount)
        {
            if (amount > Balance)
            {
                throw new InvalidOperationException("Insufficient funds.");
            }
            Balance -= amount;
            Console.WriteLine($"Withdrew {amount} from Savings Account {AccountNumber}. New Balance: {Balance}");
        }

        public override void DisplayAccountInfo()
        {
            Console.WriteLine($"Savings Account {AccountNumber} - Balance: {Balance}, Interest Rate: {interestRate}%");
        }
    }

    // Derived class: CheckingAccount
    public class CheckingAccount : BankAccount
    {
        private decimal overdraftLimit;

        public CheckingAccount(string accountNumber, decimal initialBalance, decimal overdraftLimit)
            : base(accountNumber, initialBalance)
        {
            this.overdraftLimit = overdraftLimit;
        }

        // Implementing abstract methods
        public override void Deposit(decimal amount)
        {
            Balance += amount;
            Console.WriteLine($"Deposited {amount} to Checking Account {AccountNumber}. New Balance: {Balance}");
        }

        public override void Withdraw(decimal amount)
        {
            if (amount > Balance + overdraftLimit)
            {
                throw new InvalidOperationException("Overdraft limit exceeded.");
            }
            Balance -= amount;
            Console.WriteLine($"Withdrew {amount} from Checking Account {AccountNumber}. New Balance: {Balance}");
        }

        public override void DisplayAccountInfo()
        {
            Console.WriteLine($"Checking Account {AccountNumber} - Balance: {Balance}, Overdraft Limit: {overdraftLimit}");
        }
    }
}
```


在这个例子中，“BankAccount”类是一个抽象类，它为不同类型的银行账户定义了一个通用接口。它包括抽象方法，如“Deposit”、“Withdraw”和“DisplayAccountInfo”，这些方法必须由继承自“BankAccount”的任何类实现。

SavingsAccount和CheckingAccount类继承自BankAccount，并为这些抽象方法提供了具体的实现。这种设计强制要求每种类型的银行账户都必须实现存款、取款和显示功能，同时仍然允许每种账户类型以对特定类型有意义的方式实现这些功能。

### 如何在程序中使用抽象类

让我们看看如何在“Program.cs”文件中使用“SavingsAccount”和“CheckingAccount”类。

```
namespace AbstractClasses
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a savings account
            BankAccount savings = new SavingsAccount("SA123", 1000, 1.5m);
            // Create a checking account
            BankAccount checking = new CheckingAccount("CA123", 500, 200);

            // Deposit and withdraw from the savings account
            savings.DisplayAccountInfo();

           // Deposit and withdraw from the checking account
            savings.Deposit(200);

            savings.Withdraw(100);
            // Display the updated account information
            savings.DisplayAccountInfo();

            checking.DisplayAccountInfo();

             // Deposit and withdraw from the checking account
            checking.Deposit(300);

            checking.Withdraw(600);

            // Display the updated account information
            checking.DisplayAccountInfo();

            try
            {
                checking.Withdraw(200);
            }
            catch (InvalidOperationException ex)
            {
                Console.WriteLine($"Error: {ex.Message}");
            }

            checking.DisplayAccountInfo();
        }
    }
}
```

此程序将产生以下输出：

```
Savings Account SA123 - Balance: 1000, Interest Rate: 1.5%
Deposited 200 to Savings Account SA123. New Balance: 1200
Withdrew 100 from Savings Account SA123. New Balance: 1100
Savings Account SA123 - Balance: 1100, Interest Rate: 1.5%
Checking Account CA123 - Balance: 500, Overdraft Limit: 200
Deposited 300 to Checking Account CA123. New Balance: 800
Withdrew 600 from Checking Account CA123. New Balance: 200
Checking Account CA123 - Balance: 200, Overdraft Limit: 200
Withdrew 200 from Checking Account CA123. New Balance: 0
Checking Account CA123 - Balance: 0, Overdraft Limit: 200
```

在这个例子中，创建了“SavingsAccount”和“CheckingAccount”对象，并调用了抽象方法“Deposit”、“Withdraw”和“DisplayAccountInfo”。抽象类“BankAccount”确保两种帐户类型都有这些方法，而派生类则提供特定的功能。

### 关于抽象类需要记住的要点

-**无法实例化**：您不能直接创建抽象类的实例。子类必须继承它，并为抽象方法提供实现。
    
-**包含抽象方法**：抽象类中的抽象方法没有主体。从抽象类继承的任何非抽象类都必须实现这些方法。
    
-**定义通用接口**：抽象类为相关类设置通用接口，确保它们在允许不同实现的同时保持一致。
    

抽象类在C#中很重要。它们有助于在相关类之间强制执行结构，但仍然允许特定的细节。通过使用抽象类，您可以使代码更有条理，更容易维护和扩展。

## C Sharp中的Singleton类

Singleton类是一种设计模式，它将类的实例化限制为一个实例。当您需要跨应用程序的单个共享资源时，这尤其有用，例如配置管理器、日志服务或数据库连接。

### 为什么在C#中使用Singleton类？

想象一下，你有一个负责管理数据库连接的类。您不希望此类的多个实例四处运行，这可能会导致资源管理或数据不一致的问题。Singleton类确保只创建一个实例，并提供对它的全局访问点。

### 示例：定义Singleton类

现在让我们看看如何在C#中实现Singleton类：

```
// Define a singleton class
public class Singleton
{
    private static Singleton instance;
    private static readonly object lockObject = new object();

    // Private constructor prevents instantiation from outside the class
    private Singleton()
    {
    }

    // Public property to access the single instance of the class
    public static Singleton Instance
    {
        get
        {
            // Ensure thread safety
            lock (lockObject)
            {
                if (instance == null)
                {
                    instance = new Singleton();
                }
            }
            return instance;
        }
    }

    // Example method to demonstrate the singleton instance
    public void PrintMessage()
    {
        Console.WriteLine("Hello, I am a singleton class.");
    }
}
```

在这个例子中，`Singleton`类是用私有构造函数定义的，这可以防止其他类创建新的实例。静态属性“Instance”返回类的单个实例，如果它还不存在，则创建它。lockObject确保类是线程安全的，这意味着即使在多线程环境中，也只会创建一个实例。

“PrintMessage”方法只是一个简单的例子，说明Singleton实例可以像任何其他类实例一样使用。

### 如何在`Program.cs中使用Singleton类`

现在让我们看看如何在应用程序中使用这个Singleton类：

```
class Program
{
    static void Main(string[] args)
    {
        // Retrieve the single instance of the Singleton class
        Singleton singleton1 = Singleton.Instance;
        singleton1.PrintMessage(); // Output: Hello, I am a singleton class.

        // Retrieve the instance again
        Singleton singleton2 = Singleton.Instance;

        // Check if both instances are the same
        Console.WriteLine(singleton1 == singleton2); // Output: True
    }
}
```

在这个例子中，我们检索Singleton实例两次。因为类是Singleton，所以“singleton1”和“singleton2”都引用同一个实例。“==”运算符通过返回“true”来确认这一点。

### 如何扩展Singleton示例

您可以扩展Singleton模式来处理更复杂的场景。例如，您可以使用配置数据初始化Singleton实例：

```
public class ConfigurationManager
{
    private static ConfigurationManager instance;
    private readonly Dictionary<string, string> settings = new Dictionary<string, string>();

    private ConfigurationManager()
    {
        // Simulate loading settings from a configuration file
        settings["AppName"] = "MyApplication";
        settings["Version"] = "1.0.0";
    }

    public static ConfigurationManager Instance
    {
        get
        {
            if (instance == null)
            {
                instance = new ConfigurationManager();
            }
            return instance;
        }
    }

    public string GetSetting(string key)
    {
        return settings.ContainsKey(key) ? settings[key] : null;
    }
}
```

这里，`ConfigurationManager`是一个加载和管理应用程序设置的Singleton类。GetSetting方法允许您检索特定的配置值，确保应用程序的所有部分使用相同的设置。

### 关于Singleton课程需要记住的要点

-**单实例**：Singleton类确保应用程序中只存在该类的一个实例。
    
-**全局访问**：Singleton提供了一个对实例的全局访问点，使其易于在应用程序的不同部分使用。
    
-**线程安全**：在多线程环境中，确保Singleton是线程安全的，以避免创建多个实例。
    
-**用例**：Singleton的常见用例包括管理配置、日志服务和数据库连接。
    

Singleton类是软件工程中的一种基本设计模式，提供了一种简单而强大的管理共享资源的方法。理解和正确实现Singletons可以帮助您编写更高效和可维护的代码。

## C Sharp中的通用类

C#中的泛型类提供了一种强大的方法来创建可重用和类型安全的代码。通过使用泛型类，您可以设计一个适用于任何数据类型的单个类，从而消除了对特定类型实现的需求。这使您的代码更加灵活，并减少了冗余。

### 为什么要使用泛型类？

想象一下，你需要实现一个存储整数的堆栈。稍后，您可能需要另一个堆栈来存储字符串。

您可以编写一个通用堆栈类来处理这两种数据类型以及您可能需要的任何其他数据类型，而不是编写两个单独的类。泛型类可以帮助您避免代码重复，并使您的代码库更易于维护。

### 示例：定义泛型类

让我们来看一个通用堆栈类的简单实现：

```
// Define a generic class
public class Stack<T>
{
    private List<T> items = new List<T>();

    public void Push(T item)
    {
        items.Add(item);
    }

    public T Pop()
    {
        if (items.Count == 0)
        {
            throw new InvalidOperationException("The stack is empty.");
        }
        T item = items[items.Count - 1];
        items.RemoveAt(items.Count - 1);
        return item;
    }

    public T Peek()
    {
        if (items.Count == 0)
        {
            throw new InvalidOperationException("The stack is empty.");
        }
        return items[items.Count - 1];
    }

    public bool IsEmpty()
    {
        return items.Count == 0;
    }
}
```

在这个例子中，`Stack<T>类是用类型参数`T`定义的。此类型参数是一个占位符，表示堆栈将存储的数据类型。该类包括诸如“Push”之类的方法，用于将项目添加到堆栈中，“Pop”用于删除并返回顶部项目，“Peek”用于查看顶部项目而不将其删除，以及“IsEmpty”用于检查堆栈是否为空。

因为`Stack<T>是泛型的，所以你可以将它用于任何数据类型，无论是`int`、`string`，甚至是自定义类。

### 如何在`Program.cs中使用Stack类`

让我们看看这个通用的`Stack`类如何在程序中使用：

```
class Program
{
    static void Main(string[] args)
    {
        // Stack for integers
        Stack<int> intStack = new Stack<int>();
        intStack.Push(10);
        intStack.Push(20);
        Console.WriteLine(intStack.Pop()); // Output: 20
        Console.WriteLine(intStack.Peek()); // Output: 10

        // Stack for strings
        Stack<string> stringStack = new Stack<string>();
        stringStack.Push("Hello");
        stringStack.Push("World");
        Console.WriteLine(stringStack.Pop()); // Output: World
        Console.WriteLine(stringStack.Peek()); // Output: Hello
    }
}
```

在这个例子中，我们创建了“Stack”类的两个实例：一个存储整数，另一个存储字符串。泛型的灵活性允许我们使用同一个类来处理不同的数据类型，使我们的代码更具可重用性和简洁性。

### 如何扩展泛型类

让我们更进一步，扩展我们的`Stack`类，以包含一个将所有项目作为数组返回的方法：

```
public T[] ToArray()
{
    return items.ToArray();
}
```

现在，您可以轻松地将堆栈的项转换为数组：

```
int[] intArray = intStack.ToArray();
string[] stringArray = stringStack.ToArray();
```

此扩展进一步展示了泛型的强大功能，允许相同的方法无缝地处理不同的数据类型。

### 关于泛型类需要记住的要点

-**灵活性**：泛型类可以处理任何数据类型，使其具有可适应性和可重用性。
    
-**类型安全**：使用类型参数可确保您的代码是类型安全的，在编译时而不是运行时捕获错误。
    
-**代码重用**：泛型消除了为不同数据类型重复代码的需要，从而使代码更清晰、更易于维护。
    
-**类型参数**：泛型类使用类型参数作为创建类实例时将使用的实际数据类型的占位符。
    

泛型类在C#中对于构建灵活、可重用和类型安全的代码至关重要。通过学习和使用泛型，您可以创建更可靠和可维护的应用程序。

## C Sharp的内部课程

C#中的内部类是将实现细节封装在程序集中的一种强大方式。通过使用“internal”访问修饰符，您可以限制对某些类的访问，确保它们只能在同一程序集中访问。

这对于隐藏不打算向库或应用程序的公共API公开的复杂逻辑或实用程序类特别有用。

### 为什么要使用内部类？

在大型应用程序中，您可能有只应由代码内部使用而不应由外部使用者使用的类。例如，不需要在程序集外部公开的辅助类、实用函数或更大系统的组件可以标记为“内部”。这确保了您的公共API保持干净和集中，同时仍然允许程序集中的全部功能。

### 示例：定义内部类

让我们考虑一个场景，其中您有一个处理订单的库。您可能有一个类来处理计算折扣的复杂逻辑，但您不希望库的用户可以访问这个类。相反，您只公开了主“OrderProcessor”类，将折扣逻辑隐藏在内部类中。

```
// Define a public class that uses an internal class
public class OrderProcessor
{
    public void ProcessOrder(int orderId)
    {
        // Internal class is used here
        DiscountCalculator calculator = new DiscountCalculator();
        decimal discount = calculator.CalculateDiscount(orderId);
        Console.WriteLine($"Order {orderId} processed with a discount of {discount:C}");
    }

    // Internal class that handles discount calculations
    internal class DiscountCalculator
    {
        public decimal CalculateDiscount(int orderId)
        {
            // Complex discount calculation logic
            return orderId * 0.05m;
        }
    }
}
```

在这个例子中，“DiscountCalculator”类被标记为“internal”，这意味着它只能在程序集中访问。OrderProcessor类是public类，它使用这个内部类来处理订单。库的外部用户可以调用“ProcessOrder”，而无需知道或与“DiscountCalculator”类交互。

### 如何在`Program.cs中使用内部类`

现在，让我们看看这在实践中是如何工作的：

```
class Program
{
    static void Main(string[] args)
    {
        OrderProcessor processor = new OrderProcessor();
        processor.ProcessOrder(12345); // Output: Order 12345 processed with a discount of $617.25
    }
}
```

在本例中，“ProcessOrder”方法是可公开访问的，但折扣计算的内部工作仍然隐藏，提供了一个干净安全的API。

### 关于内部课程需要记住的要点

-**有限的访问**：内部类只能在同一程序集中访问，这有助于保持公共API的简洁性和集中性。
    
-**封装**：它们用于隐藏不应公开的实现细节，如辅助函数或复杂逻辑。
    
-**可见性控制**：“内部”访问修饰符允许您控制哪些类和成员是可见的，确保其他程序集只能访问代码的必要部分。
    

内部类对于管理复杂的应用程序很重要，允许您控制可以从程序集外部访问代码的哪些部分。通过隐藏细节和限制访问，您可以保持代码库干净、易于维护和安全。

## C Sharp中的嵌套类

C#中的嵌套类是在另一个类中定义的。这种结构有助于将相关类分组在一起并封装实现细节。嵌套类可以是静态的或非静态的，它们可以直接访问其封闭类的私有成员。

### 为什么要使用嵌套类？

当一个类与另一个类的逻辑紧密相关并且不打算独立使用时，嵌套类特别有用。它们允许您封装辅助类，对程序的其他部分隐藏它们，并将相关代码放在一起。这可以带来一个更干净、更有组织的代码库。

### 示例：定义嵌套类

让我们考虑一个场景，其中一个类表示“Car”，另一个类代表“Engine”。由于“Engine”类与“Car”类密切相关，并且本身没有多大意义，因此我们可以将其定义为“Car”中的嵌套类。

```
// Define a class with a nested class
public class Car
{
    // Define private fields
    private string model;
    private Engine carEngine;

   // Constructor
    public Car(string model)
    {
        this.model = model;
        carEngine = new Engine();
    }


    // Method to start the car
    public void StartCar()
    {
        carEngine.StartEngine();
        Console.WriteLine($"{model} is starting...");
    }

    // Nested class
    public class Engine
    {
        public void StartEngine()
        {
            Console.WriteLine("Engine started.");
        }
    }
}
```

在这个例子中，“Car”类有一个私有字段“model”和一个启动汽车的方法“StartCar”。“Engine”类嵌套在“Car”类中，并包含一个“StartEngine”方法。通过将“Engine”嵌套在“Car”中，我们表达了两者之间的密切关系。

### 如何在`Program.cs中使用嵌套类`

让我们看看如何在程序中使用“Car”类及其嵌套的“Engine”类：

```
class Program
{
    static void Main(string[] args)
    {
        Car myCar = new Car("Toyota");
        myCar.StartCar(); // Output: Engine started. Toyota is starting...

        // Although you can create an instance of the nested class separately, it usually makes sense to use it through the outer class
        Car.Engine engine = new Car.Engine();
        engine.StartEngine(); // Output: Engine started.
    }
}
```

在这个例子中，我们创建了一个“Car”类的实例，并调用了“StartCar”方法，该方法在内部调用嵌套的“Engine”类的“StartEngine”方法。虽然可以单独实例化嵌套类，但更常见的是通过外部类访问它，强调两者之间的关系。

### 关于嵌套类需要记住的要点

-**封装**：嵌套类将不应该在主类之外看到的细节隐藏起来。
    
-**访问私有成员**：嵌套类可以访问主类的私有部分，这使得它们非常适合需要处理主类内部部分的辅助类。
    
-**组织**：使用嵌套类将相关类保持在一起，使代码更清晰、更有条理。
    
-**静态或非静态**：嵌套类可以是静态的或非静态的。静态嵌套类不能直接访问主类的实例部分，但非静态嵌套类可以。
    

嵌套类是组织代码的一种有用方法，特别是对于具有密切相关部分的复杂对象。将相关类放在一起可以使代码更容易管理和维护。

## C Sharp中的部分课程

C#中的分部类允许您将类定义拆分到多个文件中。此功能在大型项目中特别有用，将复杂的类分解为更小、更易于管理的部分是有益的。

通过使用“partial”关键字，您可以更好地组织代码，特别是在处理生成的代码或在团队环境中协作时。

### 为什么要使用分部类？

想象一下，你正在开发一个大型应用程序，其中一个类包含数百行代码。这可能会变得难以管理和维护。通过使用分部类，您可以将类划分为逻辑部分，每个部分都驻留在单独的文件中。这不仅使代码更具可读性，而且允许多个开发人员同时处理类的不同部分，而不会导致合并冲突。

### 示例：在C中定义一个分部类

假设我们有一个类来处理员工管理系统的各种操作。我们可以使用分部类将它们拆分到多个文件中，而不是将所有方法放在一个文件中。

**文件1:**`部分类_方法1.cs`

```
// Define a partial class
public partial class EmployeeOperations
{
    public void AddEmployee(string name)
    {
        Console.WriteLine($"Employee {name} added.");
    }
}
```

**File 2:** `PartialClass_Methods2.cs`

```
// Define the other part of the partial class
public partial class EmployeeOperations
{
    public void RemoveEmployee(string name)
    {
        Console.WriteLine($"Employee {name} removed.");
    }
}
```

在这些示例中，`EmployeeOperations`类被拆分为两个文件，每个文件都包含该类的一部分。第一个文件处理添加员工，而第二个文件处理删除员工。

### 如何在`Program.cs中使用分部类`

现在，让我们在`Program.cs `文件中使用`EmployeeOperations`类：

```
class Program
{
    static void Main(string[] args)
    {
        EmployeeOperations operations = new EmployeeOperations();

        operations.AddEmployee("John Doe");    // Output: Employee John Doe added.
        operations.RemoveEmployee("John Doe"); // Output: Employee John Doe removed.
    }
}
```

在这个例子中，`EmployeeOperations`类虽然在多个文件中定义，但其行为类似于一个类。“AddEmployee”和“RemoveEmployee”方法无缝结合，提供了一种干净有序的操作管理方式。

### 关于部分课程需要记住的要点

-**代码组织**：分部类通过将大类拆分为更小、更集中的部分来帮助保持大类的组织。
    
-**团队协作**：多个开发人员可以在同一类的不同部分上工作，而不会干扰彼此的代码。
    
-**生成代码**：通常与自动生成的代码一起使用，其中类的一部分由工具生成，其余部分由手动编写。
    

分部类是C#中的一个强大功能，它允许更好的代码管理，特别是在大规模应用程序中。通过将类分解为逻辑组件，您可以维护干净、可读和可维护的代码。

## 结论

类是C#中面向对象编程的构建块。通过理解不同类型的类（抽象类、静态类、密封类、具体类和单例类），您可以创建结构良好、可维护且高效的代码。

无论您是设计实用程序类、定义抽象接口还是封装复杂逻辑，类在塑造应用程序的架构方面都起着至关重要的作用。

[1]: https://www.youtube.com/@CliffTech
[2]: #heading-static-classes-in-c-sharp
[3]: #heading-sealed-classes-in-c-sharp
[4]: #heading-concrete-classes-in-c-sharp
[5]: #heading-abstract-classes-in-c-sharp
[6]: #heading-singleton-classes-in-c-sharp
[7]: #heading-generic-classes-in-c-sharp
[8]: #heading-internal-classes-in-c-sharp
[9]: #heading-nested-classes-in-c-sharp
[10]: #heading-partial-classes-in-c-sharp
[11]: #heading-conclusion
