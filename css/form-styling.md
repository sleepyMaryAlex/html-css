# ?Form styling

Устанавливаем  `* { box-sizing:border-box; }`

К форме можно обратиться так:

~~~
input[type=text]
~~~

Свойства:

* Внутренние отступы
* Внешние отступы
* Граница
* Тень блока
* border-radius (для скругления границ)
* Ширина
* Шрифт

Как стилизовать текстовые области:

~~~
textarea {
  width: 100%;
  resize: vertical;
  padding: 15px;
  border-radius: 15px;
  border: 0;
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.06);
  height: 150px;
}
~~~

Для стилизации радиокнопок и переключателей используется более сложный код:

~~~
label {
  display: block;
  margin-bottom: 4px;
  position: relative;
  padding-left: 30px;
  cursor: pointer;
}

label input[type=radio] {
  position: absolute;
  opacity: 0;
  width: 0;
  height: 0;
}

label span {
  position: absolute;
  top: 0;
  left: 0;
  width: 20px;
  height: 20px;
  background-color: #ddd;
  border-radius: 50%;
  transition: .3s background-color;
}

label span:after {
  content: "";
  position: absolute;
  display: none;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #fff;
  width: 8px;
  height: 8px;
  border-radius: 50%;
}

label:hover span {
  background-color: #ccc;
}

label input:checked~span {
  background-color: #2eaadc;
}

label input:checked~span:after {
  display: block;
}

<label>
  <input type="radio">
  <span></span>
</label>
~~~

`background: transparent` - делает фон `input` прозрачным.
