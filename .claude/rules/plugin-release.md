---
paths:
  - "plugins/*/package.json"
  - "plugins/*/server.ts"
---

# Выпуск версии плагина

- Номер версии бывает не только в `package.json`: `grep -rn '<старая версия>' plugins/<имя> --include=*.ts --include=*.tsx`
  перед коммитом. В `file-manager` есть `PLUGIN_VERSION` в `server.ts`, его показывают панель и строка загрузки в логе.
- Корень `package-lock.json` (`version` и `packages[""].version`) поднимать вместе с `package.json`.
- Полный прогон тестов — после правки версии, а не до неё. 24.11.2026 тег `file-manager/v0.11.2` ушёл
  с `PLUGIN_VERSION = "0.11.1"`: тест сверки версий упал бы, но прогон был до правки, пришлось выпускать 0.11.3.
