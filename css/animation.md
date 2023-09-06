# ?Animation

При анимации мы можем иметь не только два набора значений - начальные и конечные, но и множество промежуточных наборов значений.

~~~
@keyframes backgroundColorAnimation {
  from {
    background-color: red;
  }
  25% {
    background-color: yellow;
  }
  50% {
    background-color: green;
  }
  75% {
    background-color: blue;
  }
  to {
    background-color: violet;
  }
}

div {     
  animation-name: backgroundColorAnimation;
  animation-duration: 2s;
}
~~~

Имеет те же свойства, что и `transition`.

Свойство `animation-iteration-count` определяет, сколько раз будет повторяться анимация. Если необходимо, чтобы анимация запускалась бесконечное количество раз, то этому свойству присваивается значение `infinite`:

~~~
animation-iteration-count: infinite;
~~~

С помощью свойства `animation-direction: alternate;` противоположное направление анимации при повторе.

Свойство `animation-fill-mode: forwards` позволяет в качестве окончательного значения анимируемого свойства установить именно то, которое было в последнем кадре.

`animation` это shorthand для:

* `animation-name`
* `animation-duration`
* `animation-timing-function`
* `animation-delay`
* `animation-iteration-count`
* `animation-direction`
* `animation-fill-mode`
* `animation-play-state`
