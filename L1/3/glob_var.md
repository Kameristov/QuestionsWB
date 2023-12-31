[Назад](/L1/L1_.md) 

## переменная созданная в init() глобальная?

Нет, ее область видимости ограничивается функцией init()

созданная переменная в init()  локальна  в init()

init() может менять все переменные в пакете -> может менять переменные для других пакетов

----------------------------------------------------------------


Переменная, созданная в функции `init()`, не является глобальной, но она имеет пакетную область видимости. Это означает, что переменная, объявленная в `init()`, будет видима только в пределах текущего пакета.

Функция `init()` в Go используется для инициализации множества пакетов. Она выполняется автоматически перед выполнением функции `main()` или ее эквивалента в тестовом пакете. 

Когда функция `init()` выполняется, все переменные, объявленные внутри нее, будут доступны только внутри пакета. Они не будут доступны в других пакетах или файловых областях видимости, за исключением тех, которые являются экспортируемыми (начинаются с заглавной буквы).

Вот пример:

```go
package main

import "fmt"

var globalVariable int

func init() {
    // Инициализация переменной внутри init()
    globalVariable = 42
}

func main() {
    fmt.Println(globalVariable) // будет выведено значение 42
}
```

В этом примере переменная `globalVariable` объявлена вне функции `init()` и имеет пакетную видимость. Функция `init()` используется для инициализации этой переменной, и затем значение переменной может быть использовано внутри функции `main()` или в других функциях пакета, если они имеют доступ к переменной.

Важно отметить, что переменная, объявленная внутри функции `init()`, не является глобальной переменной, так как ее область видимости ограничена пакетом, что может быть полезным для контроля доступа к переменной внутри пакета.


---------------------
