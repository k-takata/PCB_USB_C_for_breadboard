# ブレッドボード用 USB Type-C 電源アダプター

## 概要

USB Type-Cからブレッドボードに電源を供給するためのアダプターです。
供給電圧は5Vと3.3Vをジャンパーで選択できます。


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
|F1                   |   1|  1.1A|[ポリヒューズ](https://akizukidenshi.com/catalog/g/g100507/)|
|J1                   |   1|      |[USB Type-Cコネクター](https://akizukidenshi.com/catalog/g/g114356/)|
|J2, J3               |   2|      |細ピンヘッダー 1x2|
|J4                   |   1|      |ピンヘッダー 1x3、出力電圧設定用|
|J5                   |   1|      |細ピンソケット 1x5|
|R1, R2               |   2|5.1kΩ|1608M|
|R3                   |   1|  1kΩ|LED電流制限用|
|SW1                  |   1|      |[スライドスイッチ](https://akizukidenshi.com/catalog/g/g115707/)|
|U1                   |   1|[NJM2845DL1-33](https://akizukidenshi.com/catalog/g/g111299/)|三端子レギュレーター 3.3V 800mA|


## 使用方法

J2, J3をブレッドボードの電源ラインに挿入して使用します。J2, J3に供給する電圧はJ4にジャンパーピンを挿すことで選択します。
J2, J3の端子は、USBコネクター側がプラス、反対側がマイナスです。向きに注意してください。

SW1が電源スイッチです。電源がオンになっていれば、LEDが点灯します。

5Vと3.3Vの両方を使用したい場合や、D+/D-のデータ線を使用したい場合は、J5にコードを接続して使います。


## 完成品

T.B.D.
<!--
[![完成品](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-thumb.jpg)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor.jpg)
-->

## License

CC0
