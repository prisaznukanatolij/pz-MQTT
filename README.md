## MQTT Broker Setup (Mosquitto)

У межах завдання було розгорнуто MQTT-брокер за допомогою Docker, налаштовано базову конфігурацію та виконано тестування роботи протоколу MQTT через клієнт.

## Структура проєкту
stt-pz-3/
├── stt-pz-3
│   ├── broker
│   │   ├── <mqtt>.conf
│   │   ├── docker-compose.yml
│   ├── screenshots            
│   ├── README.md
└──

## Розгортання MQTT-брокера
1. Перехід у директорію
cd stt-pz-3/broker
2. Запуск брокера
docker-compose up -d
3. Перевірка роботи контейнера
docker ps

## Основні поняття MQTT
Topic — канал для передачі повідомлень (наприклад: test/topic)
Publish — відправка повідомлення в topic
Subscribe — підписка на topic для отримання повідомлень
QoS (Quality of Service) — рівень гарантії доставки:
QoS 0 — доставка без гарантії
QoS 1 — доставка з підтвердженням
QoS 2 — гарантована одноразова доставка

## Підписка
 docker exec -it mqtt-broker mosquitto_sub -t "test/topic"

## Публікація
 docker exec -it mqtt-broker mosquitto_pub -t "test/topic" -m "Hello MQTT!"

## Результат
* MQTT-брокер успішно розгорнутий у Docker
* Конфігурація працює стабільно
* Реалізовано механізм Publish/Subscribe
* Повідомлення коректно передаються між клієнтами

У папці screenshots/ додано:
* підключення до брокера
* підписка на topic
* відправка повідомлення
* отримання повідомлення
