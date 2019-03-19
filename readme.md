# MetaGate DApp example
DApp приложения сети https://metahash.org - это не только статичные HTML страницы с картинками, это полноценная экосистема с множетсвом внутренних методов.

Это приложение использует два самых простых метода - получение списка кошельков пользователя тестовой и главной сети MetaHash.

## Как это работает
Первое - подключаем библиотеку взаимодействия со внутренним API:
```html
<script type="text/javascript" src="qrc:///qtwebchannel/qwebchannel.js"></script>
```

Второе - вызываем нужный метод и обрабатываем результат, методы возвращают результат строкой с json внутри, не забудьте распарсить результат:
```js
<script>
(function () {
    new QWebChannel(qt.webChannelTransport, function (channel) {
    var mainWindow = channel.objects.mainWindow;
    mainWindow.getAllWalletsJson(function (returnValue) {
        alert(JSON.parse(returnValue));
    });
    });
})();
</script>
```
