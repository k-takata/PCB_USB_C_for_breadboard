# ブレッドボード用 USB Type-C 電源アダプター (Rev. 4)

## 概要

USB Type-Cからブレッドボードに電源を供給するためのアダプターです。
供給電圧は5Vと3.3Vをジャンパーピンで選択できます。


## 使用したソフトウェア

KiCad 9.0


## 回路図

[![schema](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/schema.png)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/schema.pdf)

## 基板パターン図 (Rev. 1)

![PCB pattern](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/pcb-pattern.png)

## 部品表

| Reference           |個数|値    | 説明 |
|---------------------|----|------|------|
|C1                   |   1| 10μF|積層セラミックコンデンサー 3225M|
|D1                   |   1|      |角形LED (あるいは3mm LEDや1608MチップLED)|
|F1 (\*1)             |   1|  1.1A|[ポリヒューズ](https://akizukidenshi.com/catalog/g/g100507/)|
|F2 (\*1)             |   1|  0.5A|[ポリヒューズ](https://akizukidenshi.com/catalog/g/g115300/)、表面実装|
|J1                   |   1|      |[USB Type-Cコネクター](https://akizukidenshi.com/catalog/g/g114356/)|
|J2, J3               |   2|      |細ピンヘッダー 1x2、ブレッドボードへの挿入用、裏面に取り付け|
|J4                   |   1|      |ピンヘッダー 1x3、出力電圧設定用|
|J5                   |   1|      |ピンソケット 1x5|
|R1, R2               |   2|5.1kΩ|1608M|
|R3                   |   1|  1kΩ|1/6Wまたは1/4W、LED電流制限用。値はLEDや好みの明るさに応じて適宜調整 (1kΩ~47kΩ)|
|SW1                  |   1|      |[スライドスイッチ](https://akizukidenshi.com/catalog/g/g115707/)|
|U1 (\*2)             |   1|[LM1117GS-3.3](https://akizukidenshi.com/catalog/g/g116989/)|三端子レギュレーター 3.3V 1A|

注:
* (\*1) F1, F2は使用する電流量や実装後のサイズを考慮してどちらかを選択します。基板上にはF1の表示のみあります。
* (\*2) Rev. 2までは[NJM2845DL1-33](https://akizukidenshi.com/catalog/g/g111299/)でした。


## 作成

以下の順で取り付けるのがお勧めです。

* USBコネクター
* 表面のチップ抵抗: R1, R2, (F2, D1)
* 裏面のチップ部品: U1, C1
* 表面右側の部品: J4, R3, D1
* 裏面のピンヘッダー: J2, J3
* 表面下側のピンソケット: J5
* 表面左側の部品: SW1, F1

J5とSW1は少し干渉するので、J5を少し削る必要があるかもしれません。


## 使用方法

基板裏面に取り付けたピンヘッダーJ2, J3をブレッドボードの電源ラインに挿入して使用します。J2, J3に供給する電圧はJ4にジャンパーピンを挿すことで5Vあるいは3.3Vから選択します。
J2, J3の端子は、USBコネクター側がプラス (シルクには`VDD`あるいは`+`の表示)、反対側がマイナス (シルクには`GND`あるいは`-`の表示)です。向きに注意してください。

SW1が電源スイッチです。電源がオンになっていれば、LEDが点灯します。

5Vと3.3Vの両方を使用したい場合や、D+/D-のデータ線を使用したい場合は、J5にコードを接続して使います。


## 変更差分

### Rev. 3とRev. 4の差分

* 基板の幅を約100mil狭くしました。それに合わせていくつかの部品の位置や向きを変更しています。
* ぐらつきが少なくなるよう、J2,J3のドリル径を0.8mmから0.7mmに変更しています。
* ぐらつきが少なくなるよう、J4のドリル径を0.9mmから0.8mmに変更しています。
* SW1を少し外側にずらしてJ5との干渉を減らしています。

### Rev. 2とRev. 3の差分

* U1を[NJM2845DL1-33](https://akizukidenshi.com/catalog/g/g111299/)から、より安価で薄くて小さい[LM1117GS-3.3](https://akizukidenshi.com/catalog/g/g116989/)に変更しています。これにより、ブレッドボードに挿したときにレギュレーターがブレッドボードに当たらなくなりました。
* D1に角形以外のLEDを取り付けた時に干渉しにくいように、R3の向きを逆に変更しています。
* 基板の厚さの設定を1.2mmに変更しています。


### Rev. 1とRev. 2の差分

* Rev. 1では基板の端ギリギリにシルクを配置していたために、シルクが削れてしまっていました。Rev. 2では基板サイズを少し大きくしてわずかに余裕を持たせてあります。
* Rev. 1ではJ5とSW1が干渉していましたが、Rev. 2ではSW1を少し外側にずらして干渉を減らしています。
* Rev. 2では表面実装のポリヒューズを使えるようにしています。
* Rev. 1では基板の厚さ1.6mmで発注していましたが、Rev. 2では1.2mmで発注しています。(KiCadの設定は1.6mmのまま)


## 完成品

Rev. 1

[![完成品](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-thumb.jpg)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor.jpg)

左から順にRev. 1, Rev. 2, Rev. 3

[![Rev. 1, 2, 3 の比較](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-rev1-2-3-thumb.jpg)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-rev1-2-3.jpg)

Rev. 1, Rev. 2, Rev. 3の裏面

[![Rev. 1, 2, 3 の比較、裏面](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-rev1-2-3-back-thumb.jpg)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-rev1-2-3-back.jpg)

左から順にRev. 1, Rev. 2, Rev. 3, Rev. 4

[![Rev. 1, 2, 3, 4 の比較](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-rev1-2-3-4-thumb.jpg)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-rev1-2-3-4.jpg)

ブレッドボードに挿して使用している例 ([ESP32-C3-WROOM-02 Breakout Board](https://github.com/k-takata/PCB_esp32c3_breakout)とともに)

[![使用例](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-on-breadboard-thumb.jpg)](https://raw.githubusercontent.com/k-takata/PCB_USB_C_for_breadboard/master/images/usb-c-adaptor-on-breadboard.jpg)

## License

CC0
