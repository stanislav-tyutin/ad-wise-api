---
title: AdWise Rest API

language_tabs:
  - ruby
  - http

includes:
  - errors

search: true
---

# Введение

В данном документе приведена схема REST-API для проекта AdWise.

API endpoints, параметры и ожидаемые ответы.

Имеются примеры кода для взаимодействия с API.

# Регистрация

## Регистрация через email

### HTTP Запрос
`POST /api/profile`

### Параметры запроса

Параметр  | Описание
--------- | -------
email     | email
password  | пароль

## Регистрация через OAuth

### HTTP Запрос

`GET /api/oauth/callback`

### Параметры запроса

Параметр          | Описание
----------------- | -------
code              | код OAuth
error             | ошибка
error_resaon      | причина ошибки
error_description | описание ошибки

# Сессии

## Вход в аккаунт (OAuth)
Вход через OAuth производится аналогично авторизации

## Вход в аккаунт (Email)
### HTTP Запрос
`POST /api/session`

### Параметры запроса

Параметр  | Описание
--------- | -------
email     | email
password  | пароль

## Выход из аккаунта
### HTTP Запрос
`DELETE /api/session`


# Профиль

## Получение информации
### HTTP Запрос
`GET /api/profile/me`

## Обновление информации
### HTTP Запрос
`PATCH /api/profile/me`

## Получение информации о другом пользователе
### HTTP Запрос
`GET /api/profile/:user_id`

# Календарь
## Просмотр календаря
### HTTP Запрос
`GET /api/calendar`

## Добавить запись
### HTTP Запрос
`POST /api/calendar`

## Редактировать запись
### HTTP Запрос
`PATCH /api/calendar/:id`

## Удалить запись
### HTTP Запрос
`DELETE /api/calendar/:id`

# База рекламодателей
### HTTP Запрос
`GET /api/advertisers`
В параметрах передаются требуемые фильтры

# База блогеров
### HTTP Запрос
`GET /api/influencers`
В параметрах передаются требуемые фильтры

# Рекламные кампании
## Поиск
### HTTP запрос
`GET /api/ad_campaigns`
В параметрах передаются требуемые фильтры

## Просмотр информации
### HTTP запрос
`GET /api/ad_campaigns/:id`

## Создание
### HTTP запрос
`POST /api/ad_campaigns`

## Редактирование
### HTTP запрос
`PATCH /api/ad_campaigns/:id`

## Удаление
### HTTP запрос
`DELETE /api/ad_campaigns/:id`

# Отклики
## Список откликов
### HTTP запрос
`GET /api/ad_campaigns/:id/offers`

## Откликнуться (для блогера)
### HTTP запрос
`POST /api/ad_campaigns/:id/offer`

## Отозвать отклик (для блогера)
### HTTP запрос
`DELETE /api/ad_campaigns/:id/offer`

## Принять предложение (для блогера)
### HTTP запрос
`PATCH /api/ad_campaigns/:id/offer`

## Создать предложение (для рекламодателя)
### HTTP запрос
`POST /api/ad_campaigns/:id/offers`

## Отозвать предложение (для рекламодателя)
### HTTP запрос
`DELETE /api/ad_campaigns/:id/offers/:id`

## Выбрать блогера (для рекламодателя)
### HTTP запрос
`PATCH /api/ad_campaigns/:id/offers`

# Отклики (после подтвержения)

## Просмотр предложений
### HTTP запрос
`GET /api/offers`
В параметрах передаются требуемые фильтры

## Просмотр информации о предложении
### HTTP запрос
`GET /api/offers/:id`

## Жизненый цикл преложения
### HTTP запрос
`PATCH /api/offers/:id`

## Удаление предложения
### HTTP запрос
`DELETE /api/offers/:id`

# Загрузка файлов
### HTTP запрос
`POST /api/uploads`
Универсальный endpoint для загрузки контента

