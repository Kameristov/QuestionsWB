[Назад](/L1/L1_.md)

## реализация типа данных Куча в го

Пример:

```
type node struct{
    value int
    leftChild *node
    rightChild *node
}
```

Через массив :
в порядке с сверху вниз, с лева на право.

![Alt text](<pasted image 0.png>)

Превращается в:

![Alt text](<pasted image 0-1.png>)
