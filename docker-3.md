### 1 Загрузите образ node версии 22.2.0

```zsh
docker run node:22.2.0
```

### 2 Запустите контейнер с именем first_node из образа node версии 22.2.0 в фоновом режиме, подключив папку data из текущей директории в /var/first/data контейнера

```zsh
docker run --name first_node -d --rm -v $(pwd)/data:/var/first/data node:22.2.0 sleep infinity
```

добавил --rm, для автоматического удаления после остановки контейнера
вывод:

```zsh
28700e3afad60fa1c6295e35c83f74c20c6a36593cadac5ea977ca50760e29df
```

### 3 Запустите контейнер с именем second_node из образа node версии 22.2.0 в фоновом режиме, подключив папку data из текущей директории в /var/second/data контейнера

```zsh
docker run --name second_node -d --rm -v $(pwd)/data:/var/second/data node:22.2.0 sleep infinity
```

вывод:

```zsh
3b514963854bd5d6443fdca4bf1a8a1b65f1f64815e9f9983ac294d3ca858675
```

### 4 Подключитесь к контейнеру first_node с помощью exec и создайте текстовый файл любого содержания в /var/first/data

```zsh
docker exec -it first_node /bin/bash
cd /var/first/data/
echo "first_node text" > first_node.txt
```

### 5 Добавьте еще один файл в папку data на хостовой машине

```zsh
cd data && echo "new text" > more_text.txt
```

### 6 Подключитесь к контейнеру second_node с помощью exec и получите список файлов в директории /var/second/data, выведете на экран содержимое файлов

```zsh
docker exec -it second_node /bin/bash
cd /var/second/data/
ls
```

вывод

```zsh
first_node.txt  more_text.txt
```

### 7 Остановите оба контейнера

```zsh
docker stop first_node second_node
```

вывод

```zsh
first_node
second_node
```

### 8 Удалите оба контейнера

Контейнеры были удаленны, так как использован флаг --rm при их запуске

### 9 Удалите образ node версии 22.2.0

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
