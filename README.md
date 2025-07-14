# ブレッドボード用 USB Type-C 電源アダプター (Rev. 3)

## 概要

USB Type-Cからブレッドボードに電源を供給するためのアダプターです。
供給電圧は5Vと3.3Vをジャンパーピンで選択できます。


## 使用したソフトウェア

KiCad 9.0


## 回路図

[![schema](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/schema.png)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/schema.pdf)

## 基板パターン図

![PCB pattern](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/pcb-pattern.png)

## 部品表

| Reference           |個数|値    | 説明 |
|---------------------|----|------|------|
|C1                   |   1| 10μF|積層セラミックコンデンサー 3225M|
|D1                   |   1|      |角形LED|
|F1 (\*1)             |   1|  1.1A|[ポリヒューズ](https://akizukidenshi.com/catalog/g/g100507/)|
|F2 (\*1)             |   1|  0.5A|[ポリヒューズ](https://akizukidenshi.com/catalog/g/g115300/)、表面実装|
|J1                   |   1|      |[USB Type-Cコネクター](https://akizukidenshi.com/catalog/g/g114356/)|
|J2, J3               |   2|      |細ピンヘッダー 1x2、ブレッドボードへの挿入用、裏面に取り付け|
|J4                   |   1|      |ピンヘッダー 1x3、出力電圧設定用|
|J5                   |   1|      |細ピンソケット 1x5|
|R1, R2               |   2|5.1kΩ|1608M|
|R3                   |   1|  1kΩ|LED電流制限用、値はLEDに合わせて適宜調整|
|SW1                  |   1|      |[スライドスイッチ](https://akizukidenshi.com/catalog/g/g115707/)|
|U1                   |   1|[LM1117GS-3.3](https://akizukidenshi.com/catalog/g/g116989/)|三端子レギュレーター 3.3V 1A|

注:
* (\*1) F1, F2は使用する電流量や実装後のサイズを考慮してどちらかを選択します。基板上にはF1の表示のみあります。


## 作成

以下の順で取り付けるのがお勧めです。

* USBコネクター
* 表面のチップ抵抗: R1, R2, (F2)
* 裏面のチップ部品: U1, C1
* 表面右側の部品: J4, R3, D1
* 裏面のピンヘッダー: J2, J3
* 表面下側のピンソケット: J5
* 表面左側の部品: SW1, F1

J5とSW1は少し干渉するので、J5を少し削る必要があるかもしれません。


## 使用方法

J2, J3をブレッドボードの電源ラインに挿入して使用します。J2, J3に供給する電圧はJ4にジャンパーピンを挿すことで選択します。
J2, J3の端子は、USBコネクター側がプラス (シルクにはVDDの表示)、反対側がマイナス (シルクにはGNDの表示)です。向きに注意してください。

SW1が電源スイッチです。電源がオンになっていれば、LEDが点灯します。

5Vと3.3Vの両方を使用したい場合や、D+/D-のデータ線を使用したい場合は、J5にコードを接続して使います。


## 変更差分

### Rev. 2とRev. 3の差分

* U1を[NJM2845DL1-33](https://akizukidenshi.com/catalog/g/g111299/)から、より安価な[LM1117GS-3.3](https://akizukidenshi.com/catalog/g/g116989/)に変更しています。


### Rev. 1とRev. 2の差分

* Rev. 1では基板の端ギリギリにシルクを配置していたために、シルクが削れてしまっていました。Rev. 2では基板サイズを少し大きくしてわずかに余裕を持たせてあります。
* Rev. 1ではJ5とSW1が干渉していましたが、Rev. 2ではSW1を少し外側にずらして干渉を減らしています。
* Rev. 2では表面実装のポリヒューズを使えるようにしています。


## 完成品

Rev. 1

[![完成品](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-thumb.jpg)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor.jpg)

## License

CC0
