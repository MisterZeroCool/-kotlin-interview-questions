# Вопросы и ответы по собеседованию на вакансию Junior Android Developer на языке Kotlin.
Котлин чрезвычайно практичен. Итак, у него есть вывод типов, потрясающая безопасность типов, хорошая библиотека коллекций и библиотека параллелизма в довершение всего. И теперь это официально - многие организации переносят свои серверные приложения на Kotlin, и эта тенденция вряд ли скоро закончится. 

Плюсы Kotlin по сравнению с Java:
+ официальный язык для Android;
+ кросс-платформенность: можно писать backend-, Android-, iOS- и веб-приложения, создавать IoT-решения;
+ де-факто стандарт разработки и в нём много синтаксического «сахара»;
+ более лаконичен и малословен, что позитивно влияет на читабельность;
+ более консистентен при построении межплатформенного взаимодействия.
+  совместимость с Java;
+ большая безопасность;
+ совместимость с Java;
+ большая безопасность;
  <p align="center">
  <a href="https://www.fullstack.cafe">
  <img src="https://raw.githubusercontent.com/abhisheknaiidu/abhisheknaiidu/master/code.gif">
  </a>
</p>

### Q1: Какие Преимущества языка Kotlin перед Java?
Код на Kotlin компактнее на 30-40%
Безопасная работа с обнуляемыми переменными (Null Safety)
Функции-расширения (Extensions)
Классы данных (data classes)
Синглтоны на уровне языка (Object)
Корутины 

<details>
    <summary>### Q1: Какие Преимущества языка Kotlin перед Java?</summary>
    <p>Скандинавская мифология — мифология древних скандинавов</p>
</details>

</details>

<summary> ### Q1: How to initialize an array in Kotlin with values? ⭐⭐ </summary>
<p>

**Questions Details:**

In Java an array can be initialized such as:

```java
 int numbers[] = new int[] {10, 20, 30, 40, 50}
```

How does Kotlin's array initialization look like?


**Answer:**

```kotlin
val numbers: IntArray = intArrayOf(10, 20, 30, 40, 50)
```

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/31366229/how-to-initialize-an-array-in-kotlin-with-values/31366276#31366276)
</p>

### Q2: How to correctly concatenate a String in Kotlin? ⭐⭐

**Answer:**

In Kotlin, you can concatenate 
1. using string interpolation / templates
 ```kotlin
val a = "Hello"
val b = "World"
val c = "$a $b"
 ```
2. using the + / `plus()` operator
 ```kotlin
 val a = "Hello"
 val b = "World" 
 val c = a + b   // same as calling operator function a.plus(b)
 val c = a.plus(b)
 
 print(c)
 ```
3. using the `StringBuilder`
 ```kotlin
 val a = "Hello"
 val b = "World"
 
 val sb = StringBuilder()
 sb.append(a).append(b)
 val c = sb.toString()
 
 print(c)
 ```

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/44188240/kotlin-how-to-correctly-concatenate-a-string)
</details>

### Q3: What is basic difference between fold and reduce in Kotlin? When to use which? ⭐⭐

**Answer:**

* `fold` takes an initial value, and the first invocation of the lambda you pass to it will receive that initial value and the first element of the collection as parameters.

 ```kotlin 
 listOf(1, 2, 3).fold(0) { sum, element -> sum + element }
 ```
 The first call to the lambda will be with parameters `0` and `1`.

 Having the ability to pass in an initial value is useful _if you have to provide some sort of default value or parameter for your operation_.

* `reduce` doesn't take an initial value, but instead starts with the first element of the collection as the accumulator (called `sum` in the following example)

 ```kotlin
 listOf(1, 2, 3).reduce { sum, element -> sum + element }
 ```

 The first call to the lambda here will be with parameters `1` and `2`.

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/44429419/what-is-basic-difference-between-fold-and-reduce-in-kotlin-when-to-use-which)


### Q4: What is the idiomatic way to remove duplicate strings from array? ⭐⭐

**Questions Details:**

How to remove duplicates from an `Array<String?>` in Kotlin?


**Answer:**

Use the `distinct` extension function:

```kotlin
val a = arrayOf("a", "a", "b", "c", "c")
val b = a.distinct() // ["a", "b", "c"]
```

You can also use:
* `toSet`, `toMutableSet`
* `toHashSet` - if you don't need the original ordering to be preserved

These functions produce a `Set` instead of a `List` and should be a little bit more efficient than distinct.

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/40430297/kotlin-idiomatic-way-to-remove-duplicate-strings-from-array)


### Q5: What is the difference between var and val in Kotlin? ⭐⭐

**Answer:**

* **var** is like `general` variable and it's known as a _mutable_ variable in kotlin and can be assigned multiple times.

