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

## ブローカー
OSS
- Eclipse Mosquitto
- RabbitMQ
- Apache_ActiveMQ
商用
- IBM MessageSight
- IBM WebSphere MQ Telemetry

## ライブラリ
- Eclipse Paho (C, java, JavaScript, golang)
- MQTT.js 


