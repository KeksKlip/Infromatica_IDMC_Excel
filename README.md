# Informatica IDMC Excel

**Informatica IDMC Excel** is a utility for interacting with the Informatica Intelligent Data Management Cloud (IDMC) platform using Microsoft Excel and Power Query.

This project is designed to simplify daily tasks with metadata, jobs, and IDMC objects through a familiar Excel interface.

## Features

- Connect to IDMC via REST API
- Retrieve lists of tasks, mappings, connections, and other objects
- Load metadata into Excel
- Work with multiple organizations and environments


## Installation and Usage

1. Download the Excel file (`.xlsm`) containing macros.
2. Enable macros in Excel.
3. On the `Config` sheet, enter your Login URL and Username.
4. Click the Login button and enter your password.
5. The file includes 3 example sheets:
   - *B360 Tenant Model*
   - *B360 Model - Business Entity*
   - *B360 Model - Business Entity Fi*
6. Open Power Query Editor (`Data > Get Data > Launch Power Query Editor`) to modify IDMC REST API queries and transform the data as needed.

## Configuration

On the `Config` sheet, specify:

- `Login URL` — IDMC REST API login URL
- `Username` — your IDMC username

### Additional fields:

- `baseApiUrl` — Base URL for Administrator and CDI services  
- `frsApiUrl` — URL for services supporting Explorer in B360, CDI, CAI (undocumented API)
- `mdmApiUrl` — URL for MDM REST API
- `avosApiUrl` — URL for CAI REST API
- `Session Id` — used for authorization in IDMC REST API requests

These fields are filled automatically after login. In some cases, actual URLs may differ from those generated automatically. You can manually enter the correct URL and uncheck the `Overwrite URLs by login data` checkbox to prevent them from being overwritten during login.

### Authorization Script

On the `PS_Script` sheet, you'll find a PowerShell script for IDMC authorization. For everyday use, it is recommended to hide this sheet.

## License

MIT License

---

# Informatica IDMC Excel (на русском)

**Informatica IDMC Excel** — это утилита для взаимодействия с платформой Informatica Intelligent Data Management Cloud (IDMC) с использованием Microsoft Excel и Power Query.

Проект предназначен для упрощения повседневной работы с метаданными, заданиями и объектами IDMC через привычный интерфейс Excel.

## Возможности

- Подключение к IDMC через REST API
- Получение списка задач, маппингов, соединений и других объектов
- Загрузка метаданных в Excel
- Работа с несколькими организациями и средами


## Установка и использование

1. Скачайте файл Excel (`.xlsm`), содержащий макросы.
2. Разрешите выполнение макросов в Excel.
3. На листе `Config` укажите `Login URL` и `Username`.
4. Нажмите кнопку логина и введите пароль.
5. В файле представлены 3 листа для демонстрации работы:
   - *B360 Tenant Model*
   - *B360 Model - Business Entity*
   - *B360 Model - Business Entity Fi*
6. Откройте Power Query Editor (`Данные > Получить данные > Запуск редактора Power Query`), чтобы изменить запросы к IDMC REST API и преобразовать данные под свои нужды.

## Настройка

На листе `Config` укажите:

- `Login URL` — URL для авторизации в IDMC через REST API
- `Username` — имя пользователя IDMC

### Дополнительные поля:

- `baseApiUrl` — базовый URL для сервисов Administrator и CDI  
- `frsApiUrl` — URL для сервисов Explorer в B360, CDI, CAI (недокументированный API)
- `mdmApiUrl` — URL для MDM REST API
- `avosApiUrl` — URL для CAI REST API
- `Session Id` — используется для авторизации REST API-запросов к IDMC

Поля заполняются автоматически после авторизации. В некоторых случаях реальные URL могут отличаться от сгенерированных. Введите правильный URL вручную и снимите флажок `Overwrite URLs by login data`, чтобы избежать перезаписи при каждом входе.

### Скрипт авторизации

На листе `PS_Script` размещён PowerShell-скрипт для авторизации в IDMC. Для повседневного использования рекомендуется скрыть этот лист.

## Лицензия

MIT License
