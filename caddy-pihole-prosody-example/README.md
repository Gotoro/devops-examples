# English
This example spins up:
- the caddy proxy, with L4 plugin - this allows the caddy to actually filter requests the level 4 of the OSI transport layer (TCP). This is useful because we can actually inspect SNI or connection policies to route requests.
- the Pi-Hole DNS service to filter out all the ads and harmless websites from our requests.
- a prosody XMPP server - a modern communications server. This allows for Telegram-like communication between Android and iOS devices alike, with different apps for each platform.
- (NOT INCLUDED IN THIS EXAMPLE) a 3x-ui proxying suite, which sits in front of the server and allows for reliable communication.

All of the services are started by going into each folder and starting the docker compose file:
```bash
docker compose up --detach --build
```

The 3x-UI itself starts from the previously created dump.

# Russian
В этом примере запускаются:
– прокси-сервер Caddy с плагином L4 – это позволяет Caddy фильтровать запросы уровня 4 транспортного уровня OSI (TCP). Это полезно, поскольку мы можем проверять SNI или политики подключения для маршрутизации запросов.
– DNS-сервис Pi-Hole для фильтрации всей рекламы и безопасных веб-сайтов из наших запросов.
– XMPP-сервер Prosody – современный коммуникационный сервер. Он обеспечивает коммуникацию аля Telegram между устройствами Android и iOS, используя разные приложения для каждой платформы.
– (НЕ ВКЛЮЧЕН В ЭТОТ ПРИМЕР) Прокси комплекс 3x-UI, который располагается перед сервером и обеспечивает надёжную связь.

Все службы запускаются путём перехода в каждую папку и запуска файла docker compose:
```bash
docker compose up --detach --build
```
Сам 3x-UI запускается с ранее созданного дампа.
