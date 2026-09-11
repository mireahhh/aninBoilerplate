# Шаблон статичного сайта на webpack

## О шаблоне

> Шаблонный код, boilerplate-код (англ. boilerplate code) — нетворческий программный код, который программисту приходится писать вследствие требований языка программирования, операционной системы, библиотеки подпрограмм, манеры программирования и прочего. Название «шаблонный» говорит, что он повторяется из функции в функцию, из программы в программу с минимальными изменениями. (c) _Википедия_

Это шаблон проекта на webpack, который можно повторно использовать практически без изменений для настройки окружения разработчика. Опирайтесь на образец структуры и шаблонных файлов, представленных в коде, при создании своего проекта. Шаблон взят из публичного репозитория https://github.com/annkomkova/new-static-site-boilerplate

## Установка

# Клонировать репу

```
Открыть консоль и перевести Windows Powershell в CMD режим (корректный запуск git, nmp, yarn)
    Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
Если не скачен ГИТ, скачать ГИТ на ПК
    https://git-scm.com/install/windows
Зарегаться в ГИТ на ПК
    git config --global user.name "mireahhh"
    git config --global user.email mireahhh@yandex.ru
Проверить кто прописан
    git config user.name
    git config user.email
Чтобы не сраться с Воркспейсами, находясь в родительской папке (куда вы поместите клон бойлера), прописать
    git clone ССЫЛКА_НА_РЕПУ ПАПКА_КУДА_ПОЛОЖИТЬ
Или, зайти в VS Code и скопировать F1 -> Git:Clone, выбрав папку
    git clone
```

# Установка необходимых yarn и node_modules:

```
Скачать на ПК Node JS, при установке нажать галочку скачать доп. иснструменты
    https://nodejs.org/en/download
Установить `yarn` через `npm`
    npm install --global yarn
Установить зависимости `yarn`
    yarn
```

# Связать проект со своей новой удалённой репой:

```
На гитхабе создать новый репозиторий, лучше без readme, gitignore, License
    Create new -> New repository
Проверить с какой репой связан проект
    git remote -v

Проект бойлер будет смотреть на старую репу! 

ЕСЛИ СТАРУЮ РЕПУ И СОАВТОРА (Анну Комкому) НЕ УДАЛЯЕМ:
Переименовываем её в upstream
    git remote rename origin upstream
Добавляем новую репу как основной origin
    git remote add origin https://github.com/ВАШ_ЛОГИН/ВАША_РЕПА
Проверяем, должно выдать новую ссылку!
    git remote -v
И пушим (и можно сразу гит адд и т д сделать)
    git push -u origin main
Если ветка называется не main, посмотреть её можно так
    git branch --show-current

ИНАЧЕ ЕСЛИ УДАЛЯЕМ СОАВТОРА И ИСТОРИЮ КОМИТОВ:
    rm -rf .git
    или для PowerShell
    Remove-Item -Recurse -Force .git
Создаём новую историю
    git init
    git add .
    git commit -m "Initial commit"
Делаем основную ветку main
    git branch -M main
Привязываем свою ГИТ репу
    git remote add origin https://github.com/ВАШ_ЛОГИН/ВАША_РЕПА
Проверяем, должно выдать новую ссылку!
    git remote -v
И отправляем
    git push -u origin main
Теперь история будет начинаться примерно так
    Initial commit — Eva

ЕЩЁ РАЗ
Хочу сохранить историю:
    clone
    → git remote rename origin upstream
    → git remote add origin МОЯ_РЕПА
    → git push
Хочу полностью начать заново:
    clone
    → удалить .git
    → git init
    → git add .
    → git commit
    → git remote add origin МОЯ_РЕПА
    → git push
```

# Выложить на гитха пейджс:

```
Дальше сначала установить зависимости и созбрать сайт
    yarn
    yarn build
После запушить изменения в репу
    git add .
    git commit -m "НАЗВАНИЕ"
    git push -u origin main
После этого на гитхабе зайти
    РЕПОЗИТОРИЙ → Settings → Pages
И выставить:
    Build and deployment
    Source: Deploy from a branch

    Branch: main
    Folder: /docs
Жмём Save.

Через минуту-другую сайт должен появиться примерно здесь:
    https://mireahhh.github.io/НАЗВАНИЕ_ПРОЕКТА/
В следующие разы использовать
    Стандартный пуш на ГИТ
```

# Команды yarn

```
Запуск на локальном сервере (автоилд + автоизменения):
    yarn start
Сборка версии для продакшена (перед пушом на гит):
   yarn build
Сборка версии для разработки (для отладки, в начале - забейте):
    yarn watch
```

# Основные команды ГИТ:

```
Проверить настройки гита
    git config --list
Проверить настройки гита +дерево настроек
    git config --list --show-origin
Привязать к репозиторию
    git remote set-url origin htt_Полная_ссылка.git
Узнать к какому репозиторию привязан проект
    git remote -v
Узнать в какой ветке находимся
    git branch
Создать ветку + переключиться
    git checkout -b Название
Переключиться на ветку
    git checkout Название
Пропушить в отпределённую ветку
    git push -u origin gh-pages
После можно писать просто
    git push
```

# Первый пуш на ГИТ:

```
Узнать в какой ветке находимся
    git branch
Создать ветку + переключиться
    git checkout -b Название
Переключиться на ветку
    git checkout Название
Пропушить в отпределённую ветку (не забыл гит адд)
    git push -u origin gh-pages
```

# Стандартный пуш на ГИТ:

```
Забилдить новое
    yarn build
Добавить новое
    git add .
Сохранить изменения
    git commit -m "имя_комита"
Запушить
    git push
```
