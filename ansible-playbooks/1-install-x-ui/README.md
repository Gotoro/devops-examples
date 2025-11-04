# English
This Ansible example:
- defines an Ansible playbook which spins up a 3x-ui stealth proxy
- includes a few roles:
1. 3x_ui role installs a 3x-ui stealth proxy suite, generates a few sane settings
2. downloads and installs a nodpi binary as a service - for bypassing DPI restrictions
3. hardens ssh a bit by pushing user's public ssh key to allow for non-password login

# Russian
Этот пример Ansible:
- определяет Ansible playbook, который запускает прокси-сервер 3x-ui
- включает в себя несколько ролей:
1. Роль 3x_ui устанавливает прокси-сервер 3x-ui, генерирует несколько адекватных настроек
2. Загружает и устанавливает исполняемый файл nodpi как службу для обхода ограничений DPI
3. Усиливает защиту SSH, передавая публичный ключ SSH пользователя для дальнейшнего входа без пароля
