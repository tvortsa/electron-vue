# Использование CSS фреймворков

Хотя это может показаться легким делом, я бы посоветовал вам импортировать сторонние библиотеки CSS в веб-пакет, используя [`style-loader`](https://github.com/webpack/style-loader), который уже настроен для вас.

## Случай использования

Скажем, что мы хотим использовать [bootstrap](http://getbootstrap.com/), [bulma](http://bulma.io/), или [materialize](http://materializecss.com/) для своего приложения. Идем дальше и устанавливаем вашу библиотеку из `npm`, как обычно, но вместо того, чтобы присоединять ресурс к` index.ejs`, мы импортируем CSS в наш JavaScript, в частности в `src / renderer / main.js`.

#### пример

Давайте установим `bulma`

```bash
npm install bulma --save
```

Затем внутри `src/renderer/main.js` добавим строку.

```bash
import 'bulma/css/bulma.css'
```

Кроме того, вы также можете включить `bulma` из файла компонента.

**App.vue**

```html
<style>
  @import "~bulma/css/bulma.css";
</style>
```

Теперь `webpack` будет знать, как загрузить` bulma` для нашего приложения и сделать его доступным в продакшн сборках.

