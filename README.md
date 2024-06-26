##  flutter でnative 機能を使う

### 使い時

- カメラと画像処理
ネイティブのカメラ機能を利用して、写真を撮ったり、動画を撮影したり、リアルタイムで画像処理を行う場合がある。Flutterにはcameraプラグインもありますが、特定のカスタム機能が必要な場合は、ネイティブコードを使う。

- 位置情報サービス
GPSを利用してデバイスの現在地を取得したり、位置情報を追跡する機能を実装する場合など。これは、地図アプリや配車サービス、位置情報を利用するゲームなどでよく使われる。

- 通信機能
BluetoothやNFCなど、デバイスの通信機能を利用する場合。これには、ウェアラブルデバイスとのデータ通信や、NFCタグの読み取りなどが含まれる。

- 生体認証
指紋認証や顔認証などの生体認証機能を利用する場合。これらの機能は、セキュリティが求められるアプリケーション（例: モバイルバンキングアプリ）でよく使われる。

- ローカル通知
ネイティブの通知機能を利用して、ユーザーにローカル通知を送る場合がある。これは、特定の時間に通知を送信したり、アプリがバックグラウンドにあるときに通知を表示したりするのに使われる。



### Nativeでよく使われる機能

- Platform Channel : Flutter と Native間でのデータ通信

- Pigeon : プラットフォームチャネルを使ってFlutterとネイティブコード間でメッセージをやり取りするためのコードを自動生成

- Platform View : ネイティブのUIを表示

- Plugin : Flutterアプリからデバイスのハードウェア（カメラ、マイク、GPS、センサーなど）にアクセスしたい場合にプラグインを使用




### それぞれの Channel の違い
- Method Cannel : Flutter と Native 間で非同期でデータを取得処理


- Event Channel : Nativeから Flutter へ 一方向の通信

- BasicMessageChannel : 双方向


![alt text](assets/method.png)


### Pigeon 
スキーマを定義すると、通信するデータやmethodの型を各Platformごとに簡単に自動生成してくれる

```sh
$ flutter pub run pigeon コマンド
```

### PlatformView
ネイティブプラットフォームのViewをFlutter に埋め込むための機能。これにより、Flutterアプリ内でネイティブのUI コンポーネントを使用できる。





### 実装

1 . Flutter の main.dartにネイティブの実装を行うコードを記載

2 . Android側  android/app/src/main/kotlin/com/example/all_sdk/MainActivity.kt  にコードを追加

3 . iOS側  ios/Runner/AppDelegate.swift にコードを追加

### 上記 Method Cannel  の実装の確認
 
### iOS 
![alt text](assets/ios.png)


### Android 
![alt text](assets/android.png)

