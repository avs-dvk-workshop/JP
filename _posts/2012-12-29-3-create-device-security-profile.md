---
title: '3. 製品とセキュリティプロファイルの作成'


layout: nil
---

{:.steps}
### デバイスの登録とセキュリティプロファイルの作成

Amazon Developerアカウントの登録後、Alexaデバイスとセキュリティプロファイルの作成を行います。これにより、デバイスがクラウド上にあるAlexa Voice Serviceに接続することができるようになります。

1. [developer.amazon.com](https://developer.amazon.com/login.html)よりAmazon Developer Portalにログイン。右上の”Developer Console”をクリック。
2. Alexaタブをクリックし、Alexa Voice Service下部にあるGetting Startedボタンをクリック。
   ![](assets/avs-navigation-new.png)
3. 初めてAVSを利用する場合、ウェルカム画面が表示されます。**GET STARTED**ボタンをクリックします。すでにAVSを利用されたことがある場合、**Create Product**ボタンをクリ行くします。

{:.tab}
#### 製品情報

1. **製品名**: Developer Portal上での表示名および、ユーザが製品をAmazonに登録した祭に、ユーザにも表示される製品名。
2. **製品ID**: シンプルな製品識別名。**空白不可**。
3. *製品はアプリや出刃オスを使用しますか？*にて**端末**を選択。
4. *ご使用の端末は、コンパニオンアプリを使用しますか?*で**いいえ**を選択 。
5. 製品カテゴリーを選択。どのカテゴリーでも可。製品概要を記載。
6. *エンドユーザは、商品とどのようにやり取りするのでしょうか？*にて**ファーフィールド**を選択。
7. **(オプション入力)**画像: 下記リンクを右クリックしてテスト画像をコンピュータに保存(自身の画像でも可)し、アップロード。[https://developer.amazon.com/public/binaries/content/gallery/developerportalpublic/solutions/alexa/alexa-voice-service/images/reference-implementation-image.png](https://developer.amazon.com/public/binaries/content/gallery/developerportalpublic/solutions/alexa/alexa-voice-service/images/reference-implementation-image.png)
8. *この製品を商品として配信する予定ですか？*にて**いいえ**を選択。
9. *これは子供向け商品、それ以外は13歳以上の子供向けですか？*にて**いいえ**を選択。
10. **次へ**をクリック。

{:.tab}
#### セキュリティプロファイル

1. **プロフィールを新規作成する**リンクをクリック。
	 ![](assets/avs-create-new-security-profile.png)

2. 下記を入力   
	 - **セキュリティプロファイル名**: Alexa Voice Service Sample App Security Profile
	 - **セキュリティプロファイル記述**: Alexa Voice Service Sample App Security Profile Description
	 - **次へ**をクリック。

   **Note:** 上記は入力例のため、**セキュリティプロファイル名**や**セキュリティプロファイル記述**に他の値を設定することも可能。

	 クライアントのIDとクライアントのシークレットが自動的に生成されます。
3. **セキュリティプロファイルID**したのウェブ - Android/Kindle - iOS - 他のデバイスやプラットフォームから**ウェブ**を選択。

   - **許可された出荷地**にて`http://localhost:3000`をテキストフィールドに入力し、**追加**ボタンをクリック。これによりクライアントがAVSより固有の*Refresh Token*をリクエストすることができ、デバイスがAlexaと接続することが可能となります。
   - **許可された返品URL**にて`http://localhost:3000/authresponse`をテキストフィールドに入力し、**追加**ボタンをクリック。これによりAVSがRefresh Tokenをデバイスに受け渡すことができます。
   - *以下に同意します: AVS同意およびAVSプログラムの要件*にチェック。
	 - **完了する**をクリック。

![ProfileInfo2](/assets/Profile.png)   

{:.verify}
### チェックポイント3
1. デバイスが、AVSダッシュボードに表示されていることを確認。 [https://developer.amazon.com/avs/home.html#/avs/home](https://developer.amazon.com/avs/home.html#/avs/homes)
2. AVSダッシュボードのデバイス横の**管理する**リンクをクリック。
3. *詳細と管理*セクションの左ナビゲーションの**セキュリティプロファイル**をクリック。
4. **許可された出荷地**に`http://localhost:3000`が設定されていることを確認。
5. **許可された返品URL**に`http://localhost:3000/authresponse`が設定されていることを確認。
