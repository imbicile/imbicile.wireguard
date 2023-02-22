# Базовая установка Wireguard

Устаналивается сервер wireguard и генерируется произвольно один клиент

В дальнейшем можно настривать конфигурацию для себя и добавлять клиентов

# Описание работы

Каждый раз при запуске все ключи и адреса генерируются по новой

Сеть для линковки генерируется произвольно из диапазона `192.168.XXX.0/24`

После установки запускается служба

Пример конфигурации для клиента находся в комментарии файла конфигарации `/etc/wireguard/wg0.conf`

Ключи сервера и клиентра располагаются по пути `/etc/wireguard/`

# Переменные

Порт работы сервера `wireguard_server_port: 15604`

Сеть клиента `wireguard_client_network: "10.200.0.0/24"`

# Вариант плэйбука

```yaml
- name: Install Wireguard
  hosts:
    - all
  become: true
  roles:
    - role: imbicile.wireguard
      tags: wireguard
```
