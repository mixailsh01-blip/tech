# tech-assistant

Универсальная страница для отправки вебхуков на `quumahienot.beget.app`.
Публикуется через GitHub Pages, отдельного сервера не нужно.

## Как пользоваться

Ссылка вида:

```
https://<пользователь>.github.io/tech-assistant/ДЕЙСТВИЕ?id=XXXX
```

Например:

```
https://mixailsh01-blip.github.io/tech-assistant/InstallLicense?id=1234
```

Страница отправит `POST`-запрос на:

```
https://quumahienot.beget.app/webhook/InstallLicense
```

с телом:

```json
{ "id": "1234", "t": 1699999999999 }
```

Все параметры из query-строки (кроме `tag`) передаются в теле запроса как есть.
Действие (`InstallLicense`, или любое другое) — это последний сегмент пути
ссылки. Так же можно передать его через query-параметр, если так удобнее:

```
https://mixailsh01-blip.github.io/tech-assistant/?tag=InstallLicense&id=1234
```

На странице отображается статус запроса (загрузка / успех / ошибка) и кнопка
«Повторить» на случай сетевой ошибки.

## Как включить GitHub Pages (один раз)

1. Открыть репозиторий на GitHub → **Settings → Pages**.
2. **Source**: Deploy from a branch.
3. **Branch**: `main` / `(root)`.
4. Сохранить. Через 1-2 минуты сайт появится по адресу
   `https://<пользователь>.github.io/tech-assistant/`.
