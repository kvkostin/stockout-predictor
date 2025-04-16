# 🛒 Real-Time Shelf Monitoring System

## 📌 Описание
Система мониторинга и предсказания опустения полок в продуктовых магазинах в реальном времени. Используются потоковые данные о чеках, рассчитываются остатки и скорости продаж, формируются витрины и визуализация в Grafana, а при риске "опустения" — отправляются алерты в Telegram (возможно) 

## 🎯 Цель
Симулировать end-to-end пайплайн потоковой обработки данных, как в настоящем enterprise-решении для ритейла.

---

## 🔧 Архитектура
```
[Генератор чеков (faker)]
        ↓ Kafka (Docker)
        ↓
PySpark Streaming (Databricks или локально)
        ↓
  - PostgreSQL (Supabase / Render) — витрины
  - S3 / GCS (сырые данные)
        ↓
Grafana — Dashboards
MAYBE: Telegram Bot — Алерты
```

---

## ⚙️ Стек
- **Kafka** — стриминг событий (продажи)
- **PySpark Structured Streaming** — агрегации и расчёты
- **Databricks Community Edition** — среда выполнения пайплайна
- **PostgreSQL (Supabase)** — хранение витрин
- **S3 (AWS free-tier)** — Data Lake для сырья
- **Grafana** — визуализация метрик
- **Telegram Bot** — алерты при риске опустения
- **Docker / Airflow** — инфраструктура + оркестрация

---

## 📊 Что реализовано
- [ ] Генератор чеков и отправка в Kafka
- [ ] PySpark пайплайн (Databricks) для агрегаций
- [ ] Хранение агрегатов в PostgreSQL
- [ ] Выгрузка сырых данных в S3
- [ ] Графики и витрины в Grafana
- [ ] Telegram-бот с алертами
- [ ] README и скриншоты

---

## ✅ Результат
- 📦 End-to-End пайплайн, симулирующий enterprise-уровень
- 📈 Живой дашборд и telegram-алерты
  
---

## 🧪 Как запустить (в процессе)
1. Поднять Kafka с помощью Docker Compose
2. Запустить генератор чеков
3. Подключить Databricks notebook к Kafka
4. Запустить стриминг-агрегации
5. Проверить алерты и витрины

---

## 📂 Структура проекта (будет заполняться)
```
real-time-shelf-monitoring/
├── kafka/
├── spark/
├── airflow/
├── postgres/
├── s3/
├── grafana/
├── telegram_bot/
└── README.md
```

---

## 🚧 TODO / Roadmap
- [ ] Настроить Docker Compose для Kafka, PostgreSQL, Grafana
- [ ] Залить генератор чеков
- [ ] Написать Spark notebook (Databricks)
- [ ] Подключить Grafana к PostgreSQL
- [ ] Добавить Telegram-бота
- [ ] Оформить витрины + графики
- [ ] ?demo?
