### 1

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

### 2

```zsh
docker run --name mynode -it -e NAME=evgenii -e SURNAME=korolkov node:22.2.0
```

вывод:

```zsh
Welcome to Node.js v22.2.0.
Type ".help" for more information.
```

### 3

```zsh
`Привет ${process.env.NAME} ${process.env.SURNAME}`
```

вывод:

```zsh
'Привет evgenii korolkov'
```

### 4

```zsh
.exit
```

### 5

```zsh
docker rm mynode
```

вывод:

```
mynode
```
