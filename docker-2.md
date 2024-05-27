### 1 Загрузите образ node версии 22.2.0

```zsh
docker run node:22.2.0
```

вывод:

```zsh
Unable to find image 'node:22.2.0' locally
22.2.0: Pulling from library/node
91e301773f03: Pull complete
15856ca26414: Pull complete
30ed4c127913: Pull complete
feb30c5ba2d1: Pull complete
86d4106dc50d: Pull complete
5227f166ddfd: Pull complete
59d8b5b43a70: Pull complete
0d92e3ac5e54: Pull complete
Digest: sha256:a8ba58f54e770a0f910ec36d25f8a4f1670e741a58c2e6358b2c30b575c84263
Status: Downloaded newer image for node:22.2.0
```

### 2 Запустите контейнер node в интерактивном режиме подключения терминала, поименуйте его mynode, передайте две переменные среды NAME=<ваше имя> и SURNAME=<ваша фамилия>

```zsh
docker run --name mynode -it -e NAME=evgenii -e SURNAME=korolkov node:22.2.0
```

вывод:

```zsh
Welcome to Node.js v22.2.0.
Type ".help" for more information.
```

### 3 В интерактивной среде выполнения node выполните скрипт, который выведет на экран приветсвтие: Привет, <ваше имя> <ваша фамилия>!, эти данные должны быть получены из переменных среды

```zsh
`Привет ${process.env.NAME} ${process.env.SURNAME}`
```

вывод:

```zsh
'Привет evgenii korolkov'
```

### 4 Остановите контейнер

```zsh
docker stop mynode
```

### 5 Удалите образ node версии 22.2.0

```zsh
docker rmi node:22.2.0
```

вывод:

```zsh
Untagged: node:22.2.0
Untagged: node@sha256:a8ba58f54e770a0f910ec36d25f8a4f1670e741a58c2e6358b2c30b575c84263
Deleted: sha256:c11c521e4d5971c0b7097963b1b0268346be8bf55cac3221de545604ebe46871
Deleted: sha256:475389b5895d4598d7d0995d326acd2efa60b985de8506aed4408d12e327e199
Deleted: sha256:87ee9c33cc5522f94d82ef98c995e8c26bc46677da41e96fc2f281c5f88937ae
Deleted: sha256:17b3d90abbb5fa468974dc284299117e2b4661954ae21486b0d0b42d2429ea8e
Deleted: sha256:a4c61c3a3537ab3089c3a63a4ffa6477e7d7ea5acb14dc5c869798a3a1038f57
Deleted: sha256:2f0b170a394cb47c6ceceecfb292a73b9035922d9d1b3c97db1f33e3a44a61af
Deleted: sha256:1256aad2ecdfcc0ff37f16dd06d4b4c4ede232924fd5aa8907d2a6449a289ca1
Deleted: sha256:0d60957ceb6800aebcef123791a51940b6580ed3577e96f995161d6d13dca62d
Deleted: sha256:9f6b5e87c1209b3370798b8f074361950ec07dbf7319cc662d4c1574413a3888
```
