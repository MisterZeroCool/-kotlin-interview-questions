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
  <p class="word">Меньше кода = меньше ошибок, выше скорость разработки.</p>
</details>
</body>

<details>
    <summary>Безопасная работа с обнуляемыми переменными (Null Safety)</summary>
    <br><p class="word">В отличие от Java, в Kotlin по &shy;умолчанию все типы являются non-nullable, то есть не могут принимать значение null. &shy;Присвоение или возврат null приведет к ошибке компиляции. Чтобы присвоить переменной значение null, &shy;в Kotlin необходимо явно пометить эту переменную &shy;как nullable (добавив после типа знак вопроса). В Java же при использовании &shy;ссылки на объект с указанным значением null, появляется исключение &shy;в виде «NullPointerException!».</p> 
</details>

<details>
    <summary>Функции-расширения (Extensions)</summary>
    
    <p>Kotlin позволяет расширять класс путём добавления нового функционала без необходимости наследования от такого класса. Это реализовано с помощью специальных выражений, называемых расширения. Например, вы можете написать новые функции для класса из сторонней библиотеки, которую вы не можете изменить. Такие функции можно вызывать обычным способом, как если бы они были методами исходного класса. Этот механизм называется функцией расширения.</p>
</details>

<details>
    <summary>Классы данных (data classes)</summary>
    
    <p>Разработчику на Java приходится писать много стандартного, но часто встречающегося кода (т.н. шаблонный код или boilerplate). В Kotlin же есть возможность создания специальных классов для определения полей для хранения данных, конструктора, функций сеттеров и геттеров для каждого поля, и функций Hashcode(), toString() и equals(). Для этого достаточно добавить data в определение класса, затем компилятор сделает все сам.</p>
</details>

<details>
    <summary>Синглтоны на уровне языка (Object)</summary>
    
    <p>В Java все должно объявляться внутри класса. Но в Kotlin все иначе. Компоненты могут объявляться за пределами класса, и это автоматически делает их статическими. Поэтому нам не требуется ключевое слово static. В Java статические члены обрабатываются не так, как члены-объекты. Это означает, что для статических членов нам недоступны такие вещи, как реализация интерфейса, помещение экземпляра в ассоциативный список (map) или передача его в качестве параметра методу, который принимает объект. В Kotlin static не является ключевым словом и вместо статических членов используются объекты-компаньоны, позволяющие преодолеть вышеуказанные ограничения. В этом и заключается преимущество. Даже если члены объектов-компаньонов выглядят как статические члены в других языках, во время выполнения они все равно остаются членами экземпляров реальных объектов и могут, например, реализовывать интерфейсы.</p>
</details>

<details>
    <summary>Корутины</summary>
    
    <p>Kotlin предоставляет возможность создавать дополнительные потоки, однако в нем также существуют т.н. корутины (сопрограммы), которые позволяют использовать меньше памяти в сравнении с обычным потоком, т.к. реализованы они без стека. Корутины же в свою очередь способны выполнять интенсивные и длительные задачи методом приостановления выполнения без блокировки потока и его последующего восстановления. Что в дальнейшем позволяет сгенерировать асинхронный код без блокирования, который при его выполнении не отличить от синхронного. К тому же, они генерируют эффектные доп.стили например async или await.</p>
</details>
</body>
