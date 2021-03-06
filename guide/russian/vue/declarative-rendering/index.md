---
title: Declarative Rendering
localeTitle: Декларативное рендеринг
---
## Установка

Прежде чем мы начнем, существует несколько способов использования Vue.js, а именно через CDN и через установку пакета. Для начала проще всего использовать CDN.

Для разработки используйте это:

```html

<!-- development version, includes helpful console warnings --> 
 <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script> 
```

Для production это:

```html

<!-- production version, optimized for size and speed --> 
 <script src="https://cdn.jsdelivr.net/npm/vue"></script> 
```

Как упоминалось ранее, вы также можете установить пакет `vue-cli` , но это не рекомендуется для начинающих.

## Декларативное рендеринг

Vue.js - отличный инструмент для создания динамических страниц и вам в первую очередь стоит познакомиться с декларативным рендерингом.

Использование термина декларативность подразумевает отношения этого концепта к декларативным языкам. В ядре Vue.js находится система, которая позволяет декларативно отображать данные в DOM с помощью простых шаблонов:

```html

<div id="app"> 
  {{ message }} 
 </div> 
```

```javascript
let app = new Vue({ 
  el: '#app', 
  data: { 
    message: 'Hello, world!' 
  } 
 }); 
```

В этих снипетах вы сообщаете Vue динамически отобразить все, что хранится внутри переменной 'message'. А самое главное: всякий раз, когда 'message' изменяется, Vue.js удается перезагрузить определенную часть DOM и вы можете увидеть изменение.

Если вы хотите попробовать эту реактивность, откройте консоль и измените значение от `app.message` до, скажем, `"Hello from console"` . Вы заметили изменение на странице?

`{{ ... }}` такой синтаксис позволяет выводить значения переменной или выражения. Например вы можете поместить в него условие и оно выведет 'hello':

```html

<div id="app"> 
  {{ 1 < 2 ? "hello" : "goodbye" }} 
 </div> 
```

Есть случаи когда мы хотим установить в значение атрибута переменную из Vue. Вы можете подумать, что можно использовать такой же синтаксис, но во Vue есть кое-что специально для этой цели, это называется биндинг.

```html

<div id="app"> 
  <a v-bind:href="dynamicLink">This link</a> 
 </div> 
```

```javascript
let app = new Vue({ 
  el: '#app', 
  data: { 
    dynamicLink: 'medium.freecodecamp.org' 
  } 
 } 
```

Синтаксис `v-bind` - это то, что во Vue.js называет «директивой». Это способ установить атрибут тега, который будет обрабатываться Vue. Во Vue множество директив, все они начинаются с `v-`.
