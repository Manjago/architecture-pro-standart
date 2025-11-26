```mermaid
gantt
    title RoadMap MVP "Открытие депозитов онлайн" (6 месяцев)
    dateFormat YYYY-MM-DD
    
    section Фаза 1: Фундамент
    АБС API Layer                    :crit, abs_api, 2025-12-01, 4w
    Rate Management Service          :crit, rate_svc, 2025-12-01, 3w
    Deposit Service                  :crit, dep_svc, after rate_svc, 4w
    PostgreSQL + API Gateway Setup   :infra, 2025-12-01, 2w
    Форма заявки на Сайте           :site_form, 2025-12-08, 3w
    
    section Фаза 2: Клиентские интерфейсы
    Frontend Интернет-банка (React)  :crit, frontend, after dep_svc, 4w
    Админка бэк-офиса               :admin, after dep_svc, 3w
    Notification Service (SMS)       :notif, after dep_svc, 2w
    API Gateway (Security)           :gateway, after infra, 2w
    
    section Фаза 3: Интеграция КЦ
    REST API для кол-центра         :cc_api, after rate_svc, 1w
    Доработка внутреннего КЦ        :cc_internal, after cc_api, 2w
    Rate Export Service             :export_svc, after cc_api, 2w
    SFTP Integration                :sftp, after export_svc, 1w
    Импорт в партнёрский КЦ         :cc_partner, after sftp, 2w
    
    section Фаза 4: Тестирование и запуск
    Интеграционное тестирование     :crit, int_test, after frontend admin notif, 3w
    Нагрузочное тестирование        :load_test, after int_test, 2w
    Пилотный запуск (1 регион)      :crit, pilot, after load_test, 2w
    Мониторинг и фиксы              :fixes, after pilot, 2w
    Полный запуск (все регионы)     :crit, launch, after fixes, 2w
    
    section Сквозные задачи
    Документация                    :doc, 2025-12-01, 26w
    Обучение команд                 :training, 2025-12-01, 26w
```
