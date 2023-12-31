# ?CSS specificity

Для определения стиля к элементу могут применяться различные селекторы, и важность каждого селектора оценивается в баллах. Чем больше у селектора пунктов, тем он важнее, и тем больший приоритет его стили имеют над стилями других селекторов.

* Селекторы тегов имеют важность, оцениваемую в 1 балл
* Селекторы классов, атрибутов и псевдоклассов оцениваются в 10 баллов
* Селекторы идентификаторов оцениваются в 100 баллов
* Встроенные inline-стили (задаваемые через атрибут `style`) оцениваются в 1000 баллов

CSS предоставляет возможность полностью отменить значимость стилей. Для этого в конце стиля указывается значение `!important`:

~~~
a {
  font-size: 18px;
  color: red !important;
}
~~~
