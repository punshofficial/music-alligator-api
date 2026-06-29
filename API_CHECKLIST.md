# API Checklist

## Легенда

- ✅ проверено и описано
- 🟡 частично проверено
- ❌ не проверено
- ⛔ не трогать без отдельного подтверждения

## Auth

- ✅ `GET /auth/authenticate` — 200-схема добавлена
- ❌ `POST /auth/sign_in`
- ❌ `POST /auth/sign_up`
- ❌ `POST /auth/send_confirm_code`
- ❌ `POST /auth/confirm_code`
- ⛔ `POST /auth/change_password`
- ⛔ `POST /auth/update_password`

## Releases

- ✅ `POST /releases` — список и поиск по `search`, 201-схема добавлена
- ✅ `POST /releases/create` — создан тестовый draft-релиз; после проверок удалён
- ✅ `GET /releases/filters` — 200/400-схемы добавлены
- ⛔ `GET /releases/update/track` — служебный endpoint
- ✅ `GET /releases/{id}` — 200-схема подтверждена по `releaseId` из списка
- ✅ `PUT /releases/{id}` — проверено на тестовом draft-релизе
- ✅ `Release/TrackResponse` — ключи ответа тестового релиза сверены со схемами; добавлены `client`, `text`, `isFromMigration`, `artists[].platforms`
- ✅ `DELETE /releases/{id}` — проверено на тестовом релизе, 200 `StatusResponse`; последующий GET вернул 404 `RELEASE_NOT_FOUND`
- ⛔ `PUT /releases/{id}/status/moderate`
- ✅ `GET /ddex/release/{id}` — статусы выгрузки по площадкам, проверено на draft/uploaded/released релизах
- ✅ `POST /releases/{id}/cover` — проверено на тестовом релизе, multipart `file`, 201 `MediaUploadResponse`
- ✅ `POST /releases/{id}/tracks/order` — проверено на тестовом релизе, `order: [{ trackOrder, trackId }]`, 201 `StatusResponse`
- ✅ `PUT /releases/{id}/tracks/{trackId}` — проверено на тестовом draft-релизе
- ✅ `genre/additionalGenres` — формат подтверждён по фронту и тестовому релизу: основной жанр `{ genreId }` или `{ genreId, subGenreId }`, дополнительные жанры массивом таких объектов
- ✅ `streamingPlatforms` — при сохранении тестового релиза выбранные площадки могут дополняться связанными ID (например, Shazam/KION Music)
- ✅ `DELETE /releases/{id}/tracks/{trackId}` — проверено на втором треке тестового релиза, 200 `StatusResponse`
- ✅ `POST /releases/{id}/tracks/{trackId}/upload` — проверено на тестовом релизе, multipart `file`, 201 `MediaUploadResponse`; после WAV сервер добавляет mp3
- ⛔ `DELETE /releases/{id}/tracks/{trackId}/upload`
- ✅ `POST /releases/{id}/tracks` — создан второй трек в тестовом релизе, 201 `CreateTrackResponse`

## Media

- ❌ `POST /media/upload`

## Platforms

- ✅ `GET /platform/platforms/streaming` — 200/400-схемы добавлены
- ✅ `GET /platform/platforms/social` — 200-схема добавлена
- ✅ `GET /platform/countries` — 200/400-схемы добавлены

## Artists

- ✅ `GET /artists` — 200-схема добавлена
- ✅ `POST /artists` — создан тестовый артист
- ✅ `PUT /artists/{id}` — проверено на тестовом артисте, Apple Music/Spotify с пустым `platformId`
- ⛔ `DELETE /artists/{id}`

## Persons

- ✅ `GET /persons` — 200-схема добавлена
- ✅ `GET /persons/person-data` — 200-схема добавлена
- ✅ `POST /persons` — создан тестовый участник
- ❌ `PUT /persons/{id}` — тестировать только на тестовой сущности
- ⛔ `DELETE /persons/{id}`

## Labels

- ✅ `GET /labels` — 200-схема добавлена
- ✅ `POST /labels` — создан тестовый лейбл
- ❌ `PUT /labels/{id}` — тестировать только на тестовой сущности

## Bandlinks

- 🟡 `POST /multi_links` — может быть списком или созданием, нужен безопасный payload
- ❌ `POST /multi_links/name_exists`
- ❌ `PUT /multi_links/{id}` — тестировать только на тестовой сущности
- ⛔ `DELETE /multi_links/{id}`
- ⛔ `DELETE /releases/{releaseId}/multi_links/{linkId}`

## Statistics

- 🟡 `GET /statistics/filters` — 200-схема добавлена, низкий приоритет
- 🟡 `POST /statistics` — read-like, низкий приоритет

## Finance

- 🟡 `GET /finance/reports/filters` — 200-схема добавлена, низкий приоритет
- 🟡 `GET /finance/balance` — 200-схема добавлена, низкий приоритет
- ❌ `GET /finance/reports/file/{type}` — низкий приоритет
- ❌ `GET /finance/transactions/invoice/{currency}/history` — низкий приоритет
- 🟡 `POST /finance/reports` — низкий приоритет
- 🟡 `POST /finance/reports/detailed` — низкий приоритет
- 🟡 `POST /finance/transactions` — низкий приоритет
- ⛔ `POST /finance/transactions/create`

## Client

- 🟡 `GET /client` — подтверждён 404
- 🟡 `GET /client/contract_data` — подтверждён 404
- ✅ `GET /documents/contracts` — 200-схема добавлена
- ⛔ `POST /client/avatar`
- ⛔ `DELETE /client/avatar`
- ⛔ `POST /client/bank_data`
- ⛔ `POST /client/document`
- ❌ `POST /documents/contracts`

## Packages

- ✅ `GET /packages/types` — 200-схема добавлена
- 🟡 `GET /packages` — подтверждён wrapper, массив был пустой
- 🟡 `GET /packages/my` — подтверждён wrapper, массив был пустой
- ⛔ `GET /packages/moderation`
- ⛔ `POST /packages/{id}`
- ⛔ `POST /packages/my/{id}/pay`
- ⛔ `DELETE /packages/my/{id}`

## Support

- 🟡 `GET /support/types` — 200-схема добавлена, низкий приоритет
- ❌ `GET /support/cases/{id}` — низкий приоритет
- 🟡 `POST /support` — низкий приоритет
- ⛔ `POST /support/cases`
- ⛔ `POST /support/cases/{id}/message/`
- ⛔ `POST /support/cases/{id}/media`

## System

- ✅ `GET /locale` — 200-схема добавлена
- ✅ `GET /notifications` — 200-схема добавлена
- ✅ `GET /page` — 200-схема добавлена
