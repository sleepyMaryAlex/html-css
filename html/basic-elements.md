# ?Basic elements

* `<body>` - является контейнером для всех отображаемых аспектов документа, таких как заголовки, абзацы, изображения, гиперссылки, таблицы, списки и т. д. В документе HTML может быть только один элемент `body`.
* `<div>` - простая строка.
* `<br/>` - перенос строки, пустой элемент. Тег `<br>` пригодится для написания адресов или стихов.

~~~
<p>Be not afraid of greatness.<br>
Some are born great,<br>
some achieve greatness,<br>
and others have greatness thrust upon them.</p>
~~~

Не используйте `<br>` для создания margins между параграфами; оберните их элементами `<p>` и используйте свойство CSS `margin` для управления их размером.

* `<hr/>` - рисует линию между строчек.
* `<p>` - параграф, переносит текст через строку. Блочный элемент. Нельзя вкладывать параграфы друг в друга.
* `<pre>` - выводит текст так, как от определен в коде в Visual Studio со всеми пробелами. Внутри него можно использовать другие теги.
* `<code>` - Для создания блока с кодом, внутри которого записывается код на любом языке программирования. Тег `<code>` часто используют вместе с тегом `<pre>`, что позволяет сохранить форматирование. Если тег `<pre>` не используется, то переносы строк нужно контролировать самостоятельно, например, оборачивая каждую строку в тег `<p>`.

Если мы хотим вывести код html на страницу, то важно чтобы браузер не обработал теги. Можно сделать так:

~~~
<code>
  <<span>p</span>>Вставляем тег p в виде простого текста <<span>/p</span>>
</code>
~~~

* `<span>` - служит для стилизации заключенного в него текстового содержимого.

~~~
<p><span style="color:red;">Первый</span> параграф</p>
~~~

* `<h1>`-`<h6>` - заголовки разного размера. `h1` - самый большой.
* `<source>` - используется для указания нескольких медиа-ресурсов для медиа-элементов, таких как `<video>`, `<audio>` и `<picture>`. Тег `<source>` позволяет указать альтернативные файлы видео/аудио/изображений, которые браузер может выбирать в зависимости от поддержки браузера или ширины области просмотра. Браузер выберет первый, `<source>` который он поддерживает.

~~~
<picture>
  <source srcset="image1.jpg" media="(min-width: 1000px)" />
  <source srcset="image2.jpg" media="(min-width: 750px)" />
  <img src="image3.jpg" />
</picture>
~~~

Он отображает `image1.jpg` с разрешением 1000 пикселей и выше, `image2.jpg` с разрешением 750–999 пикселей и `image3.jpg` с разрешением 749 пикселей и ниже.

* `<q>` - определяет короткую цитату. Браузеры обычно заключают цитату в кавычки.
* `<cite>` - определяет название творческого произведения (например, книги, стихотворения, песни, фильма, картины, скульптуры и т. д.). Текст в `<cite>` обычно отображается курсивом.

~~~
<p><cite>The Scream</cite> by Edward Munch. Painted in 1893.</p>
~~~

* `<blockquote>` - указывает раздел, цитируемый из другого источника.
* `<picture>` - содержит два тега: один или несколько тегов `<source>` и один тег `<img>`.
* `<abbr>` - определяет аббревиатуру или акроним. Используйте атрибут `title`, чтобы отобразить описание аббревиатуры при наведении курсора мыши на элемент.
* `<kbd>` - используется для определения ввода с клавиатуры. Содержимое внутри отображается моноширинным шрифтом браузера по умолчанию.
* `<canvas>` - используется для рисования графики на лету с помощью JavaScript.
* `<svg>` - определяет контейнер для графики SVG. `<svg>` производит векторную графику и `<canvas>` производит растровую графику.
* `<noscript>` - отображается, когда JavaScript не поддерживается браузером или если JavaScript отключен в браузере.
* `<meter>` - определяет скалярное измерение в известном диапазоне или дробное значение.

~~~
<label for="disk_c">Disk usage C:</label>
<meter id="disk_c" value="2" min="0" max="10">2 out of 10</meter>
~~~

* `<data>` - позволяет авторам предоставлять машиночитаемую версию своего содержимого. Такая кодификация должна быть предусмотрена в обязательном атрибуте `value`.

~~~
<ul>
  <li><data value="21053">Cherry Tomato</data></li>
  <li><data value="21054">Beef Tomato</data></li>
  <li><data value="21055">Snack Tomato</data></li>
</ul>
~~~

* `<circle>` - используется для создания круга.

~~~
<svg height="100" width="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
~~~

Обратно совместимый метод превращения круга в SVG в ссылку:

~~~
<svg id="circle">
  <a xlink:href="https://www.google.com" style="cursor: pointer" target="_blank">
    <circle  cx="125" cy="70" r="60" stroke="darkblue" stroke-width="3" fill="green" />
  </a>
</svg>
~~~

* `<script>` - используется для встраивания клиентского скрипта (JavaScript). Когда браузер загружает HTML и встречает `<script>...</script>`, он не может продолжить построение DOM. Он должен выполнить скрипт прямо сейчас. То же самое происходит и с внешними скриптами `<script src="..."></script>`. Есть несколько обходных путей. Например, мы можем разместить скрипт внизу страницы. Тогда он сможет видеть элементы над ним и не блокирует отображение содержимого страницы. Но это решение далеко от совершенства. Например, браузер замечает скрипт (и может начать его загрузку) только после того, как загрузит полный HTML-документ. К счастью, есть два `<script>` атрибута, которые решают для нас проблему: `defer` и `async`. Атрибут `defer`: cкрипт загружается «в фоновом режиме», а затем запускается, когда DOM полностью построен. Атрибут `async`: скрипты загружаются в фоновом режиме и запускаются по мере готовности. `type="module"` подразумевает `defer`.

~~~
<script src="file.js">
  alert(1); // так как указан src, то внутренняя часть тега игнорируется
</script>
~~~

* `<samp>`: используется для отображения текста, который является результатом вывода компьютерной программы или скрипта. Браузеры обычно отображают текст в контейнере `<samp>` с помощью моноширинного шрифта.
* `<wbr>`:  указывает, где в тексте можно добавить разрыв строки. Если слово слишком длинное, браузер может прервать его в неправильном месте. Вы можете использовать `<wbr>`, чтобы добавить возможность разрыва слов.

~~~
<p>To learn AJAX, you must be familiar with the XML<wbr>Http<wbr>Request Object.</p>
~~~