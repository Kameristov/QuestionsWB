[Назад](/L1/L1_.md) 

## как передать в функцию неограниченное количество переменных разных типов]

для передачи неограниченного количества переменных разных типов можно использовать синтаксис ...тип для параметра функции. 
Это называется "variadic function" или "функция с переменным числом аргументов".

чтобы передавать любой тип используется тип пустого интерфейса или тип any который равен пустому интерфейсу

PrintValues(values ...interface{}) 
PrintValues(values ...any) 

-----------------------------------------------------
В Go для передачи неограниченного количества переменных разных типов можно использовать синтаксис ...тип для параметра функции. Это называется "variadic function" или "функция с переменным числом аргументов".

Вот пример:

go
package main

import "fmt"

func PrintValues(values ...interface{}) {
    for _, value := range values {
        fmt.Println(value)
    }
}

func main() {
    PrintValues(1, "Hello", true, 3.14)
}


В этом примере функция PrintValues принимает параметр values ...interface{}, что означает, что она может принимать любое количество аргументов любого типа. Внутри функции мы используем цикл range для перебора всех переданных аргументов и выводим их на экран.

При выполнении кода будет выведено:


1
Hello
true
3.14


Таким образом, вы можете передавать в функцию PrintValues любое количество аргументов разных типов.

Обратите внимание, что тип аргументов в функции PrintValues является interface{}, что означает, что функция работает с пустым интерфейсом и может принимать значения любого типа. Если вам нужно выполнить какие-то операции с конкретными типами, вам может потребоваться использовать утверждение типа (type assertion) для приведения аргументов к нужному типу.