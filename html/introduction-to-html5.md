# ?Introduction to HTML5

_HTML (HyperText Markup Language)_ представляет язык разметки гипертекста, используемый преимущественно для создания документов в сети интернет. HTML структурирует веб-страницу, определяя ее элементы, такие как абзацы, заголовки и списки.

### Элементы и атрибуты HTML5

Документ HTML5, как и любой документ HTML, состоит из элементов, а элементы состоят из тегов. Как правило, элементы имеют открывающий и закрывающий тег, которые заключаются в угловые скобки. Например:

~~~
<div>Текст элемента div</div>
~~~

Элементы также могут состоять из одного тега, например, элемент `<br />`, функция которого - перенос строки.

~~~
<div>Текст <br /> элемента div</div>
~~~

Такие элементы еще называют пустыми элементами (void elements). Хотя я использовал закрывающий слеш, но его наличие согласно спецификации необязательно, и равнозначно использованию тега без слеша: `<br>`.

Каждый элемент внутри открывающего тега может иметь атрибуты. Например:

~~~
<div style="color:red;">Кнопка</div>
~~~

Элемент `div` имеет атрибут `style`. После знака равно в кавычках пишется значение атрибута: `style="color:red;"`.

Существуют глобальные или общие для всех элементов атрибуты, как например, `style`, а есть специфические, применяемые к определенным элементам, как например, `type`.

Кроме обычных атрибутов существуют еще булевые или логические атрибуты (boolean attributes). Подобные атрибуты могут не иметь значения. Например, у кнопки можно задать атрибут `disabled`:

~~~
<input type="button" value="Нажать" disabled>
~~~

__Порядок атрибутов не имеет значения.__

#### Глобальные атрибуты

В HTML5 есть набор глобальных атрибутов, которые применимы к любому элементу HTML5:

* `accesskey`: определяет клавишу для быстрого доступа к элементу

~~~
<button accesskey="s">Stress reliever</button>
~~~

* `class`: задает класс CSS, который будет применяться к элементу
* `contenteditable`: определяет, можно ли редактировать содержимое элемента
* `contextmenu`: определяет контекстное меню для элемента, которое отображается при нажатии на элемент правой кнопкой мыши
* `dir`: устанавливает направление текста в элементе
* `draggable`: определяет, можно ли перетаскивать элемент
* `dropzone`: определяет, можно ли копировать переносимые данные при переносе на элемент
* `hidden`: скрывает элемент
* `id`: уникальный идентификатор элемента. На веб-странице элементы не должны иметь повторяющихся идентификаторов
* `lang`: определяет язык элемента

~~~
<p lang="fr">Ceci est un paragraphe.</p>
~~~

* `spellcheck`: указывает, будет ли для данного элемента использоваться проверка правописания
* `style`: задает стиль элемента
* `tabindex`: определяет порядок, в котором по элементам можно переключаться с помощью клавиши TAB
* `title`: устанавливает дополнительное описание для элемента
* `translate`: определяет, должно ли переводиться содержимое элемента
* `itemscope`: задаёт область действия словаря в структуре данных. Как правило, работает совместно с атрибутом `itemtype` и задаёт пределы, где `itemtype` будет активен.
* `itemprop`: используется для добавления свойств словаря микроданных к элементу.

~~~
<div itemscope itemtype="http://schema.org/Movie">
  <h1 itemprop="name">Аватар</h1>
  <span>Режиссер: <span itemprop="director">Джеймс Кэмерон</span> (род. 16 августа 1954 г.)</span>
  <span itemprop="genre">Фантастика</span>
  <a href="https://youtu.be/0AY1XIkX7bY" itemprop="trailer">Трейлер</a>
</div>
~~~

Но, как правило, из всего этого списка наиболее часто используются три: `class`, `id` и `style`.

#### Специфические атрибуты

* `type`: указывает на тип элемента. Например, кнопка 
* `value`: определяет текст кнопки
* `name`: идентификация

#### Пользовательские атрибуты

Разработчик или создатель веб-страницы сам может определить любой атрибут, предваряя его префиксом `data-`.

~~~
<input type="button" value="Нажать" data-color="red" >
~~~

#### Одинарные или двойные кавычки

Нередко можно встретить случаи, когда в html при определении значений атрибутов применяются как одинарные, так и двойные кавычки. И одинарные, и двойные кавычки в данном случае допустимы, хотя чаще применяются именно двойные кавычки.

### Создание документа HTML5

~~~
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Документ HTML5</title>
  </head>
  <body>
    <div>Содержание документа HTML5</div>
  </body>
</html>
~~~

Для создания документа HTML5 нам нужны в первую очередь два элемента: `DOCTYPE` и `html`. Элемент `doctype` или Document Type Declaration сообщает веб-браузеру тип документа. `<!DOCTYPE html>` указывает, что данный документ является документом `html` и что используется `html5`, а не `html4` или какая-то другая версия языка разметки.

Внутри элемента `html` мы можем разместить два других элемента: `head` и `body`. Элемент `head` содержит метаданные веб-страницы - заголовок веб-страницы, тип кодировки и т.д., а также ссылки на внешние ресурсы - стили, скрипты, если они использутся. Элемент `body` собственно определяет содержимое html-страницы.

