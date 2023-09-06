# ?Gradients

### linear-gradient

Функция CSS `linear-gradient()` создает изображение, состоящее из постепенного перехода между двумя или более цветами по прямой линии.

~~~
background: linear-gradient(#e66465, #9198e5);
background: linear-gradient(0.25turn, #3f87a6, #ebf8e1, #f69d3c);
background: linear-gradient(to left, #333, #333 50%, #eee 75%, #333 75%);
background: linear-gradient(217deg, rgba(255,0,0,.8), rgba(255,0,0,0) 70.71%),
            linear-gradient(127deg, rgba(0,255,0,.8), rgba(0,255,0,0) 70.71%),
            linear-gradient(336deg, rgba(0,0,255,.8), rgba(0,0,255,0) 70.71%);
~~~

С помощью `repeating-linear-gradient` можно создавать повторяющиеся линейные градиенты. Например:

~~~
background: repeating-linear-gradient(45deg, #3f87a6, #ebf8e1 15%, #f69d3c 20%);
~~~

### radial-gradient

`radial-gradient` создает изображение, состоящее из постепенного перехода между двумя или более цветами, исходящими от источника. Его форма может быть кругом или эллипсом.

~~~
background: radial-gradient(#e66465, #9198e5);
background: radial-gradient(closest-side, #3f87a6, #ebf8e1, #f69d3c);
background: radial-gradient(circle at 100%, #333, #333 50%, #eee 75%, #333 75%);
background: radial-gradient(ellipse at top, #e66465, transparent),
            radial-gradient(ellipse at bottom, #4d9f0c, transparent);
~~~
