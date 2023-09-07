# ?Media query

~~~
<link rel="stylesheet" type="text/css" href="desktop.css" />
<link rel="stylesheet" type="text/css" media="(max-device-width:480px)" href="mobile.css" />
~~~

С помощью ключевого слова `and` можно комбинировать условия, например:

~~~
<link rel="stylesheet" type="text/css" media="(min-width:481px) and (max-width:768px)" href="mobile.css" />
~~~

Также можно не разлелять стили по файлам, а использовать правила CSS3 Media Query в одном файле css:

~~~
@media (max-device-width:480px){
  body {
    background-color: blue;
  }
  /*Далее остальные стили*/
}
~~~

Применяемые функции в CSS3 Media Query:

* `aspect-ratio`: отношение ширины к высоте области отображения (браузера)
* `device-aspect-ratio`: отношение ширины к высоте экрана устройства
* `max-width`/`min-width` и `max-height`/`min-height`: максимальная и минимальная ширина и высота области отображения (браузера)
* `max-device-width`/`min-device-width` и `max-device-height`/`min-device-height`: максимальная и минимальная ширина и высота экрана мобильного устройства
* `orientation`: ориентация (портретная или альбомная)

Типы носителей:

* `all`.	Все типы. Это значение используется по умолчанию.
* `print`. Принтеры и другие печатающие устройства.
* `projection`. Проекторы.
* `screen`. Экран монитора.
* `speech`.	Речевые синтезаторы, а также программы для воспроизведения текста вслух. Сюда, например, можно отнести речевые браузеры.

~~~
@media screen and (min-width: 480px) {
  body {
    background-color: lightgreen;
  }
}
~~~

Вы можете использовать список, разделенный запятыми, чтобы применять стили, когда устройство пользователя соответствует любому из различных типов мультимедиа, функций или состояний. Например, следующее правило будет применять свои стили, если устройство пользователя имеет минимальную высоту `680` пикселей или является устройством с экраном в портретном режиме:

~~~
@media (min-height: 680px), screen and (orientation: portrait) {
  /* … */
}
~~~
