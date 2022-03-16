# MQTT example (eclipse-mosquitto)

目的：簡単にMQTT(eclipse-mosquitto)を試してみる

## Mosquitto on Docker

起動

```
% docker run -it --rm -p 1883:1883 -p 9001:9001 \
    -v $(pwd)/config/mosquitto.conf:/mosquitto/config/mosquitto.conf \
    -v $(pwd)/data:/mosquitto/data \
    -v $(pwd)/log:/mosquitto/log \
    -d eclipse-mosquitto
```
MQTTとWebSocketsの両方のプロトコルを利用できる
port:1883 mqtt接続(TCP)
port:9001 Websocket接続

## mosquitto_pub と mosquitto_sub

Termnalを２つ以上使って簡単にmosquitto_pub と mosquitto_subを確認

Terminal1(Sub)
Terminal2(Pub)

1. Terminal1(Sub)
```
トピック:mytopicをSubする
/ # mosquitto_sub -h localhost -t mytopic
```

1. Terminal2(Pub)
```
トピック:mytopicへメッセージをPubする
/ # mosquitto_pub -h localhost -m "my test message" -t mytopic
```

1. Terminal1(Sub)
```
トピック:mytopicが受信できたことが確認できる
/ # mosquitto_sub -h localhost -t mytopic
my test message
```

# MQTT version 5 (-D /--property)
-V で version 5 を指定して、v5の機能を利用してみる

pub (property に response-topic をつける)
```
/ # mosquitto_pub -h localhost -m "my test message111" -t aaa/bbb/mytopic -D PUBLISH response-topic xxxyyyzzz12345
```

sub (-F で出力する項目を選択して response-topic を受け取る)
```
/ # mosquitto_sub -h localhost -t aaa/bbb/mytopic -V mqttv5 -F '%R %t %m'
xxxyyyzzz12345 aaa/bbb/mytopic 0
```


# Client
時間があるときに調査する
1. Javascript client (pub/sub)
https://github.com/mqttjs/MQTT.js

1. Go Client (pub/sub)
1. Java Client (pub/sub)


# Ref.
https://mqtt.org/