* **val** is like `Final` variable and it's known as _immutable_ in Kotlin and can be initialized only single time.

```sh
+----------------+-----------------------------+---------------------------+
|                |             val             |            var            |
+----------------+-----------------------------+---------------------------+
| Reference type | Immutable(once initialized  | Mutable(can able to change|
|                | can't be reassigned)        | value)                    |
+----------------+-----------------------------+---------------------------+
| Example        | val n = 20                  | var n = 20                |
+----------------+-----------------------------+---------------------------+
| In Java        | final int n = 20;           | int n = 20;               |
+----------------+-----------------------------+---------------------------+
```

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/44200075/val-and-var-in-kotlin)


### Q6: Where should I use var and where val? ⭐⭐

**Answer:**

Use **var** where value is changing _frequently_. For example while getting location of android device:

```kotlin
var integerVariable : Int? = null
```

Use **val** where there is _no change_ in value in whole class. For example you want set textview or button's text programmatically.

```kotlin
val stringVariables : String = "Button's Constant or final Text"
```

🔗 **Source:** [stackoverflow.com](https://stackoverflow.com/questions/44200075/val-and-var-in-kotlin)


### Q7: What is a data class in Kotlin? ⭐⭐

**Answer:**

We frequently create classes whose main purpose is to hold data. In Kotlin, this is called a data class and is marked as `data`:

```kotlin
data class User(val name: String, val age: Int)
```

To ensure consistency and meaningful behavior of the generated code, data classes have to fulfill the following requirements:

* The primary constructor needs to have at least one parameter;
* All primary constructor parameters need to be marked as val or var;
* Data classes cannot be abstract, open, sealed or inner;

🔗 **Source:** [kotlinlang.org](https://kotlinlang.org/docs/reference/data-classes.html)


### Q8: What is a primary constructor in Kotlin? ⭐⭐

**Answer:**

The **primary constructor** is part of the class header. Unlike Java, you don't need to declare a constructor in the body of the class. Here's an example:

```kotlin
class Person(val firstName: String, var age: Int) {
    // class body
}
```

The main idea is by removing the constructor keyword, our code gets simplified and easy to understand.

🔗 **Source:** [www.programiz.com](https://www.programiz.com/kotlin-programming/constructors)


### Q9: How to create singleton in Kotlin? ⭐⭐

**Answer:**

Just use `object`.
```kotlin
object SomeSingleton
```
The above Kotlin object will be compiled to the following equivalent Java code:
```java
public final class SomeSingleton {
   public static final SomeSingleton INSTANCE;

   private SomeSingleton() {
      INSTANCE = (SomeSingleton)this;
      System.out.println("init complete");
   }

   static {
      new SomeSingleton();
   }
}
```
This is the preferred way to implement singletons on a JVM because it enables thread-safe lazy initialization without having to rely on a locking algorithm like the complex double-checked locking.

🔗 **Source:** [medium.com](https://medium.com/@BladeCoder/kotlin-singletons-with-argument-194ef06edd9e)


### Q10: What will be result of the following code execution? ⭐⭐⭐

**Questions Details:**

What will be the output?
```kotlin
val aVar by lazy {
    println("I am computing this value")
    "Hola"
}
fun main(args: Array<String>) {
    println(aVar)
    println(aVar)
}
```


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q11: Explain lazy initialization in Kotlin ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q12: Explain the Null safety in Kotlin ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q13: Explain what is wrong with that code? ⭐⭐⭐

**Questions Details:**

Why is this code wrong?

```kotlin
class Student (var name: String) {
    init() {
        println("Student has got a name as $name")
    }

    constructor(sectionName: String, var id: Int) this(sectionName) {
    }
}
```


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q14: How are extensions resolved in Kotlin and what doest it mean? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q15: What is a purpose of Companion Objects in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q16: What is Lateinit in Kotlin and when would you use it? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q17: When to use lateinit over lazy initialization in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q18: May you briefly compare Kotlin vs Java? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q19: What are coroutines in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q20: What is the difference between suspending vs. blocking? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q21: What is suspending function in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q22: What is the equivalent of Java static methods in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q23: Explain advantages of "when" vs "switch" in Kotlin ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q24: What are the advantages of Kotlin over Java? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q25: What are some disadvantages of Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q26: What is the difference between "open" and "public" in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q27: What is the difference between “const” and “val”? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q28: How to convert List to Map in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q29: val mutableList vs var immutableList. When to use which in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q30: What is the difference between List and Array types? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q31: What is the idiomatic way to deal with nullable values, referencing or converting them? ⭐⭐⭐

**Questions Details:**

If I have a nullable type `Xyz?`, I want to reference it or convert it to a non-nullable type `Xyz`. What is the idiomatic way of doing so in Kotlin?


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q32: When would you use Elvis operator in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q33: Rewrite this code in Kotlin ⭐⭐⭐

**Questions Details:**

Can you rewrite this Java code in Kotlin?
```java
public class Singleton {
    private static Singleton instance = null;
    private Singleton(){
    }
    private synchronized static void createInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
    }
    public static Singleton getInstance() {
        if (instance == null) createInstance();
        return instance;
    }

```


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q34: What is a difference between a class and object in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q35: How is it recommended to create constants in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q36: May you use IntArray and an Array<Int> is in Kotlin interchangeably? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q37: How would you create a singleton with parameter in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q38: What is the Kotlin double-bang (!!) operator? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q39: What is the purpose of Unit-returning in functions? Why is VALUE there? What is this VALUE? ⭐⭐⭐

**Questions Details:**

Explain what is the purpose of Unit-returning in functions? Why is VALUE there? What is this VALUE?
```kotlin
fun printHello(name : String?) : Unit { 
   if (name != null) 
     print("Hello, $name!") 
   else 
     print("Hi there!") 
   // We don't need to write 'return Unit.VALUE' or 'return', although we could 
}
```


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q40: What are scope functions in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q41: Why would you use apply in Kotlin? ⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q42: How would you refactor this code using "apply"? ⭐⭐⭐

**Questions Details:**

Consider:
```kotlin
class Message(message: String, signature: String) {
  val body = MessageBody()
  
  init {
    body.text = message + "\n" + signature
  }
}
```
Do you see any refactoring that could be done?


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q43: Why is there no static keyword in Kotlin? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q44: What is inline class in Kotlin and when do we need one? Provide an example. ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q45: Provide a real use case when inline classes may be useful ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q46: What is Coroutine Scope and how is that different from Coroutine Context? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q47: Explain the difference between Inline classes vs type aliases ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q48: How would you override default getter for Kotlin data class? ⭐⭐⭐⭐

**Questions Details:**

Given the following Kotlin class:
```kotlin
data class Test(val value: Int)
```
How would I override the Int getter so that it returns `0` if the value negative?


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q49: How can I create “static” method for enum in Kotiln? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q50: How to create an instance of anonymous class of abstract class in Kotlin? ⭐⭐⭐⭐

**Questions Details:**

Assume that `KeyAdapter` is an abstract class with several methods that can be overridden.

In java I can do:
```kotlin
KeyListener keyListener = new KeyAdapter() {
    @Override public void keyPressed(KeyEvent keyEvent) {
        // ...
    }
};
```
How to do the same in Kotlin?


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q51: How to create empty constructor for data class in Kotlin? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q52: What are Object expressions in Kotlin and when to use them? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q53: What is Kotlin backing field is used for? ⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q54: Rewrite this code using "run" extension function  ⭐⭐⭐⭐

**Questions Details:**

Consider:
```kotlin
val generator = PasswordGenerator()
generator.seed = "someString"
generator.hash = {s -> someHash(s)}
generator.hashRepititions = 1000

val password: Password = generator.generate()
```
How would you refactor this code using `run` extension function?


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q55: Explain the difference between lateinit and lazy in details ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q56: What's wrong with that code? ⭐⭐⭐⭐⭐

**Questions Details:**

Let's say I want to override the Int getter so that it returns 0 if the value negative for the data class. What's bad with that approach?

```kotlin
data class Test(private val _value: Int) {
  val value: Int
    get() = if (_value < 0) 0 else _value
}
```


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q57: What is SAM Conversion in Kotlin? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q58: What is the difference between “*” and “Any” in Kotlin generics? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q59: Why do we use “companion object” as a kind of replacement for Java static fields in Kotlin? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q60: Imagine you moving your code from Java to Kotlin. How would you rewrite this code in Kotlin? ⭐⭐⭐⭐⭐

**Questions Details:**

```java
public class Foo {
    private static final Logger LOG = LoggerFactory.getLogger(Foo.class);
}
```


 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q61: How Kotlin coroutines are better than RxKotlin/RxJava? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q62: What is the difference between launch/join and async/await in Kotlin coroutines? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q63: What is a motivation to make classes final by default in Kotlin? Do you agree with that decision? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q64: How does the reified keyword in Kotlin work? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q65: What is The Billion Dollar Mistake? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q66: What is the difference between Java field and Kotlin property? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q67: How to implement Builder pattern in Kotlin? ⭐⭐⭐⭐⭐

 See 👉 **[Answer](https://www.fullstack.cafe/Kotlin)**


### Q68: When to use and do not use an inline function in Kotlin? ⭐⭐⭐⭐⭐

