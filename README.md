# $Lib

#### Test:

```javascript
//найти эллемент
let logo = $.find('#logo');
//удалить эллемент
$.rem('#logo');
//функция поп апа
$.popup('#area');
//скрыть
$.hide('#he');
//показать
$.show('#he');
//console.log
$.log(123);
//информация о эллементе
$.info('#he');
//изображение в консоль
$.logimg('img/logo.jpg');
//клик по эллемнту
$.click('.btn');
//изменяем текст эллемента
$.text('.btn', 'alert =3');
//добовляем класс
$.add('.btn', 'btnf');
//добавляем скрипт, стили
$.js('test.js');
$.css('test.css');
//заменяем {lib} на $lib
document.body.innerHTML = $.rnd({
  lib: "$lib",
  title: "JS",
  description: "Is top"
});
```

#### Download

```bash
  npm install htmlcssphpjs/libs
     [========] 100%
```

#### Code

```html
<script src="lib.js"></script>
```
