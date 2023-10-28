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
  <img src="https://camo.githubusercontent.com/fb9f8045c2a49eec15a7608a6dcac8928a9f92e45bebab3619c9bec17a443c1a/68747470733a2f2f322e62702e626c6f6773706f742e636f6d2f2d45696763415342354b37492f5735373454727a357461492f41414141414141414150452f326967686d464c58576334543679386a6f62595f4c6f4271756930537549364177434c63424741732f73313630302f4b656c6c616e253235324241742532353242576f726b2e676966">
  </a>
</p>


### Q1: Преимущества языка Kotlin перед Java?


<body>
<details>
    <summary>Код на Kotlin компактнее на 30-40%</summary>
    <p><i>Меньше кода = меньше ошибок, выше скорость разработки.</i></p>
</details>

<details>
    <summary>Безопасная работа с обнуляемыми переменными (Null Safety)</summary>
    <p><i>В отличие от Java, в Kotlin по умолчанию все типы являются non-nullable, &shy;то есть не могут принимать значение null. Присвоение или возврат null приведет к ошибке &shy;компиляции. Чтобы присвоить переменной значение null, в Kotlin необходимо явно пометить &shy;эту переменную как nullable (добавив после типа знак вопроса). В Java же при использовании &shy;ссылки на объект с указанным значением null, появляется исключение в виде «NullPointerException!».</i></p>
</details>

<details>
    <summary>Функции-расширения (Extensions)</summary>
    <p><i>
    Kotlin позволяет расширять класс путём добавления нового функционала без необходимости &shy;наследования от такого класса. Это реализовано с помощью &shy;специальных выражений, называемых расширения. Например, &shy;вы можете написать новые функции для класса из сторонней библиотеки, которую вы не можете &shy;изменить. Такие функции можно вызывать обычным способом, как если бы они были методами &shy;исходного класса. Этот механизм называется функцией расширения.</i></p>
</details>

<details>
    <summary>Классы данных (data classes)</summary>
    <p><i>
    Разработчику на Java приходится &shy;писать много стандартного, но часто встречающегося кода (т.н. шаблонный &shy;код или boilerplate). В Kotlin же есть возможность создания специальных классов для определения полей для &shy;хранения данных, конструктора, функций сеттеров и геттеров для каждого поля, и функций Hashcode(), toString() и equals(). Для этого &shy;достаточно добавить data в определение класса, затем компилятор сделает все сам.</i></p>
</details>

<details>
    <summary>Синглтоны на уровне языка (Object)</summary>
    <p><i>В Java все должно объявляться внутри класса. Но в Kotlin все иначе. Компоненты могут объявляться за &shy;пределами класса, и это автоматически делает их статическими. Поэтому нам не требуется ключевое слово static. &shy;В Java статические члены обрабатываются не так, как члены-объекты. Это означает, что &shy;для статических членов нам недоступны такие вещи, как реализация интерфейса, &shy;помещение экземпляра в ассоциативный список (map) или передача его в качестве параметра методу, &shy;который принимает объект. В Kotlin static не является ключевым словом и вместо статических &shy;членов используются объекты-компаньоны, позволяющие преодолеть вышеуказанные &shy;граничения. В этом и заключается преимущество. Даже если члены объектов-компаньонов &shy;выглядят как статические члены в других языках, во время выполнения они все равно остаются членами &shy;экземпляров реальных объектов и могут, например, реализовывать интерфейсы.</i></p>
</details>

<details>
    <summary>Корутины</summary>
    <p class="word"><i>Kotlin предоставляет возможность создавать дополнительные потоки, однако в нем также существуют т.н. корутины (сопрограммы), которые &shy;позволяют использовать меньше памяти в сравнении с обычным потоком, т.к. реализованы они без стека. Корутины же в свою очередь способны выполнять &shy;интенсивные и длительные задачи методом приостановления выполнения без блокировки &shy;потока и его последующего восстановления. Что в дальнейшем позволяет сгенерировать &shy;асинхронный код без блокирования, который при его выполнении не отличить от синхронного. &shy;К тому же, они генерируют эффектные доп.стили например async или await.</i></p>
</details>

<details>
    <summary>Разница между Exception в Java и Kotlin</summary>
    <p class="word"><i>Одним из ключевых отличий между Java и Kotlin является подход к исключениям. &shy;В Java есть два типа исключений: checked и unchecked.

&shy;Checked исключения это те, которые должны быть обработаны в коде, иначе компилятор не позволит коду скомпилироваться. Unchecked исключения не требуют обработки в коде.

&shy;С точки зрения исключений компилятор Kotlin отличается тем, что не различает checked и unchecked исключения. Все исключения — только unchecked, &shy;поэтому нет необходимости отлавливать или объявлять какие-либо исключения &shy;(вы самостоятельно принимаете решение, стоит ли их отлавливать и обрабатывать).

&shy;Такой подход был выбран разработчиками Kotlin, чтобы упростить и &shy;ускорить процесс разработки, сократив количество бойлерплейта и улучшив &shy;читаемость кода. Однако, это может привести к тому, что некоторые ошибки &shy;могут быть упущены при компиляции и проявиться только во время выполнения программы.

&shy;Некоторые разработчики считают, что отказ от checked исключений является недостатком Kotlin, поскольку это может привести к ошибкам, &shy;которые могут быть предотвращены на этапе компиляции в Java. Однако, &shy;другие разработчики утверждают, что этот подход снижает количество шаблонного кода и &shy;упрощает написание программ.</i></p>
</details>

<details>
    <summary>Как перенести статичные методы из Java в Kotlin?</summary>
    <p class="word"><i>В Kotlin нет статических методов, для этих целей обычно служит companion object.
Для того чтобы метод из Java был представлен как статический используется аннотация @JvmStatic. Эта аннотация говорит компилятору Kotlin создать статический метод в байт-коде, что позволяет использовать методы так же, как в Java.

Например, если у нас есть статический метод в Java:
```java
public class MyClass {
    public static int sum(int a, int b) {
        return a + b;
    }
}

Мы можем использовать этот метод в Kotlin, добавив аннотацию @JvmStatic:
```kotlin
object MyClass {
    @JvmStatic
    fun sum(a: Int, b: Int): Int {
        return a + b
    }
}</i></p>
</details>
