# Структура проекта

Когда дело доходит до создания приложений electron , структура проекта немного отличается. Если вы использовали официальный [`vuejs-templates/webpack`](https://github.com/vuejs-templates/webpack) сетап ранее, тогда структура должна казаться довольно знакомой. Документация в этом разделе пытается объяснить общий обзор того, как работает шаблон и различия, когда ваше приложение построено.

### Однофайловая настройка `package.json`

Было время не так давно, когда два `package.json` setup was neccessary, но благодаря усилиям [@electron-userland](https://github.com/electron-userland), both [`electron-packager`](https://github.com/electron-userland/electron-packager) and [`electron-builder`](https://github.com/electron-userland/electron-builder) теперь полностью поддерживаю однофайловую настройку `package.json`.

#### `Dependencies`

Эти зависимости **будут** включены в ваше окончательное продакшн приложение. Так что если вашему приложению для работы нужен определенный модуль, установите его здесь!

#### `devDependencies`

Эти зависимости **не будут** включены в ваше окончательное продакшн приложение. HПрежде чем вы сможете установить модули, необходимые специально для разработки, такие как скрипты сборки, загрузчики `webpack` и т. д.

#### Installing Native NPM Modules

Нам нужно убедиться, что наши собственные модули npm созданы electron. Для этого мы можем использовать [`electron-rebuild`](https://github.com/electron/electron-rebuild), но для упрощения настоятельно рекомендуется использовать [`electron-builder`](https://github.com/electron-userland/electron-builder) для вашего инструмента сборки, так как многие из этих задач выполняются для вас.

### On the subject of the `main` process

Во время разработки вы можете заметить `src/main/index.dev.js`. Этот файл используется специально для разработки и используется для установки dev-tools. Этот файл не нужно изменять, но его можно использовать для расширения ваших потребностей в разработке. После сборки вступит в силу `webpack` и создаст пакет с` src / main / index.js` в качестве входного файла.
