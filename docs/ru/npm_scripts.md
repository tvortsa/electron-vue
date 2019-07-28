# NPM Scripts

Чтобы устранить лишние задачи в процессе разработки, обратите внимание на некоторые из доступных вам сценариев NPM. Следующие команды должны быть запущены из корневого каталога вашего проекта. И, конечно, вы можете запустить любую из следующих команд, используя `yarn run <command>`.
### `npm run build`

Создайте свое приложение для производства и упаковки. Более подробную информацию можно найти в разделе [**Building Your App**](building_your_app.md).

### `npm run dev`

Запустить приложение в разработке.

Вы также можете передать параметры командной строки в приложение с помощью:

    npm run dev --arg1=val1 --arg2

### `npm run lint`

Lint все ваши `src/` и `test/` JS и Vue файлы компонентов.

### `npm run lint:fix`

Lint все ваши `src/` и `test/` JS и Vue файлы компонентов и пытается исправить проблемы в них.

### `npm run pack`

Запускает и `npm run pack: main` и` npm run pack: renderer`. Хотя эти команды доступны, не так много случаев, когда вам придется делать это вручную, поскольку `npm run build` будет обрабатывать этот шаг.

### `npm run pack:main`

Запускает webpack для сборки исходников `main` process.

### `npm run pack:renderer`

Запускает webpack для сборки исходников `renderer` process.

### `npm run unit`

Run unit tests with Karma + Jasmine. More information on [**Unit Testing**](unittesting.md).

### `npm run e2e`

Run end-to-end tests with Spectron + Mocha. More information on [**End-to-end Testing**](end-to-end_testing.md).

### `npm test`

Runs both `npm run unit` & `npm run e2e`. More information on [**Testing**](testing.md).

