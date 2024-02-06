# Работа с GIT

## Инициализация репозитория

* Инициализировать репозиторий можно с помощью команды git init;

* Проверить статус, или состояние, репозитория поможет команда git status;

* Если вы ошиблись и случайно инициализировали не ту папку, можно «разгитить» её — удалить скрытую подпапку .git.


## Добавление файлов в репозиторий

* Команда git add позволяет подготовить файл к сохранению.

* Команда git add --all подготовит к сохранению сразу все файлы.

* С помощью git add . можно добавить в репозиторий текущую папку со всеми файлами.


## Commit

* Коммит можно сделать с помощью команды git commit.

* Ключ -m позволяет присвоить коммиту сообщение. Помните, что такие сообщения должны быть информативными: чётко описывать изменения.

* В коммит попадает то, что было предварительно добавлено «в корзину», или «в кадр», перед коммитом.


## Знакомство с GitHub

* GitHub — платформа, которая работает с Git и упрощает командное взаимодействие.

* Кроме GitHub, существуют и другие подобные платформы, например GitLab, Bitbucket и так далее.

* Git — это консольный инструмент для работы с локальными и удалёнными репозиториями. Он не связан напрямую ни с одной из платформ и развивается отдельно от них.

## Удаленный репозиторий

Удаленный репозиторий создается на GitHub по инструкции

## Создание SSH-ключа

* SSH — протокол, который обеспечивает безопасный обмен данными в сети и использует для этого ключи.

* SSH-ключ — ваш виртуальный идентификатор в GitHub. Как ключ от квартиры, он позволяет получить доступ к GitHub-репозиторию. Также SSH используется для доступа к другим удалённым серверам.

* SSH-ключ состоит из двух частей — публичной и приватной. Публичный ключ зашифрует данные, а приватный — расшифрует. Приватным ключом ни в коем случае нельзя делиться, иначе любой сможет расшифровать все ваши секреты!

* Подключить SSH-ключ в удаленном репозитории во вкладке Settings

## Связываем удаленный репозиторий с локальным

* git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git  - связать удаленный репозиторий с локальным;

* git remote -v - проверить связь между локальным и удаленным репозиторием

## Push

* git push --set-upstream origin master - первое создание ветки

* Коммиты хранятся в ветках. Начальная ветка создаётся автоматически и называется main или master.

* За отправку изменений на удалённый репозиторий отвечает команда git push.

* Интерфейс GitHub позволяет удобно просмотреть все коммиты в репозитории, а также изменения в этих коммитах.

## Файл README.md

* Название проекта и его краткое описание: кем создан, для чего, какие решает задачи и какие закрывает проблемы.

* Технологии, которые применяются в проекте. В чём его отличие от аналогичных.

* Документация проекта — подробная инструкция о том, что представляет собой проект.

* Планы проекта, если они есть.

## Логи

* git log - показать список коммитов.

* git log --oneline - получение сокращенного лога.

## Хеш — идентификатор коммита

* Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для каждого из них рассчитывает уникальный идентификатор — хеш.

* Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.

* Все хеши, а также таблицу соответствий хеш → информация о коммите Git хранит в папке .git.

## Получить сокращённый лог

* Можно вызвать не только полный лог, но и сокращённый — это делается командой git log --oneline.

* В сокращённом логе выводятся сокращённые хеши — их можно использовать точно так же, как и полные.

## HEAD — всему голова

* В числе прочих файлов в папке .git есть служебный файл HEAD. Он указывает на самый свежий коммит.

* Вместо хеша последнего коммита можно написать слово HEAD — Git вас поймёт.

## Статусы файлов в Git

![alt жизненный цикл файла](image.png)

* Статусом untracked помечается файл, о существовании которого Git знает, но не следит за изменениями в нём. Этот статус — противоположность tracked, в который попадают все файлы, отслеживаемые Git.

* Файл переходит в статус staged после выполнения git add.

* Статус modified означает, что файл был изменён.

* Большинство файлов в проектах «шагает» по следующему циклу: «изменён» → «добавлен в список на коммит» → «закоммичен» → «изменён» → и так далее.

## Как читать git status

* Команда git status всегда подскажет, что происходит с файлом: например, он добавлен в список «на коммит» или ещё вообще не отслеживается, или изменён.

* git status показывает явно следующие состояния файлов: untracked, staged и modified.

* git status подсказывает, какие команды можно выполнить, чтобы поменять состояние файла.