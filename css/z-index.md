# ?z-index

CSS-свойство `z-index` определяет положение позиционированного элемента и его дочерних элементов или флекс-элементов по оси `z`. Перекрывающие элементы с большим значением `z-index` будут накладываться поверх элементов с меньшим `z-index`.

> Позиционируемый элемент — это элемент, у которого вычисленное значение `position` является `relative`, `absolute`, `fixed` либо `sticky`. (Другими словами, это все, кроме `static`.)

`z-index` вообще не имеет смысла для элементов в нормальном потоке (у которых свойство `position` равно `static`).

~~~
div {
  width: 200px;
  height: 200px;
}

<div style="background: #b3ecf9; z-index: 1"></div>
<div style="background: #b3ecb3; margin-top: -86px; margin-left: 38px; z-index: 0"></div>
~~~

Значением свойства `z-index` может быть либо `auto`, либо целое число (`<integer>`).

`auto`. Элемент не будет создавать нового локального контекста наложения. Порядок наложения блока в текущим контексте наложения будет равен `0`.

`z-index` можно применять непосредственно к элементам `grid`, то есть к прямым дочерним элементам `display: grid` или `display: inline-grid` элементам.

`z-index` можно применять непосредственно к `flex` элементам, то есть к прямым дочерним элементам `display: flex` или `display: inline-flex` элементам.

А ещё отдельные контексты наложения задаются элементами со значением `opacity`, меньшим единицы. Это было сделано для того, чтобы можно было легко перенести альфа-блендинг на последнюю стадию отрисовки для обработки видеокартой.
