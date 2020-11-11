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

```javascript
globalThis.$ = {
	find: function (dom) {
	  return document.querySelector(dom);
	},
  rem: function (dom) {
    document.querySelector(dom).remove();
  },
  popup: function (dom) {
    let d = document.querySelector(dom);
    if (d.style.display == "none") {
        d.style.display = "block";
    } else if (d.style.display == "block") {
        d.style.display = "none";
    } else {
        console.warn('Не заданно display: block или none');
        d.style.display = "block";
    }
  },
  hide: function (dom) {
    document.querySelector(dom).style.display = "none";
  },
  show: function (dom) {
    let d = document.querySelector(dom);
    if (d.style.display == "none") {
      d.style.display = "block";
    } else {
      console.warn('Как я тебе это отображу? Поставь display: none; хоть!!!');
    }
  },
  log: function (text) {
	  console.log('%c%s', 'color: black; font: 1.2rem/1 Tahoma;', text);
  },
  info: function (dom) {
	  console.log('%O', document.querySelector(dom));
  },
  logimg: function (i,s,c) {
	  const r = new FileReader();
        if(s==undefined){s=100};
	  r.addEventListener('load', function () {
	    const o ='background: url(\'' + r.result + '\') left top no-repeat; font-size: '+s+'px; background-size: contain; background-color:'+c;
	    console.log('%c     ',o);
	  },false);
	  fetch(i)
	    .then(r=>r.blob())
	    .then(b=>{
	  	if(b.type.indexOf('image')===0){
	  	  if(b.size>8192&& navigator.userAgent.indexOf('Firefox')>0){
	  		throw new Error('Изображение СЛИШКОМ большое.');
	  	  }
	  	  return b;
	  	}else{
	  	  throw new Error('Хм... Неправильный адрес.');
	  	}
	    })
	    .then(i=>r.readAsDataURL(i))
	    .catch(e=>console.warn(e.message));
	},
  click: function (dom) {
    document.querySelector(dom).click();
  },
  text: function (dom, text) {
    document.querySelector(dom).textContent = text;
  },
  add: function (dom, cl) {
    document.querySelector(dom).classList.add(cl);
  }
};```
