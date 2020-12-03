# MQTT example (eclipse-mosquitto)

## Mosquitto on Docker

起動

```
% docker run -it --rm -p 1883:1883 -p 9001:9001 \
    -v $(pwd)/config/mosquitto.conf:/mosquitto/config/mosquitto.conf \
    -v $(pwd)/data:/mosquitto/data \
    -v $(pwd)/log:/mosquitto/log \
    -d eclipse-mosquitto
```

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

# Client
時間があるときに調査する
1. Javascript client (pub/sub)
1. Go Client (pub/sub)
1. Java Client (pub/sub)
