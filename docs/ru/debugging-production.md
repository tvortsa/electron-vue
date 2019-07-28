# отладка

### Main Process

При запуске приложения в процессе разработки вы могли заметить сообщение от `main` процесса, в котором упоминается удаленный отладчик. С момента выхода `electron@^1.7.2`, удаленная отладка через Inspect API был введен и может быть легко доступен, открыв предоставленную ссылку с Google Chrome или через другой отладчик, который может удаленно подключиться к процессу, используя порт по умолчанию 5858, например Visual Studio Code.

```bash
┏ Electron -------------------

  Debugger listening on port 5858.
  Warning: This is an experimental feature and could change at any time.
  To start debugging, open the following URL in Chrome:
      chrome-devtools://devtools/bundled/inspector.html?experiments=true&v8only=true&ws=127.0.0.1:5858/22271e96-df65-4bab-9207-da8c71117641

┗ ----------------------------
```

### Production Builds

###### Notice

Although it is possible to debug your application in production, please do know that production code is minified and highly unreadable compared to what you find during development.

##### `renderer` Process

Здесь нет большой разницы, чем в разработке. Вы можете просто вызвать dev tools используя [`BrowserWindow` APIs](https://electron.atom.io/docs/api/web-contents/#contentsopendevtoolsoptions). Используя начальный electron-vue setup, Вы можете добавить следующий фрагмент кода внутри `src / main / index.js`, сразу после конструкции` new BrowserWindow`, чтобы принудительно вызвать dev tools открыть при запуске.

```js
mainWindow.webContents.openDevTools()
```

##### `main` Process

Similar to what is mentioned above, you can also attach an external debugger to the `main` process to remotely debug your application. In order to activate the debugger in production you can add the follow snippet after the `app` import inside `src/main/index.js`. Then you can navigate Google Chrome to `chrome://inspect` and get connected.

```js
app.commandLine.appendSwitch('inspect', '5858')
```



