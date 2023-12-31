[Назад](/L1/L1_.md) 

## массив указателей наполняется через _, data := range


Например, если у вас есть массив указателей и вы хотите заполнить его значениями из другого массива, вы можете использовать _ для игнорирования индекса, а data для получения значения элемента:

go
var arr []*int
otherArr := []int{1, 2, 3, 4, 5}

for _, data := range otherArr {
    // создаем новый указатель на int и присваиваем ему значение элемента
    ptr := new(int)
    *ptr = data
    
    // добавляем указатель в массив
    arr = append(arr, ptr)
}


С помощью range проходим по всему масиву получая значения
затем создаем с помоощью оператора new указатель на тип данных
Через вязтие значения по указателю записываем значение масива в значение указателя
Добавляем указатель в массив указателей



-----------------------------------------------------------
В языке Go оператор _ используется для игнорирования значения, которое возвращается при итерации по массиву или срезу. Это может быть полезно, когда вам не нужно использовать значение элемента массива или среза.

Например, если у вас есть массив указателей и вы хотите заполнить его значениями из другого массива, вы можете использовать _ для игнорирования индекса, а data для получения значения элемента:

go
var arr []*int
otherArr := []int{1, 2, 3, 4, 5}

for _, data := range otherArr {
    // создаем новый указатель на int и присваиваем ему значение элемента
    ptr := new(int)
    *ptr = data
    
    // добавляем указатель в массив
    arr = append(arr, ptr)
}


В этом примере мы игнорируем индекс элемента массива otherArr с помощью _, а значение элемента сохраняем в переменную data. Затем мы создаем новый указатель на int, присваиваем ему значение data и добавляем его в массив arr.

Таким образом, использование _ вместе с data := range позволяет заполнить массив указателей значениями из другого массива, игнорируя индексы.
