### 1

```zsh
docker run busybox
```

### 2

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

### 3

```zsh
docker ps -a
```

вывод:

```zsh
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                          PORTS     NAMES
c34b2afd4157   busybox   "ping -c 7 netology.…"   About a minute ago   Exited (0) 44 seconds ago                 pinger
fd7d7912bbf3   busybox   "sh"                     About a minute ago   Exited (0) About a minute ago             quizzical_chaum
```

### 4

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

### 5

```zsh
docker start pinger
```

```zsh
pinger
```

### 6

```zsh
docker ps -a
```

```zsh
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                          PORTS     NAMES
c34b2afd4157   busybox   "ping -c 7 netology.…"   About a minute ago   Exited (0) 44 seconds ago                 pinger
fd7d7912bbf3   busybox   "sh"                     About a minute ago   Exited (0) About a minute ago             quizzical_chaum
```

### 7

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
