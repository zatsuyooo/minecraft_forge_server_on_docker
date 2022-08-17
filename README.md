# minecraft_forge_server_on_docker
MinecraftのForge ServerをDocker上で動かします。  
イメージは[itzg/docker-minecraft-server](https://github.com/itzg/docker-minecraft-server)を使用しています。

## 事前準備
- docker-compose.ymlを編集する
- 使用するメモリを設定する
    ```yaml
    environment:
        - MEMORY=<number>G
    ```
- MinecraftとForgeのバージョンを指定する
    ```yaml
    environment:
      - VERSION=<minecraft version>
      - FORGEVERSION=<forge version>
    ```
## サーバーを起動する
    ```bash
    cd minecraft_forge_server_on_docker
    sudo docker compose up -d
    ```

## サーバーコンソールに接続する
```bash
sudo docker attach mc
```
Ctrl-p, Ctrl-qでデタッチ可能

## ホワイトリストにユーザーを追加する
```bash
sudo docker attach mc
whitelist add <player>
```

## オペレーター権限をユーザーに付与する
```bash
sudo docker attach mc
op <player>
```