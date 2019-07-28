# входной `index.html`

electron-vue использует [**`html-webpack-plugin`**](https://github.com/ampedandwired/html-webpack-plugin) для создания `index.html` в продакшн сборках. Во время разработки вы найдете `index.ejs` в каталоге `src /`. Именно здесь вы можете внести изменения в свой входной HTML файл.

Если вы не знакомы с тем, как работает этот плагин, то я бы посоветовал вам взглянуть на его [documentation](https://www.npmjs.com/package/html-webpack-plugin). Но вкратце, этот плагин будет автоматически вводить производственные активы, включая `renderer.js` и `styles.css` в финальный минифицированный `index.html`.

### `index.ejs` во время разработки

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title><%= htmlWebpackPlugin.options.title %></title>
    <%= ... %>
  </head>
  <body>
    <div id="app"></div>
    <!-- webpack builds are automatically injected -->
  </body>
</html>
```

### `index.html` в продакшн \(non-minified\)

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>app</title>
    <link href="styles.css" rel="stylesheet">
  </head>
  <body>
    <div id="app"></div>
    <script type="text/javascript" src="renderer.js"></script>
  </body>
</html>
```

### На предмет использования CDNs

Хотя преимущества использования ресурсов, предоставляемых из CDN, могут быть очень важны для конечного размера сборки вашего приложения, я бы посоветовал не использовать их. Основная причина в том, что при этом вы предполагаете, что приложение всегда имеет доступ к Интернету, что не всегда имеет место для приложений Electron. Это становится довольно серьезной проблемой для CSS-фреймворков, таких как начальная загрузка, так как ваше приложение быстро превратится в беспорядочный беспорядок.

> "Мне все равно, я все еще хочу использовать CDN "

Если вы по-прежнему решаете использовать CDN, вы можете сделать это, добавив теги в файл `src / index.ejs`. Просто убедитесь, что настроены правильные потоки UI / UX, когда ваше приложение находится в автономном режиме.
