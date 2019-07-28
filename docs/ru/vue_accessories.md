# Vue Plugins

electron-vue поставляется со следующим `vue` плагинами, которые могут быть установлены во время `vue-cli` scaffolding...

* [axios ](https://github.com/mzabriskie/axios)\(web requests\)
* [vue-electron](https://github.com/SimulatedGREG/vue-electron) \(присоединяет electron API к объекту Vue\)
* [vue-router](https://github.com/vuejs/vue-router) \(роуты одностраничного приложения\)
* [vuex](https://github.com/vuejs/vuex) \(flux-inspired архитектура приложения\)
* [vuex-electron](https://github.com/vue-electron/vuex-electron) \(синхронизирует vuex store между всеми процессами и экземплярами\)

---

### [`axios`](https://github.com/mzabriskie/axios)

> HTTP-клиент на основе promise для браузера и node.js

Если вы знакомы с `vue-resource`, то `axios` будет чувствовать себя очень знакомо, так как большая часть API почти идентична. Вы можете легко импортировать `axios` в ваших сценариях `main` процесса или используйте вместе с` this. $ http` & `Vue.http` в процессе` renderer`. Обратите внимание, что во время разработки вы можете столкнуться с проблемами с CORS поскольку запросы передаются через`webpack-dev-server`. В качестве небольшого обходного пути, вы можете отключить [`webSecurity`](https://electronjs.org/docs/api/browser-window#new-browserwindowoptions) в BrowserWindow configuration, bно, пожалуйста, не забудьте отключить это только во время разработки. Отключать это в продакшн крайне не рекомендуется, и это может создать серьезную угрозу безопасности для вашего конечного приложения!

### [`vue-electron`](https://github.com/SimulatedGREG/vue-electron)

> Vue плагин, который придает electron APIs к объекту Vue, делая их доступными для всех компонентов.

Простой плагин `vue` который делает API electron легко доступными с`this.$electron`, больше не нужно импортировать электрон в каждый необходимый компонент.

### [`vue-router`](https://github.com/vuejs/vue-router)

> `vue-router` является официальным роутером для [Vue.js](http://vuejs.org/). Он глубоко интегрируется с ядром Vue.js для создания Single Page Applications c Vue.js a breeze.

Предоставленная структура проекта должна быть знакома с настройкой, представленной в официальном `vuejs-templates/webpack` boilerplate.

### [`vuex`](https://github.com/vuejs/vuex)

> Vuex это **state management pattern + library**for Vue.js applications. Он служит централизованным хранилищем для всех компонентов приложения с правилами, гарантирующими, что состояние может быть изменено только предсказуемым образом.

Предоставленная структура проекта довольно проста, но она поощряет использование шаблона модуля `vuex`, чтобы помочь организовать ваши хранилища данных. Дополнительный файл `@ / store / modules / index.js` позволяет вашему магазину` vuex` импортировать все модули за один раз.

### [`vuex-electron`](https://github.com/vue-electron/vuex-electron)

> Самый простой способ использовать хранилище Vuex между всеми процессами (включая main) и экземплярами.

В случае, если ваше приложение имеет несколько окон, вероятно, вам нужно будет разделить состояние приложения между ними. Более того, возможно, вам нужно будет поделиться состоянием приложения между запусками или разными экземплярами. Вы можете легко решить эти две задачи, используя `vuex-store`.
