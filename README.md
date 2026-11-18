# Каталог магазина из Java

Покажи оператору остаток по SKU и проверь, что JDBC и Hibernate возвращают одинаковую карточку.

**Этап 05** · Java 21 · JDBC · Hibernate

[Этап 05](https://github.com/1ommyFi7in/java-backend-roadmap/blob/main/%D0%9E%D0%B2%D0%B5%D1%80%D0%B2%D1%8C%D1%8E.md#05-jdbc-hibernate-%D0%B8-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B9) · [Техническое задание](SPECIFICATION.md) · [Тестовые данные](https://github.com/1ommyFi7in/java-backend-roadmap/blob/main/%D0%9F%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D1%8B/%D0%9A%D0%BE%D0%BD%D1%82%D1%80%D0%B0%D0%BA%D1%82%D1%8B%20%D0%B8%20%D1%82%D0%B5%D1%81%D1%82%D0%BE%D0%B2%D1%8B%D0%B5%20%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5%20%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0.md) · [Весь маршрут](https://github.com/1ommyFi7in/java-backend-roadmap)

> [!NOTE]
> Учебное задание. В репозитории находятся постановка, примеры и критерии приёмки. Реализацию добавляй по мере прохождения этапа.

## Результат этапа

| Что собрать | Что отработать |
| --- | --- |
| Два адаптера одной модели каталога, CLI и интеграционные тесты с PostgreSQL. | PreparedStatement, маппинг JPA, логирование, изолированные фикстуры. |

## Как выглядит результат

```text
> show 11 --via jdbc
11 SKU-11 Кружка 49.90 stock=3
> show 11 --via jpa
11 SKU-11 Кружка 49.90 stock=3
> show 999 --via jpa
ERROR PRODUCT_NOT_FOUND
```

В чате запрос `/product 11` возвращает `Кружка — 49.90, в наличии 3`.

## Проверка перед сдачей

- [ ] `mvnw verify` проверяет одинаковый результат JDBC и Hibernate и обработку неизвестного товара. Вручную проверить вывод при отключённой БД. При подключённом боте проверить корректную и неизвестную команду.

## Начать работу

```sh
git clone https://github.com/1ommyFi7in/shop-java-catalog.git
cd shop-java-catalog
```

Открой [техническое задание](SPECIFICATION.md), подготовь входные данные и начни с основного сценария. Команды запуска и проверок добавь после первого рабочего прогона.

[← Модель магазина в PostgreSQL](https://github.com/1ommyFi7in/shop-postgres) · [Конкурентный резерв и диагностика JVM →](https://github.com/1ommyFi7in/shop-concurrency-jvm)
