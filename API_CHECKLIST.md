# API Checklist

## Легенда

- ✅ готово
- 🟡 частично
- ❌ не проверено
- ⛔ не трогать

## Auth

- ✅ `GET /auth/authenticate`
- ✅ `POST /auth/sign_in`

## Releases

- ✅ `POST /releases`
- ✅ `POST /releases/create`
- ✅ `GET /releases/filters`
- ✅ `GET /releases/{id}`
- ✅ `PUT /releases/{id}`
- ✅ `DELETE /releases/{id}`
- ✅ `PUT /releases/{id}/status/moderate`
- ✅ `GET /ddex/release/{id}`
- ✅ `POST /releases/{id}/cover`
- ✅ `POST /releases/{id}/tracks`
- ✅ `POST /releases/{id}/tracks/order`
- ✅ `PUT /releases/{id}/tracks/{trackId}`
- ✅ `DELETE /releases/{id}/tracks/{trackId}`
- ✅ `POST /releases/{id}/tracks/{trackId}/upload`
- ✅ `DELETE /releases/{id}/tracks/{trackId}/upload`
- ✅ `Release/TrackResponse`
- ✅ `genre/additionalGenres`
- ✅ `streamingPlatforms`

## Platforms

- ✅ `GET /platform/platforms/streaming`
- ✅ `GET /platform/platforms/social`
- ✅ `GET /platform/countries`

## Artists

- ✅ `GET /artists`
- ✅ `POST /artists`
- ✅ `PUT /artists/{id}`
- ✅ `DELETE /artists/{id}`

## Persons

- ✅ `GET /persons`
- ✅ `GET /persons/person-data`
- ✅ `POST /persons`
- ✅ `PUT /persons/{id}`
- ✅ `DELETE /persons/{id}`

## Labels

- ✅ `GET /labels`
- ✅ `POST /labels`
- ✅ `PUT /labels/{id}`

## Statistics

- ✅ `GET /statistics/filters`
- ✅ `POST /statistics`

## Finance

- ✅ `GET /finance/reports/filters`
- ✅ `POST /finance/reports/filters`
- ✅ `GET /finance/balance`
- ✅ `GET /finance/reports/file/{type}`
- ✅ `GET /finance/transactions/invoice/{currency}/history`
- ✅ `POST /finance/reports`
- ✅ `POST /finance/reports/detailed`
- ✅ `POST /finance/transactions`

## Client

- ✅ `GET /documents/contracts`
- ✅ `GET /documents/contracts/html`
- ✅ `GET /documents/contracts/template`
- ✅ `GET /documents/contracts/{contractId}/file`
- ✅ `GET /documents/contracts/{contractId}/amendment`

## Support

- ✅ `GET /support/types`
- ✅ `GET /support/cases/{id}`
- ✅ `POST /support`

## System

- ✅ `GET /locale`
- ✅ `GET /notifications`
- ✅ `GET /page`
