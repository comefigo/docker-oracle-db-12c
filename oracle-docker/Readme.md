# Oracle Database dockerfile build

Oracle Database 12c R2 Standard EditionのDocker版のビルド方法です  

元ネタは[こちら](https://github.com/oracle/docker-images/tree/master/OracleDatabase/SingleInstance)です

## 前提条件

- Docker CE for Windowsがインストールされていること
- このリポジトリが配置されているドライブがDockerの共有ドライブ設定で共有許可されていること
- Disk容量の空きが25GB以上あること
- メモリーの空きが4GB以上あること

## 事前準備

[OTN(Oracle Technology Network)]((http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html))からOracle Database 12c Release 2(12.2.0.1)のインストーラを入手し、installerディレクトリに配置

## 初期設定

SID、PDB、パスワードなどはoracle.envに記載されていますので、適宜変更してください


## 初期データ

起動時に都度init-data内のSQL/shを流すようにしています（名前順にロードされる）  
なので、テスト用に再利用したい場合は、一度TABLEをクリーンアップするSQLを配置してから、  


## データの永続化

データはoracle-dataフォルダに永続化されています

## 起動

```
> docker-compose up -d
```

## 停止

```
> docker-compose stop
```

## 破棄

```
> docker-compose down
```
