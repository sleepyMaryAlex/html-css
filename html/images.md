# ?Images

~~~
<img src="winter.png" alt="Winter" />
~~~

Атрибут `src` - путь к изображению. Путь может быть абсолютный и относительный. Можно брать из интернета.
Атрибут `alt` - текстовое описание изображения.

`<figure>` применяется для заголовков для различных иллюстраций, диаграмм, фотографий и т.д. А элемент `figcaption` просто обертывает заголовок для содержимого внутри элемента `figure`.

~~~
<figure>
  <figcaption>February 2013</figcaption>
  <img src="winter.png" alt="Winter">
</figure>
~~~

PNG, GIF, JPG форматы изображений могут отображаться во всех веб-браузерах.

Атрибут `srcset` указывает несколько ресурсов (URL-адресов) для элемента.

Каждый источник `srcset` имеет следующий формат: `URL width`.

* `URL` = URL-адрес или путь к файлу изображения.
* `width` = фактическая ширина изображения в единицах `w` (например, `450w`).

Несколько элементов `src` разделяются запятыми.

Атрибут `size` sопределяет различную ширину изображения.

Каждый размер `sizes` имеет следующий формат: `(media-condition) width`

* `media-condition` = Медиа-запрос (например, `max-width: 540px`), за которым следует пробел.
* `width` = Ширина доступного пространства в пикселях (`px`), `em` или области просмотра (`vw`).

~~~
<img srcset="/img/html/vangogh-sm.jpg 120w,
/img/html/vangogh.jpg 193w,
/img/html/vangogh-lg.jpg 278w" sizes="(max-width: 710px) 120px,
(max-width: 991px) 193px,
278px">
~~~

Старые браузеры, не поддерживающие эти функции, просто проигнорируют их. Вместо этого эти браузеры продолжат загружать изображение, указанное в атрибуте `src`, как обычно.
