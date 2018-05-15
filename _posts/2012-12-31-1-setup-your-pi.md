---
title: '1. ラズパイとIntel Speech Enabling開発キットのセットアップ'


layout: nil
---

まずはラズパイの設定から開始します。Raspberry Pi 3ボードに搭載されているもの -

- 4 USBポート
- ビデオ出力用のHDMIポート (HDMIモニターに接続するために利用します。)
- 音声出力のための3.5mmオーディオジャック (本ラボでは利用しません。IntelのDSPに接続します。)
- Micro SDカードスロット
- イーサネットポート

{:.steps}
### ラズパイの組み立て

1. Micro SDカードをラズパイのMicro SDカードスロット差し込む (接触部分を上に向けるよう注意してください。)
2. キーボードとマウスをUSBポートに接続
3. HDMIポートを利用し、モニターに接続
4. イーサネットがある場合はケーブルを接続 - ない場合は、画面右上部にあるWifiのアイコンをクリックし、Wifiを有効にするとともに、SSIDを指定
![wifi](/assets/wifi.png)


{:.steps}
### Intel Speech Enabling開発キットの組み立て

Intelのキットは音声をキャプチャする**マイクロフォンアレイ**ボード、オーディオの処理アルゴリズムを実装している**Digital Signal Processor** (DSP) ボード、DSPボードとRaspberry Piを接続ための**Interconnect FPC**が含まれています。組み立てる前にそれぞれが揃っていることを確認してください。
![contents](/assets/Contents.png)

まず、マイクアレイボードとDSPボードの接続から行います。マイクアレイボードとDSPボードそれぞれに対となる2つのコネクターと端子があります。それらを慎重に差し込んでください。2つの円形ボードがずれることなく接続されていることを確認してください。
![Connect Mic PCB to DSP PCB](/assets/FlipConnect.png)

![Connect Detail](/assets/AlignPress.png)

次にFPCをDSPボードに接続してください。DSPボードを裏返し、FPCの2つのコネクターのうち**小さい方**をボードに接続してください。FPCとDSPボードのピンがずれていないことを確認してからコネクターをしっかりと差し込んでください。

![FPC to DSP](/assets/ConnectorPress.png)

それではFCPのもう一方(大きいコネクター側)を**Raspberry Pi**に接続します。DSPボードをひっくり返すことで、FPCのコネクターが下側になるため組み立て安くなります。Raspberry Piのピン配列に合わせ、慎重にコネクターを接続してください。
![Pi to FPC](/assets/PiConnect.png)

下記のように**DSPボード**の3.5mmオーディオコネクターにスピーカーもしくはイヤフォンを差し込んでください。Raspberry Piのオーディオジャックは**使用しない**よう注意してください。次に電源をDSPボードの**USBマイクロ**コネクターに接続します。DSPボードの下部に**青いLED**がつくことで電源が入ったことが確認できます。スピカーの電源が入っていることも確認してください - 万が一つかない場合はバッテリーの充電を行ってください。 USBマイクロケーブルをスピーカーのコネクターに差し込むことで、バッテリーの充電が行なえます。
![Audio and Power](/assets/AudioPowerInstallDSP.png)

下記の写真を確認し、キットのすべての接続が正しく行われていることを確認してください。ラズパイの電源を入れた際に、Intelキットの**マイクアレイ**ボードの円形**白LED**が点灯します。この写真ではイーサネット接続がされていません。

![SetupFinished](/assets/SetupFinished.png)


{:.steps}
### ラズパイの起動

1. ラズパイのマイクロUSBコネクターに電源を差します。
2. キーボードレイアウトが正しいことを確認してください。(日本語キーボードの場合は、Japaneseを選択) 画面左上部のRaspberryアイコンからKeyboard and Mouse設定を選択して変更してください。
![Keyboard setup](/assets/KBAM.png)
3. OS言語が正しいことを確認してください。(日本語のAlexaを利用する場合は、Japaneseを選択) 画面左上部のRaspberryアイコンから、Raspberry Pi Configurationを選択しLocaleをja(Japan)に設定してください。
![Locale setup](/JP/assets/locale.png)
4. OSの再起動が促されるため、再起動を行い画面が日本語に変更されていることを確認してください。
5. ツールバー上の地球のアイコンをクリックし、ブラウザーを起動してください。

{:.verify}
### チェックポイント 1
1. インターネットに接続されていることを確認し、[https://developer.amazon.com](https://developer.amazon.com)にアクセスできる。
2. Intelキット下部の**青いLED**とマイクロフォンアレイの**白いLED**が点灯している。
