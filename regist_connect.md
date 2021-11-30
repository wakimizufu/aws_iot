# AWS IoT モノ登録とMQTTメッセージ受信確認

## 概要

・AWS IoTよりRaberyPiをモノとして登録した上でサンプルプログラムを実行してMTQQメッセージ受信を確認する


## AWS IoT・モノ登録手順

・AWS IoTにてRaberyPiをモノとして登録する手順について以下にスナップショットを掲載する

![デバイス登録_1](https://user-images.githubusercontent.com/89113273/144030916-41217438-2694-456b-9f3d-a8c29ea8a084.png)

![デバイス登録_2](https://user-images.githubusercontent.com/89113273/144030930-e663d3e5-d24e-4530-90cf-66dd9316bdcb.png)

![デバイス登録_3](https://user-images.githubusercontent.com/89113273/144030936-13235a0e-20e5-45de-bb8d-05f5f95aaaf9.png)

![デバイス登録_4](https://user-images.githubusercontent.com/89113273/144030957-3582ba6d-d961-4228-b606-ff599a5414d6.png)

![デバイス登録_5](https://user-images.githubusercontent.com/89113273/144030967-8e2ced99-9f96-4958-8d7a-691d83b13f0a.png)

![デバイス登録_7](https://user-images.githubusercontent.com/89113273/144030996-041273e4-8f5c-44bd-9291-f50a621a6cf2.png)

![デバイス登録_8](https://user-images.githubusercontent.com/89113273/144031126-e40cd0d6-a6c0-4815-8930-32818e04c5c5.png)

![デバイス登録_9](https://user-images.githubusercontent.com/89113273/144031148-45fe1375-f5f1-4879-9d41-9dec426f4423.png)

## RasberyPi・AWS IoT Develop SDK実行前各種インストール対応

・モノ登録時にダウンロードしたサンプルプログラムをRasberyPiで実行する前に、node.js,npm,nをインストールする必要がある

・下記のコマンドラインの内容を順次実行して環境構築した

```
sudo apt-get update
sudp apt-get install -y nodejs npm
sudo npm cache clean
sudo npm install -g n
sudo n stable
```

## サンプルプログラムによるMQTTメッセージ受信

・登録時にダウンロードしたZIPファイルを解凍すると証明書ファイルとstart.shファイルが含まれる
![デバイス登録_6](https://user-images.githubusercontent.com/89113273/144030985-8e304e91-72b5-40af-a81e-55a159b9921f.png)

・登録時に表示されたコマンドラインより解凍したファイルをRasberryPiへ転送した上でstart.shファイルへの実行パーミッションの設定を行う

・start.shを実行すると以下の様な表示がされるRasbetyPiからMQTTメッセージが定期的に送信される

![aws_start sh_Raspi実行中_20211130](https://user-images.githubusercontent.com/89113273/144034219-179cdb56-4638-492b-88bb-b4bb1a2938c4.png)

・RasbetyPiから送信されたメッセージはAWS IoTに送信され、MQTTテストクライアントにて受信された内容を以下のスナップショットの様に表示される

![aws_start sh_Raspi実行中_20211123](https://user-images.githubusercontent.com/89113273/144034527-582fe3a3-fd98-4130-89a1-13de089f419d.png)

