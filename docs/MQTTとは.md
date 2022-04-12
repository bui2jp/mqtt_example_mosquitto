# MQTTとは

Message Queuing Telemetry Transport

軽量なデータ配信プロトコル  
アプリケーション層で使用される  
TCP/IPによるPub/Sub型データ配信

## 特徴
シンプル、軽量、省電力
- 軽量なプロトコル
- TopicベースのでPub/Sub
- 1:1, 1:N, N:Nのメッセージ配布
- QoS0,QoS1,QoS2
- Retain

## 登場人物
brocker, publisher, subscriber

## シーケンス
軽量化を実現できている理由

## version 3 と version 5

## Will, Retain, QOS, Keep Alive

## プロトコル比較
mqtt,http,websocket,amqp,grpc,...

## パフォーマンス

## ブローカー
(OSS)
- Eclipse Mosquitto
- RabbitMQ (*Pluginが必要)
- Apache_ActiveMQ

(商用)
- IBM MessageSight
- IBM WebSphere MQ Telemetry

## ライブラリ
- Eclipse Paho (C, java, JavaScript, golang)
- MQTT.js 

## 暗号化 (MQTT over TLS)

## MQTT over WebSocket


# (補足)　AMQP
Advanced Message Queuing Protocol  
Azure Service Busはこちらを採用している  
RabbitMQ  
MQTTに比べると重い

