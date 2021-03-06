---

copyright:
 years: 2015 2016

---


# Web アプリケーションによる {{site.data.keyword.mobilepushshort}} の受信の使用可能化
{: #web_notifications}
最終更新日: 2016 年 10 月 17 日
{: .last-updated}

Google Chrome および Mozilla Firefox の Web アプリケーションによる {{site.data.keyword.mobilepushshort}} の受信を可能にできるようになりました。

## {{site.data.keyword.mobilepushshort}}用の Web ブラウザー・クライアント SDK のインストール
{: #web_install}

このトピックでは、Web アプリケーションの開発を促進するためにクライアント JavaScript Push SDK をインストールして使用する方法について説明します。

### Google Chrome Web アプリケーションの初期化

Chrome Web アプリケーションの場合、Javascript SDK をインストールするには、以下の手順を実行します。

[Bluemix Web push SDK](https://codeload.github.com/ibm-bluemix-mobile-services/bms-clientsdk-javascript-webpush/zip/master) から `BMSPushSDK.js`、`BMSPushServiceWorker.js`、および `manifest_Website.json` をダウンロードします。

1. `manifest_Website.json` ファイルを編集します。

Google Chrome ブラウザーの場合、`name` を、ご使用のサイトの名前に変更します。`gcm_sender_id` を、Firebase Cloud Messaging (FCM) または Google Cloud Messaging (GCM) の送信側_ID に変更します。詳しくは、[Google の資料](https://developers.google.com/web/fundamentals/getting-started/codelabs/push-notifications/#make_a_project_on_the_google_developer_console)を参照してください。gcm_sender_id 値には数値のみが含まれます。

```
 {
  "name": "YOUR_WEBSITE_NAME",
      "gcm_sender_id": "GCM_Sender_Id"
    }
```
    {: codeblock}
 
Mozilla Firefox ブラウザーの場合、以下の値を `manifest.json` ファイルに追加します。`name` を、ご使用のサイトの名前に変更します。

```
{
  "name": "YOUR_WEBSITE_NAME"
    }
```
    {: codeblock}

2. `manifest_Website.json` ファイル名を `manifest.json` に変更します。
3. `BMSPushSDK.js`、`BMSPushServiceWorker.js`、および `manifest.json` をルート・ディレクトリーに追加します。
3. `manifest.json` を html ファイルの `<head>` タグに組み込みます。
```
 <link rel="manifest" href="manifest.json">
```
    {: codeblock}
4. Bluemix Web Push SDK を GitHub から Web アプリケーションに組み込みます。
```
 <script src="BMSPushSDK.js" async></script>
```
    {: codeblock}

## Web Push SDK の初期化 
{: #web_initialize}

Bluemix {{site.data.keyword.mobilepushshort}}サービスの `app GUID` と `app Region` を使用して Push SDK を初期化します。  

app GUID を入手するには、初期化されたプッシュ・サービスのナビゲーション・ペインで**「構成」**オプションを選択し、**「モバイル・オプション」**をクリックします。Bluemix のプッシュ通知サービス appGUID パラメーターを使用するようにコード・スニペットを変更します。

`App Region` は、{{site.data.keyword.mobilepushshort}}サービスがホストされる場所を指定します。次の 3 つの値のいずれかを使用できます。

 - 米国のダラス:	 `.ng.bluemix.net`
 - 英国:      			 `.eu-gb.bluemix.net`
 - シドニー:   		 `.au-syd.bluemix.net`

```
    var bmsPush = new BMSPush();
    function callback(response) {
        alert(response.response)
    }
    var initParams = {
      "appGUID":"push app GUID",
  "appRegion":"Region where service hosted",
   "clientSecret":"clientSecret of your push service"
    }
  bmsPush.initialize(params, callback)
```
	{: codeblock}

## Web アプリケーションの登録
{: #web_register}

`register()` API を使用して、デバイスを{{site.data.keyword.mobilepushshort}}サービスに登録します。Google Chrome から登録する場合、Firebase Cloud Messaging (FCM) または Google Cloud Messaging (GCM) の API キーと Web サイト URL を、Bluemix {{site.data.keyword.mobilepushshort}} サービス Web 構成ダッシュボードに追加します。詳しくは、[Google Cloud Messaging の資格情報の構成](t_push_provider_android.html)で Chrome 用のセットアップを参照してください。

Mozilla Firefox から登録する場合は、Web サイト URL を Bluemix {{site.data.keyword.mobilepushshort}}サービスの Web 構成ダッシュボードで Firefox 用セットアップの下に追加してください。

以下のコード・スニペットを使用して、 Bluemix {{site.data.keyword.mobilepushshort}}サービスに登録します。
```
    var bmsPush = new BMSPush();
    function callback(response) {
        alert(response.response)
    }
    var initParams = {
      "appGUID":"push app GUID",
  "appRegion":"Region where service hosted",
  "clientSecret":"clientSecret of your push service"
  }
  bmsPush.initialize(params, callback)
    bmsPush.register(function(response) {
      alert(response.response)
  })
```
    {: codeblock}

## 基本{{site.data.keyword.mobilepushshort}}の送信
  {: #send}

アプリケーションの開発が完了したら、プッシュ通知を送信できます。 

1. **「通知の送信 (Send Notifications)」**を選択し、**「送信先 (Send To)」**オプションとして**「Web 通知 (Web Notifications)」**を選択することでメッセージを構成します。 
2. **「メッセージ」**フィールドに、配信する必要があるメッセージを入力します。
3. 以下のオプションの設定を指定することを選択できます。
  - **通知タイトル (Notification Title)**: メッセージ・アラートの見出しとして表示されるテキストです。
  - **通知アイコン URL (Notification Icon URL)**: メッセージにアプリ通知アイコンを付けて配信する必要がある場合、このフィールドにアイコンへのリンクを指定します。
  - **追加のペイロード (Additional payload)**: 通知用のカスタム・ペイロードの値を指定します。

以下のイメージは、ダッシュボードの Web 通知オプションを示しています。

  ![「通知」画面](images/DashboardWebpush.jpg)
  
## 次のステップ
  {: #next_steps_tags}

基本通知を正常にセットアップしたら、タグ・ベースの通知および詳細オプションの構成を行うことができます。

{{site.data.keyword.mobilepushshort}}サービスの以下の機能をご使用のアプリに追加します。
  タグ・ベースの通知を使用する場合は、[タグ・ベースの通知](c_tag_basednotifications.html)を参照してください。
  拡張通知オプションを使用する場合は、[拡張通知](t_advance_badge_sound_payload.html)を参照してください。



