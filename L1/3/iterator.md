# [Назад](/L1/L1_.md)

## как из функции сделать итератор для for (как итерироваться по функции)

### Ответ

Функция должна возвращать итерируемый объект (канал, слайс, мапа, массив и тд.)

-----------------------------------------------------

Пример

```go
package main

import (
    "fmt"
)

func main() {
    for _, val := range FuncIterator() {
        fmt.Println(val)
    }

}

func FuncIterator() []int {
    return []int{1, 2, 3, 4, 5}
}
```

```cmd
Ответ:
1
2
3
4
5
```

-----------------------------------------------------

Также можно через структуру с методами. В улсовии `for` метод возвращает `bool` значение

```go
package main

import (
    "fmt"
)

type MyIterator struct {
    data  []int
    index int
}

func (it *MyIterator) Next() (interface{}, bool) {
    if it.index >= len(it.data) {
        return nil, false
    }
    value := it.data[it.index]
    it.index++
    return value, true
}

func (it *MyIterator) HasNext() bool {
    return it.index < len(it.data)
}

func NewIterator(data []int) *MyIterator {
    return &MyIterator{
        data:  data,
        index: 0,
    }
}

func main() {
    data := []int{1, 2, 3, 4, 5}
    iterator := NewIterator(data)

    for iterator.HasNext() {
        value, _ := iterator.Next()
        fmt.Println(value)
    }
}
```
