---
title: '6. ユニットテストの実行'


layout: nil
---
スクリプト(sdk-folder)で、すでにディレクトリ内にビルドが生成されている前提



#### ユニットテスト

プロトタイプのユニットテスト郡を実行するため、ターミナルウィンドウで下記のステップを実行します。

`cd /home/pi/sdk-folder/sdk-build
sudo make all test
`

本ワークショップでは、時間短縮のためテストはプリビルドされています。イヤフォンもしくはスピーカーがある場合、Alexaが一連のオーディオテストと機能テストを実施する内容を聞くことができます。

テスト自体は４分程度かかり、すべてのテスト項目がすべて100% Successで完了します。デベロッパーは、クライアントデバイスソフトウェアを修正した際、いつでも**ユニットテスト**を実行し、意図しない不具合が起きていないことを確認できます。これでクライアントを起動する準備が整いました。

