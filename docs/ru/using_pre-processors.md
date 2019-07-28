# Использование препроцессоров

Одним из больших преимуществ использования [`vue-loader`] (https://github.com/vuejs/vue-loader) с [` webpack`] (https://github.com/webpack/webpack) является возможность предварительной обработки HTML / CSS / JS непосредственно в файлах компонентов Vue без особых усилий. Для получения дополнительной информации об этой проверке [**here**](https://vuejs.org/v2/guide/single-file-components.html).

## Случай использования

Допустим, нам нужно использовать Sass / SCSS для предварительной обработки нашего CSS. Во-первых, нам нужно установить соответствующий загрузчик `webpack` для обработки этого синтаксиса.

#### установка `sass-loader`

```bash
npm install --save-dev sass-loader node-sass
```

Как только необходимый нам загрузчик установлен, все в значительной степени закончено. `vue-loader` волшебным образом позаботится об остальном. Теперь мы можем легко добавить `lang="sass"` или `lang="scss"` в наши файлы компонентов Vue. Обратите внимание, мы также установили `node-sass` так как это зависимый пакет для `sass-loader`.

#### применение атрибута `lang`

Так...

```html
<style>
  body {
    /* CSS */
  }
</style>
```

...сейчас становится...

```html
<style lang="scss">
  body {
    /* SCSS */
  }
</style>
```

Те же принципы применимы практически к любому другому препроцессору. Так, может быть, вам нужен Coffeescript для вашего JS? Просто установите [coffeescript-loader](https://github.com/webpack/coffee-loader) и примените `lang="coffeescript"` атрибут вашему тегу `<script>`.

Для более расширенного использования этой функции, пожалуйста, перейдите на [vue-loader documentation](http://vue-loader.vuejs.org/en/configurations/pre-processors.html) для дополнительной информации.

## использование Sass/SCSS globals

При использовании Sass / SCSS для вашего синтаксиса CSS очень полезно использовать глобальные переменные / миксины во всех файлах компонентов Vue. Вот как это сделать.

### Случай использования

Этот пример демонстрирует, как применить `globals.scss` ко всем файлам компонентов Vue. В этой документации предполагается, что вы уже настроили `sass-loader` в своей среде разработки, как указано выше.

#### Определите свой globals

**src/renderer/globals.scss**

```scss
$brand-primary: blue;
$brand-accent: turquoise;
```

#### Inject `globals.scss` directly into `node-sass`

Edit the `vue-loader` config in **.electron-vue/webpack.renderer.config.js**

```js
loaders: {
  sass: 'vue-style-loader!css-loader!sass-loader?indentedSyntax=1&data=@import "./src/renderer/globals"',
  scss: 'vue-style-loader!css-loader!sass-loader?data=@import "./src/renderer/globals";'
}
```

#### Use your globals

**SomeComponent.vue**

```html
<style lang="scss">
  body { color: $brand-primary; }
</style>
```