> `Метаданные` – это короткие текстовые описания, используемые для индексации и нахождения информации.

`<html>` является корневым элементом HTML-документа, что означает, что он содержит все содержимое и теги HTML-документа.

### Разновидности синтаксиса HTML5

Стиль HTML предполагает следующие моменты:

* Начальные открывающие теги могут отсутствовать у элементов
* Конечные закрывающие теги могут отсутствовать у элементов
* Только пустые элементы (void elements) (например, `br`, `img`, `link`) могут закрываться с помощью слеша `/>`
* Регистр названий тегов и атрибутов не имеет значения
* Можно не заключать значения атрибутов в кавычки
* Некоторые атрибуты могут не иметь значений (`checked` и `disabled`)
* Специальные символы не экранируются
* Документ должен иметь элемент `DOCTYPE`

Если же возникают затруднения, насколько правильной является создаваемая разметка `html`, то ее можно проверить с помощью валидатора по адресу https://validator.w3.org

Тег `<! -- -->` используется для написания комментария в коде HTML документа:

~~~
<!-- this is a comment -->
~~~

### Void elements

Для разметки, например, `hr` элемента разрешены оба следующих действия:

~~~
<hr>
<hr/>
~~~

Но завершающая косая черта на элементах `void` не имеет никакого эффекта и плохо взаимодействует со значениями атрибутов, не заключенными в кавычки.

`img` элемент без косой черты:

~~~
<img alt=SVG src=http://www.example.com/logo.svg>
~~~

`img` элемент с косой чертой в конце:

~~~
<img alt=SVG src=http://www.example.com/logo.svg/>
~~~

В первом случае (без косой черты) `http://www.example.com/logo.svgстановится` значением атрибута `src` в DOM, как и ожидалось.

Однако во втором случае (с косой чертой) `http://www.example.com/logo.svg/` неожиданно становится значением атрибута `src` в DOM — что нарушает отображение изображения.

### WAI-ARIA

Роли ARIA придают контенту семантическое значение.

По умолчанию многие семантические элементы HTML имеют определенную роль; например, `<input type="radio">` имеет роль "radio". Несемантические элементы в HTML не играют никакой роли. Атрибут `role` может предоставлять семантику.

~~~
<ul role="tabpanel">
~~~

Атрибут `aria-label` следует использовать для предоставления текстовой альтернативы элементу, у которого нет видимого текста на экране.

~~~
<button aria-label="menu" class="burger"></button>
~~~


Атрибут `aria-labeledby` используется для создания связей между объектами и их метками.

~~~
<span role="checkbox" aria-checked="false" tabindex="0" aria-labelledby="tac"></span>
<span id="tac">I agree to the Terms and Conditions.</span>
~~~

Атрибут `aria-describedby` перечисляет `id` элементов, описывающие объект.

~~~
<button aria-describedby="trash-desc">Move to trash</button>
…
<p id="trash-desc">
  Items in the trash will be permanently removed after 30 days.
</p>
~~~

Будьте осторожны при использовании атрибутов `aria-label`, `aria-labelledby` и `aria-describedby`, поскольку они не работают согласованно со всеми элементами HTML.

Атрибуты `aria-label`, `aria-labelledby` и `aria-describedby` можно использовать с:

* интерактивные элементы
* элементы, которые имеют роль – либо неявно (`header`, `footer`, `main`, `nav`, `aside`, `section` и `form`), либо явно заданные через атрибут `role`
* `iframe` и `img` элементы

### Необязательные закрывающие теги

| Тег |	Когда можно не писать |
|---|---|
| `</html>`	| Если после него не идет <!-- комментарий --> |
| `</head>`	| Если после него не идет <!-- комментарий --> или пробел |
| `</body>`	| Если после него не идет <!-- комментарий --> |
| `</li>`	| Перед `<li>` или `</ul>`/`</ol>` |
| `</dt>`	| Перед `<dt>` или `<dd>` |
| `</dd>` | Перед `<dt>`, `<dd>` или концом родителя |
| `</p>` | Перед открывающим тегом любого не-фразового потокового («блочного» по-старому:) элемента, либо закрывающим тегом родительского элемента (если у того не прозрачная модель контента) |
| `</rt>` и `</rp>`	| Перед `<rt>`, `<rp>` или `</ruby>` |
| `</optgroup>`	| Перед `<optgroup>` или `</select>` |
| `</option>`	| Перед `<option>`, `<optgroup>`, `</optgroup>` или `</select>` |
| `</colgroup>` | Если после него не идет <!-- комментарий --> или пробел |
| `</caption>` | Если после него не идет <!-- комментарий --> или пробел |
| `</thead>` | Перед `<tbody>` или `<tfoot>` |
| `</tbody>` | Перед другим `<tbody>`, `<tfoot>` или `</table>` |
| `</tfoot>` | Перед `</table>` |
| `</tr>`	| Перед `<tr> `или концом родителя |
| `</td>` и `</th>`	| Перед `<td>`, `<th>` или концом родителя |
