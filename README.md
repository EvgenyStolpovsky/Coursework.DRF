## Курсовая DRF

#### Критерии приемки курсовой работы
    - Настроили CORS.
    - Настроили интеграцию с Telegram.
    - Реализовали пагинацию.
    - Использовали переменные окружения.
    - Все необходимые модели описаны или переопределены.
    - Все необходимые эндпоинты реализовали.
    - Настроили все необходимые валидаторы.
    - Описанные права доступа заложены.
    - Настроили отложенную задачу через Celery.
    - Проект покрыли тестами как минимум на 80%.
    - Код оформили в соответствии с лучшими практиками.
    - Имеется список зависимостей.

#### Контекст. В 2018 году Джеймс Клир написал книгу «Атомные привычки», которая посвящена приобретению новых полезных привычек и искоренению старых плохих привычек. Заказчик прочитал книгу, впечатлился и обратился к вам с запросом реализовать трекер полезных привычек. В рамках учебного курсового проекта реализуйте бэкенд-часть SPA веб-приложения.

#### Описание задач.
Добавьте необходимые модели привычек.
Реализуйте эндпоинты для работы с фронтендом.
Создайте приложение для работы с Telegram и рассылками напоминаний.

#### Модели
Привычка:
Пользователь — создатель привычки.
Место — место, в котором необходимо выполнять привычку.
Время — время, когда необходимо выполнять привычку.
Действие — действие, которое представляет из себя привычка.
Признак приятной привычки — привычка, которую можно привязать к выполнению полезной привычки.
Связанная привычка — привычка, которая связана с другой привычкой, важно указывать для полезных привычек, но не для приятных.
Периодичность (по умолчанию ежедневная) — периодичность выполнения привычки для напоминания в днях.
Вознаграждение — чем пользователь должен себя вознаградить после выполнения.
Время на выполнение — время, которое предположительно потратит пользователь на выполнение привычки.
Признак публичности — привычки можно публиковать в общий доступ, чтобы другие пользователи могли брать в пример чужие привычки.

#### Валидаторы
Исключить одновременный выбор связанной привычки и указания вознаграждения.
Время выполнения должно быть не больше 120 секунд.
В связанные привычки могут попадать только привычки с признаком приятной привычки.
У приятной привычки не может быть вознаграждения или связанной привычки.
Нельзя выполнять привычку реже, чем 1 раз в 7 дней.

#### Пагинация
Для вывода списка привычек реализовать пагинацию с выводом по 5 привычек на страницу.

#### Права доступа
Каждый пользователь имеет доступ только к своим привычкам по механизму CRUD.
Пользователь может видеть список публичных привычек без возможности их как-то редактировать или удалять.
Эндпоинты
Регистрация
Авторизация
Список привычек текущего пользователя с пагинацией
Список публичных привычек
Создание привычки
Редактирование привычки
Удаление привычки

#### Интеграция
Для полноценной работы сервиса необходим реализовать работу с отложенными задачами для напоминания о том, в какое время какие привычки необходимо выполнять.
Для этого потребуется интегрировать сервис с мессенджером Telegram, который будет заниматься рассылкой уведомлений.

#### Безопасность
Для проекта необходимо настроить CORS, чтобы фронтенд мог подключаться к проекту на развернутом сервере.

#### Документация проекта: http://127.0.0.1:8000/swagger/