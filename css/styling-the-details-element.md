# ?Styling the details element

`details` представляет раскрываемый блок.

`details[open] > summary` - стилизация в раскрытом виде.

По умолчанию элемент `summary` в качестве маркера скрытости/раскрытости использует символ треугольника. Но его также можно настроить. Для настройки изображения маркера можно использовать свойство `list-style`, а также дополнительные свойства типа `list-style-type` или `list-style-image`, которые применяются для стилизации списков.

Но естественно свойством `list-style` мы не ограничены и по своему усмотрению можем более тонко управлять заголовком, например, с помощью свойства `content`.

~~~
summary:before {
  content: "+";
}

details[open] summary:before {
  content: "-";
}
~~~