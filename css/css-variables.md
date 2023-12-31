# ?CSS variables

Переменные CSS имеют доступ к DOM, а это означает, что вы можете создавать переменные с локальной или глобальной областью действия, изменять переменные с помощью JavaScript и изменять переменные на основе медиа-запросов.

Обратите внимание, что селектор, заданный набору правил, определяет область, в которой может использоваться настраиваемое свойство. Обычно рекомендуется определять настраиваемые свойства в псевдоклассе `:root`, чтобы их можно было применять глобально во всем HTML-документе:

~~~
:root {
  --blue: #1e90ff;
  --white: #ffffff;
}

.container {
  color: var(--blue);
  background-color: var(--white);
  padding: 15px;
}
~~~

Функция `var()` используется для вставки значения переменной CSS.

Синтаксис функции `var()` следующий:

~~~
var(--name, value)
~~~

* `name`. Обязательно. Имя переменной (должно начинаться с двух тире).
* `value`. Необязательно. Резервное значение (используется, если переменная не найдена).

Преимущества использования `var()`:

* делает код более читаемым (более понятным)
* значительно упрощает изменение значений цвета

Чтобы изменить сине-белый цвет на более мягкий сине-белый, вам просто нужно изменить значения двух переменных.
