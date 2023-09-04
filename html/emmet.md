# ?Emmet

_Emmet_ использует синтаксис для описания позиций элементов внутри сгенерированного дерева и атрибутов элементов.

### Вложенные операторы

Вы можете использовать оператор `>` для вложения элементов друг в друга:

~~~
div>ul>li + TAB

<div>
  <ul>
    <li></li>
  </ul>
</div>
~~~

Используйте оператор `+`, чтобы разместить элементы рядом друг с другом, на одном уровне:

~~~
div+p+bq

<div></div>
<p></p>
<blockquote></blockquote>
~~~

С помощью оператора `^` вы можете подняться на один уровень вверх по дереву и изменить контекст, в котором должны появиться следующие элементы:

~~~
div+div>p>span+em^bq

<div></div>
<div>
  <p><span></span><em></em></p>
  <blockquote></blockquote>
</div>
~~~

С помощью оператора `*` вы можете определить, сколько раз элемент должен выводиться:

~~~
ul>li*5

<ul>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ul>
~~~

Круглые скобки используются для группировки поддеревьев в сложных сокращениях:

~~~
div>(header>ul>li*2>a)+footer>p

<div>
  <header>
    <ul>
      <li><a href=""></a></li>
      <li><a href=""></a></li>
    </ul>
  </header>
  <footer>
    <p></p>
  </footer>
</div>
~~~

### Операторы атрибутов

Id и class:

~~~
div#header+div.page+div#footer.class1.class2.class3

<div id="header"></div>
<div class="page"></div>
<div id="footer" class="class1 class2 class3"></div>
~~~

Пользовательские атрибуты:

~~~
td[title="Hello world!" colspan=3]

<td title="Hello world!" colspan="3"></td>
~~~

Нумерация позиций `$`:

~~~
ul>li.item$*5

<ul>
  <li class="item1"></li>
  <li class="item2"></li>
  <li class="item3"></li>
  <li class="item4"></li>
  <li class="item5"></li>
</ul>
~~~

### Текст `{}`

~~~
a{Click me}

<a href="">Click me</a>
~~~

### How to use Emmet

~~~
nav>ul>li*3>a.chapter{Chapter $ of 3}

<nav>
  <ul>
    <li><a href="" class="chapter">Chapter 1 of 3</a></li>
    <li><a href="" class="chapter">Chapter 2 of 3</a></li>
    <li><a href="" class="chapter">Chapter 3 of 3</a></li>
  </ul>
</nav>
~~~
