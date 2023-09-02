# ?Audio / Video

### Аудио

~~~
<audio src="путь к аудио-файлу" controls></audio>
~~~

Атрибут `controls` добавляет элементы интерфейса для плеера. Каждый браузер реализует их по-своему, и единого стандарта на этот счёт нет.

При добавлении аудио на HTML-страницу важно помнить, что не все браузеры поддерживают одни и те же форматы аудио. Специально для этого существует вложенный тег `source`, в котором указываются пути на другие форматы аудио файлов. В таком случае браузер выберет тот, который поддерживается в настоящий момент.

~~~
<audio controls>
  <source src="https://example.com/audio.mp3">
  <source src="https://example.com/audio.ogg">
</audio>
~~~

Текст между тегами `<audio>` и `</audio>` будет отображаться только в браузерах, которые не поддерживают `<audio>` элемент.

~~~
<audio controls autoplay muted>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>
~~~

`autoplay` ничего не делает. Современные браузеры требуют некоторой формы взаимодействия, прежде чем они позволят странице автоматически воспроизводиться со звуком. Добавьте `muted` после `autoplay`, чтобы аудиофайл начал воспроизводиться автоматически (но без звука).

### Видео

~~~
<video src="https://example.com/our-video.mp4" controls></video>
~~~

С помощью специальных тегов `<source>` возможно добавлять несколько форматов видео. Это необходимо по причине того, что каждый браузер умеет воспроизводить только определенные форматы видео. Единственный формат, который корректно обрабатывают все браузеры — `mp4`. Браузер выберет первый поддерживаемый им источник.

~~~
<video controls>
  <source src="https://example.com/our-video.mp4" type="video/mp4">
  <source src="https://example.com/our-video.webm" type="video/webm">
  <source src="https://example.com/our-video.ogg" type="video/ogg">
</video>
~~~

Также обязательным является наличие атрибута `type`, когда несколько ссылок, который сообщит браузеру формат видео. Именно по этому атрибуту браузер примет решение, какой файл необходимо загрузить.

Тег `<video>` имеет несколько важных атрибутов:

* `controls` - добавляет элементы управления для видеоплеера.
* `autoplay` - автоматическое воспроизведение после загрузки видео. Браузеры в большинстве случаев не поддерживают `autoplay`. Однако `muted` `autoplay` всегда разрешен.

~~~
<video src="video.mp4" autoplay muted></video>
~~~

* `width` - ширина видеоплеера.
* `height` - высота видеоплеера.
* `poster` - указывает изображение, которое будет отображаться во время загрузки видео или до тех пор, пока пользователь не нажмет кнопку воспроизведения.
...и другие.

Тег `<track>` определяет текстовые дорожки для элементов `<audio>` или `<video>`.

~~~
<video width="320" height="240" controls>
  <source src="../../assets/squirrel.mp4" type="video/mp4">
  <track src="sample.vtt" kind="subtitles" srclang="en" label="English">
</video>
~~~

sample.vtt
~~~
WEBVTT
00:00:00.500 --> 00:00:02.000
The Web is always changing

00:00:02.500 --> 00:00:04.300
and the way we access it is changing
~~~

Типы текстовой дорожки:

* `captions`
* `chapters`
* `descriptions`
* `metadata`
* `subtitles`