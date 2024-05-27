### 1 Загрузите образ busybox последней версии

```zsh
docker run busybox
```

### 2 Запустите новый контейнер busybox с командой ping сайта netology.ru, и количеством пингов 7, поименуйте контейнер pinger

```zsh
docker run --name pinger busybox ping -c 7 netology.ru
```

вывод:

```zsh
PING netology.ru (104.22.41.171): 56 data bytes
64 bytes from 104.22.41.171: seq=0 ttl=63 time=108.286 ms
64 bytes from 104.22.41.171: seq=1 ttl=63 time=105.721 ms
64 bytes from 104.22.41.171: seq=2 ttl=63 time=105.251 ms
64 bytes from 104.22.41.171: seq=3 ttl=63 time=105.794 ms
64 bytes from 104.22.41.171: seq=4 ttl=63 time=105.582 ms
64 bytes from 104.22.41.171: seq=5 ttl=63 time=105.764 ms
64 bytes from 104.22.41.171: seq=6 ttl=63 time=105.771 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 105.251/106.024/108.286 ms
```

### 3 Выведите на список всех контейнеров - запущенных и остановленных

```zsh
docker ps -a
```

вывод:

```zsh
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                          PORTS     NAMES
c34b2afd4157   busybox   "ping -c 7 netology.…"   About a minute ago   Exited (0) 44 seconds ago                 pinger
fd7d7912bbf3   busybox   "sh"                     About a minute ago   Exited (0) About a minute ago             quizzical_chaum
```

### 4 Выведите на экран логи контейнера с именем pinger

```zsh
docker logs pinger
```

вывод:

```zsh
PING netology.ru (104.22.41.171): 56 data bytes
64 bytes from 104.22.41.171: seq=0 ttl=63 time=108.286 ms
64 bytes from 104.22.41.171: seq=1 ttl=63 time=105.721 ms
64 bytes from 104.22.41.171: seq=2 ttl=63 time=105.251 ms
64 bytes from 104.22.41.171: seq=3 ttl=63 time=105.794 ms
64 bytes from 104.22.41.171: seq=4 ttl=63 time=105.582 ms
64 bytes from 104.22.41.171: seq=5 ttl=63 time=105.764 ms
64 bytes from 104.22.41.171: seq=6 ttl=63 time=105.771 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 105.251/106.024/108.286 ms
```

### 5 Запустите второй раз контейнера с именем pinger

```zsh
docker start pinger
```

```zsh
pinger
```

### 6 Выведите на список всех контейнеров - запущенных и остановленных

```zsh
docker ps -a
```

```zsh
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                          PORTS     NAMES
c34b2afd4157   busybox   "ping -c 7 netology.…"   About a minute ago   Exited (0) 44 seconds ago                 pinger
fd7d7912bbf3   busybox   "sh"                     About a minute ago   Exited (0) About a minute ago             quizzical_chaum
```

### 7 Выведите на экран логи контейнера с именем pinger

```zsh
docker logs pinger
```

```zsh
PING netology.ru (104.22.41.171): 56 data bytes
64 bytes from 104.22.41.171: seq=0 ttl=63 time=102.202 ms
64 bytes from 104.22.41.171: seq=1 ttl=63 time=103.042 ms
64 bytes from 104.22.41.171: seq=2 ttl=63 time=103.103 ms
64 bytes from 104.22.41.171: seq=3 ttl=63 time=108.965 ms
64 bytes from 104.22.41.171: seq=4 ttl=63 time=103.170 ms
64 bytes from 104.22.41.171: seq=5 ttl=63 time=102.267 ms
64 bytes from 104.22.41.171: seq=6 ttl=63 time=103.324 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 102.202/103.724/108.965 ms
PING netology.ru (104.22.41.171): 56 data bytes
64 bytes from 104.22.41.171: seq=0 ttl=63 time=101.627 ms
64 bytes from 104.22.41.171: seq=1 ttl=63 time=107.745 ms
64 bytes from 104.22.41.171: seq=2 ttl=63 time=101.383 ms
64 bytes from 104.22.41.171: seq=3 ttl=63 time=101.845 ms
64 bytes from 104.22.41.171: seq=4 ttl=63 time=110.857 ms
64 bytes from 104.22.41.171: seq=5 ttl=63 time=103.212 ms
64 bytes from 104.22.41.171: seq=6 ttl=63 time=103.652 ms

--- netology.ru ping statistics ---
7 packets transmitted, 7 packets received, 0% packet loss
round-trip min/avg/max = 101.383/104.331/110.857 ms

```

### 8 Определите по логам общее количество запусков команды ping и какое общее количество отправленых запросов

Общее количесвто запусков команды ping - 2, отправленых запросов - 14

### 9 Удалите контейнер с именем pinger

```zsh
docker rm pinger
```

вывод:

```zsh
pinger
```

### 10 Удалите образ busybox

```zsh
docker rmi busybox
```

вывод:

```zsh
Untagged: busybox:latest
Untagged: busybox@sha256:5eef5ed34e1e1ff0a4ae850395cbf665c4de6b4b83a32a0bc7bcb998e24e7bbb
Deleted: sha256:23d6e6de0b63623e44a1ec59746682c77f197702ae77264eb287fa5119256f8a
Deleted: sha256:4712e14e7e366854795a6664128e48cf7ad6199328abd09caadde8f5f3c0aa06
```
