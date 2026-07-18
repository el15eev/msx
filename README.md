# Media Station X: OTTPlayer + HDGO

Готовая стартовая страница Media Station X с двумя кнопками:

- OTTPlayer (`widget.ottplayer.tv`)
- HDGO (`hdgo.me`)

## 1. Подготовьте файлы

Откройте `start.json` и замените `el15eev` на ваш логин GitHub.

Пример:

```json
"parameter": "content:https://ivan123.github.io/msx/data/apps.json"
```

Название репозитория в этой инструкции — `msx`. Если выберете другое название, замените `/msx/` в `start.json` на имя репозитория.

## 2. Загрузите на GitHub

1. Создайте публичный репозиторий `msx`.
2. Загрузите в корень репозитория:
   - `start.json`
   - папку `data` вместе с файлом `apps.json`
3. Откройте **Settings → Pages**.
4. В разделе **Build and deployment** выберите:
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/(root)**
5. Нажмите **Save** и подождите публикации.

Проверьте в браузере:

```text
https://el15eev.github.io/msx/start.json
```

Должен открыться JSON-текст.

## 3. Настройте телевизор

В Media Station X откройте:

**Settings → Start Parameter → Setup**

1. Включите значок замка, чтобы использовать HTTPS.
2. Введите:

```text
el15eev.github.io
```

Media Station X автоматически запросит:

```text
https://el15eev.github.io/msx/start.json
```

После сохранения появится страница с кнопками OTTPlayer и HDGO.

## Если кнопка не открывается

В Media Station X попробуйте **Settings → Validate Links → No**.

Некоторые порталы используют HTTP. На отдельных версиях VIDAA переход из HTTPS-контекста на HTTP может блокироваться. В таком случае замените нужное действие в `data/apps.json`, например:

```json
"action": "link:https://widget.ottplayer.tv"
```

или

```json
"action": "link:https://hdgo.me"
```

Если HTTPS-версия портала не поддерживается, верните `http://`.
