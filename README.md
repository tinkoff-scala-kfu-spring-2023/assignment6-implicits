# Implicits in Scala

Вам дана базовая реализация комплексных чисел. 
```scala
final case class ComplexNumber(real: Double, imaginary: Double) {
  def *(other: ComplexNumber) =
    ComplexNumber(
      (real * other.real) + (imaginary * other.imaginary),
      (real * other.imaginary) + (imaginary * other.real)
    )
  def +(other: ComplexNumber) =
    ComplexNumber(real + other.real, imaginary + other.imaginary)
  def ~=(o: ComplexNumber) = 
    (real - o.real).abs < 1e-6 && (imaginary - o.imaginary).abs < 1e-6 
}
final object ComplexNumber
```

Ваша задача добавить функционал к этой реализации с запретом изменять исходный код класса и его объекта-компаньона, вам так же запрещено наследоваться от этого класса (final), запрещено использовать паттерны из Java (например, декоратор).

1. Добавить операции вычитания и деления (тут можно кидать нужный runtime exception), а также полярную форму для каждого инстанса класса `ComplexNumber`.
1. Добавить возможность использовать все методы с числовыми типами ([Numeric](https://www.scala-lang.org/api/2.13.10/scala/math/Numeric.html)).
1. Добавить возможность создавать комплексные числа при помощи специального синтаксиса, напоминающего алгебраическое представление комплексных чисел `z = a + bi`.

Тесты для этого домашнего задания писать не нужно. 
