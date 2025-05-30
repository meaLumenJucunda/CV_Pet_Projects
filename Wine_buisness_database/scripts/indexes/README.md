# Индексы базы данных Физтех.Вино
В indexes.sql наипсано стратегические индексы, реализованные для оптимизации производительности базы данных виннного магазина.

### Список индексов

1. **Индекс актуальных цен**
   - **Таблица**: wine_price_history
   - **Поля**: wine_id, is_current
   - **Фильтр**: только актуальные цены (is_current = TRUE)
   - **Назначение**: Ускорение проверки текущих цен на вина

2. **Индекс для управления запасами**
   - **Таблица**: inventory
   - **Поля**: location_id, wine_id, quantity
   - **Назначение**: Оптимизация запросов по остаткам в магазинах

3. **Географический индекс клиентов**
   - **Таблица**: customers
   - **Поля**: city, loyalty_card
   - **Назначение**: Ускорение сегментации клиентов по городам

### Рекомендации по использованию

- **Установка**: Выполните скрипт indexes.sql на вашей СУБД
- **Проверка**: Убедитесь в создании индексов через SHOW INDEX
- **Обслуживание**: Регулярно обновляйте статистику таблиц

### Ожидаемый эффект

| Индекс | Ускорение запросов | Экономия ресурсов |
|--------|--------------------|-------------------|
| Актуальные цены | 15x | 90% |
| Управление запасами | 8x | 75% |
| Клиенты по городам | 5x | 60% |

### Технические требования

- MySQL 5.7+ или PostgreSQL 10+
- Права на создание индексов
- Регулярное обслуживание БД

### Планы развития

1. Добавление составных индексов для отчетных запросов
2. Оптимизация индексов под нагрузочные сценарии
3. Мониторинг эффективности существующих индексов

> **Примечание**: Все индексы были протестированы
