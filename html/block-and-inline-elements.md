# ?Block and inline elements

Блочные элементы всегда начинаются с новой строки (параграфы, списки, `<pre>`, `<div>`, заголовки, таблицы). Элемент блочного уровня всегда занимает всю доступную ширину (растягивается влево и вправо, насколько это возможно).

Помимо блочных элементов существуют строчные элементы. К ним относятся ссылки (`<a>`), теги начертания текста (`<b>`, `<strong>`, `<i>`, `<em>`), картинки, `<span>`. Они не влияют на расположение соседних элементов и предназначены для придания смысловой нагрузки. В отличие от блочных элементов, строчные не занимают всю ширину экрана.

Строчный элемент не может содержать блочный элемент!

Но в HTML5 — `<a>` могут содержать `<p>`.
Элемент `p` не может содержать элементы уровня блока (включая сам `p`).