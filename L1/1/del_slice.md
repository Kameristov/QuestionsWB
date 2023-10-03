[Назад](/L1/L1_.md) 

## удаление i элемента слайса - cap

для удаления элемента из слайса требуется создать новый слайс и в него скопировать все значения кроме элемента который требуется удалить.

следует применять функцию copy
Сначалы 
// Копируем элементы до индекса в новый срез
    newSlice := make([]int, len(slice)-1)
    copy(newSlice, slice[:index])

    // Копируем элементы после индекса в новый срез
    copy(newSlice[index:], slice[index+1:])

У слайса есть параметр cap отвечающий за емкость слайса
Он указыает до скольки элементов можно добавлять в слайс без выделения нового исходного массива большей величины. 

До определенного момента при достижения края емкость новый базовый массива увеличивается в двое

Емкость можно задать при создании массива через make 3 параметром
Также значение емкости можно получить через функцию cap()

-----------------------------------------------------------
Для удаления элемента из среза в Go вы можете использовать функцию copy() и оператор среза.

Вот пример кода, который удаляет элемент из среза:

go
package main

import "fmt"

func main() {
    // Исходный срез
    slice := []int{1, 2, 3, 4, 5}

    // Индекс элемента, который нужно удалить
    index := 2

    // Копируем элементы до индекса в новый срез
    newSlice := make([]int, len(slice)-1)
    copy(newSlice, slice[:index])

    // Копируем элементы после индекса в новый срез
    copy(newSlice[index:], slice[index+1:])

    // Выводим новый срез
    fmt.Println(newSlice)
}


В этом примере мы создали исходный срез slice с элементами [1, 2, 3, 4, 5]. Затем мы указали индекс элемента, который нужно удалить (в данном случае это элемент с индексом 2). Мы создали новый срез newSlice с помощью функции make(), указав длину равную len(slice)-1, чтобы исключить удаленный элемент. Затем мы скопировали элементы до индекса из исходного среза в новый срез с помощью функции copy(). Затем мы скопировали элементы после индекса из исходного среза в новый срез. Наконец, мы вывели новый срез newSlice, который не содержит удаленного элемента.

Обратите внимание, что удаление элемента из среза не изменяет исходный срез. Если вам нужно изменить исходный срез, вы можете присвоить ему значение нового среза:

go
slice = newSlice



---------------------------------------------------------
Вызов     Тип аргумента    Результат

len(s)    string type      длина строки в байтах
          [n]T, *[n]T      длина массива (== n)
          []T              длина среза
          map[K]T          длина карты (количество определенных ключей)
          chan T           количество элементов находящихся в очереди в буфере канала

cap(s)    [n]T, *[n]T      длина массива (== n)
          []T              емкость среза
          chan T           емкость буфера канала