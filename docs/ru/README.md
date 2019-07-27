![](../images/logo.png)

> Шаблон для создания приложений electron, с помощью VUE \(в значительной степени, как это звучит\).

[![Build Status](https://semaphoreci.com/api/v1/simulatedgreg/electron-vue/branches/master/badge.svg)](https://semaphoreci.com/simulatedgreg/electron-vue)

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/uses-js.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/makes-people-smile.svg)](http://forthebadge.com)

## Обзор

Целью этого проекта является устранение необходимости ручной настройки приложений electron с использованием vue. electron-vue использует преимущества `vue-cli` для скафолдинга, `webpack` с `vue-loader`, `electron-packager` или `electron-builder`, некоторыми из наиболее используемых плагинов, таких как `vue-router`, `vuex`, и др.

#### Смотрите документацию [здесь](https://simulatedgreg.gitbooks.io/electron-vue/content/index.html).

Что вы найдете в этом шаблоне...

* Базовая структура проекта с **единственным** `package.json` сетапом
* Детальная [документация](https://simulatedgreg.gitbooks.io/electron-vue/content/)
* Скафолдинг проекта с использованием [vue-cli](https://github.com/vuejs/vue-cli)
* Готовые плагины Vue \([axios](https://github.com/mzabriskie/axios), [vue-electron](https://github.com/SimulatedGREG/vue-electron), [vue-router](https://github.com/vuejs/vue-router), [vuex](https://github.com/vuejs/vuex)\)\*
* Установленные [vue-devtools](https://github.com/vuejs/vue-devtools) и [devtron](https://github.com/electron/devtron) инструменты для разработки
* Возможность легко упаковать ваше приложение, используя [electron-packager](https://github.com/electron-userland/electron-packager) или [electron-builder](https://github.com/electron-userland/electron-builder)\*
* `appveyor.yml` и `.travis.yml` конфигурации для автоматического развертывания с [electron-builder](https://github.com/electron-userland/electron-builder)\*
* Возможность производить веб-вывод для браузеров
* Удобный [NPM scripts](/npm_scripts.md)
* Use of [webpack](https://github.com/webpack/webpack) and [vue-loader](https://github.com/vuejs/vue-loader) with Hot Module Replacement
* Process restarting when working in electron's `main` process
* HTML/CSS/JS поддержка препроцессора с [vue-loader](https://github.com/vuejs/vue-loader/)
