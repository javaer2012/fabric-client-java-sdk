# 使用hyperledger fabric client java sdk
## 一。 安装 fabric 1.0 alpha 容器

```
docker pull hyperledger/fabric-orderer:x86_64-1.0.0-alpha
docker pull hyperledger/fabric-peer:x86_64-1.0.0-alpha
docker pull hyperledger/fabric-zookeeper:x86_64-1.0.0-alpha
docker pull hyperledger/fabric-couchdb:x86_64-1.0.0-alpha
docker pull hyperledger/fabric-kafka:x86_64-1.0.0-alpha
docker pull hyperledger/fabric-ca:x86_64-1.0.0-alpha
docker pull hyperledger/fabric-ccenv:x86_64-1.0.0-alpha
docker pull hyperledger/fabric-javaenv:x86_64-1.0.0-alpha

#把 镜像tag成latest
docker tag hyperledger/fabric-orderer:x86_64-1.0.0-alpha hyperledger/fabric-orderer:latest 
docker tag  hyperledger/fabric-peer:x86_64-1.0.0-alpha  hyperledger/fabric-peer:latest
docker tag  hyperledger/fabric-zookeeper:x86_64-1.0.0-alpha  hyperledger/fabric-zookeeper:latest
docker tag  hyperledger/fabric-couchdb:x86_64-1.0.0-alpha hyperledger/fabric-couchdb:latest
docker tag  hyperledger/fabric-kafka:x86_64-1.0.0-alpha  hyperledger/fabric-kafka:latest
docker tag  hyperledger/fabric-ca:x86_64-1.0.0-alpha  hyperledger/fabric-ca:latest
docker tag  hyperledger/fabric-ccenv:x86_64-1.0.0-alpha  hyperledger/fabric-ccenv:latest
docker tag  hyperledger/fabric-javaenv:x86_64-1.0.0-alpha  hyperledger/fabric-javaenv:latest
```

## 二。 拉取fabric  client java sdk 项目

```
cd /Users/roamer/Documents/Projects/Hyperledger/roamer
git clone https://github.com/roamerxv/fabric-client-java-sdk.git
```

## 三。 清理 docker 容器和 images

```
docker rm -f $(docker ps -aq)
docker rmi -f dev-peer0-example_cc_go-1  dev-peer1-example_cc_go-1 dev-peer2-example_cc_go-1 dev-peer3-example_cc_go-1
docker rmi -f dev-peer0-example_cc_go-11 dev-peer1-example_cc_go-11 dev-peer2-example_cc_go-11 dev-peer3-example_cc_go-11
```

## 四。设置环境变量

```
cd /Users/roamer/Documents/Projects/Hyperledger/roamer/fabric-client-java-sdk
export WD=$PWD
```

## 五。运行测试用例

```
cd $WD/src/test
./cirun.sh
```