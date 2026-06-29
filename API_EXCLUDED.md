# API Excluded From Current Coverage

Эти endpoint'ы сознательно исключены из текущей рабочей OpenAPI-документации: они не нужны для ближайших MCP/сервисов, слишком рискованные для тестов или не несут полезной нагрузки сейчас. Полная OpenAPI-заготовка сохранена в `API_EXCLUDED.openapi.yaml`, чтобы вернуть их без повторного reverse engineering.

## Auth

- `POST /auth/sign_up` — регистрация; по фронту: профиль + `{ login, email, password, phone }` -> `passwordToken`; не тестируем без тестовой почты.
- `POST /auth/send_confirm_code` — отправка кода; по фронту: `{ login, passwordToken }`; не тестируем, чтобы не отправлять письмо.
- `POST /auth/confirm_code` — подтверждение кода; по фронту: `{ login, passwordToken, code }`; не тестируем без кода.
- `POST /auth/change_password` — смена пароля по токену восстановления; по фронту: `{ login, passwordToken, newPassword }` -> `passwordToken`; не тестируем.
- `POST /auth/update_password` — смена пароля в профиле; по фронту: `{ oldPassword, newPassword, newPasswordRepeat }`; не тестируем.

## Bandlinks

- `POST /multi_links` — список или создание бандлинка; тело зависит от сценария и не полностью подтверждено.
- `POST /multi_links/name_exists` — проверка занятости имени.
- `PUT /multi_links/{id}` — обновление бандлинка.
- `DELETE /multi_links/{id}` — удаление бандлинка.
- `DELETE /releases/{releaseId}/multi_links/{linkId}` — открепление бандлинка от релиза.

## Packages

- `GET /packages/types` — типы пакетов; ранее была добавлена 200-схема.
- `GET /packages` — список пакетов; подтверждён wrapper, массив был пустой.
- `GET /packages/my` — мои пакеты; подтверждён wrapper, массив был пустой.
- `GET /packages/moderation` — пакеты на модерации.
- `POST /packages/{id}` — заказ пакета.
- `POST /packages/my/{id}/pay` — оплата пакета.
- `DELETE /packages/my/{id}` — удаление моего пакета.
