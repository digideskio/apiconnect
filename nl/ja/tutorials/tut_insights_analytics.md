---
copyright:
  years: 2017
lastupdated: "2017-12-15"
---

{:new_window: target="blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 基本的な分析を行って洞察を深める
所要時間: 30 分  
スキル・レベル: ビギナー

## 目標
ここでは、{{site.data.keyword.apiconnect_full}}での API 分析の基本的な概要を取り上げます。 独自の API を使用しながら、用意されている分析ダッシュボードの機能を確認してください。


## 前提条件
独自の API による分析結果を表示するには、API 製品を作成して公開しておく必要があります。 さらに、その API を何度か呼び出して分析用のデータを生成することも必要です。可能なら、あらかじめ用意されているテスト・アプリケーションではなく、登録済みのアプリケーションのクライアント ID を使用してください。

このチュートリアルで使用するデータを生成するために、Postman の *Collection Runner* を使用して、別々のデータとクライアント ID によって API を数回呼び出しました。 似たようなツール (Firefox 用の HttpRequester など) を使用することもできれば、cURL を使用してコマンド・ラインから API を複数回呼び出すことも可能です。 {{site.data.keyword.apiconnect_short}} で**「探索」**リンクをクリックして、API のサンプル要求を取得することもできます。

## カタログ分析の概要
API の所有者には、提供する API の正常な動作やパフォーマンスを評価するための方法が必要です。 そのような分析を行えるのは、主にカタログ・レベルです。 カタログの概要をまだつかんでいない場合は、IBM Knowledge Center の[カタログの処理![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン")](https://www.ibm.com/support/knowledgecenter/en/SSFS6T/com.ibm.apic.apionprem.doc/conref_working_with_env.html){:new_window} を参照してください。 

このチュートリアルを実行する人もアプリケーション開発者も、開発者ポータルでアプリケーション固有の分析結果にアクセスできますが、ここではカタログ分析に焦点を合わせます。

そのカタログに公開した API と製品に関するリアルタイム情報と履歴情報に最大 90 日間アクセスできます。 呼び出し元のユーザーも確認できます。 カタログに複数のスペースがある場合は、スペース・レベルに移動することも可能です。

このチュートリアルには 4 つのアクティビティーがあり、それぞれ以下の作業の実行方法を示します。
* 分析の表示
* イベント・レコードの詳細の表示
* 新しいダッシュボードの作成
* 新しい視覚化機能の作成


## アクティビティー 1: すぐに使用可能な分析機能による結果の表示
1. {{site.data.keyword.Bluemix_short}} の {{site.data.keyword.apiconnect_short}} サービスでダッシュボードを起動し、開きたいカタログを選択します。 
2. *「分析」*タブをクリックします。

   ![](./images/analyticstab.png) 
  
デフォルトの概要ダッシュボードの 2 つのビジュアル棒グラフに、以下の内容に関する最近の 7 日間のデータが表示されます。
* アクティブな製品 - 上位 5 件 
* アクティブな API - 上位 5 件 

3. どちらかの棒グラフにマウスを移動すると、さらに詳細なデータ (API カウントや API 名など) が表示されます。

   ![](./images/defaultoverview.png) 

4. 検索バーを使用して、表示するデータをフィルターで絞り込みます。 別の時間フィルターや自動リフレッシュ・レートを選択することもできます。 選択内容に応じて、視覚化機能の内容が更新されます。

すぐに使用可能な状態で用意されているダッシュボードは、他にもあります。

5. フォルダー・アイコンをクリックして、保存されているダッシュボードをロードし、ドロップダウン・リストから **api_default** を選択します。

   ![](./images/api_default.png) 

このダッシュボードには、API の状況、エラー、応答時間、呼び出し総数、1 日あたりの呼び出し数を表示する視覚化機能の別のセットが用意されています。

   ![](./images/sandbox-api_default.png) 


## アクティビティー 2: イベントの詳細の表示

視覚化機能を使用すれば、データの概要を分かりやすく表示できますが、グラフに取り込まれたデータの元になっているイベント・レコードに移動するための手段も必要です。

1. 視覚化機能の左下隅にある矢印アイコンにマウスを移動します。 小さな矢印が表示されます。
2. 矢印をクリックすると、その視覚化機能で使用されているデータのテーブルが表示されます。 
3. **「イベントの表示」**ラベルをクリックすると、各イベントの最大 100 個のレコードの詳細情報に移動できます。

   ![](./images/statuscodetable.png) 

ダッシュボードの視覚化機能を編集、移動、削除できます。

## アクティビティー 3: 新しいダッシュボードの作成

API のトラフィック・パターンを表示する新しいダッシュボードを作成します。 どのパターンにも、組み込みの視覚化機能を使用して対応できます。 

1. 新規ダッシュボード・アイコンをクリックし、**「既存の視覚化から選択 (Choose from existing visualizations)」**リンクをクリックします。 

   ![](./images/newdashboard.png) 
    使用可能な視覚化機能のリストが表示されます。

2. いくつかの視覚化機能を選択してダッシュボードに追加します。  以下に例を示します。
  * サブスクライブ済みのアプリケーション
  * 1 プランあたりのアプリケーション数 
  * 成功率
  * 1 日あたりの API 呼び出し数
  
  **ヒント** それぞれの視覚化機能を選択すると、選択タブによってダッシュボードの表示がブロックされるので、視覚化機能がダッシュボードに追加されたことに気付かない可能性があります。 視覚化機能を 1 つ選択するたびに選択タブを閉じれば、ダッシュボードの変化を確認できます。

3. **「保存」**をクリックして、ダッシュボード名を `Subscriber Dashboard` にします。

   ![](./images/savedashboard.png)

   ![](./images/namedashboard.png) 


## アクティビティー 4: 新しい視覚化機能の作成
作成した Subscriber Dashboard に、1 日あたりの API 呼び出し数を表示する組み込みの視覚化機能を組み込みました。 そのような集計情報を見ると、アプリケーションごとの使用状況も確認したくなります。 それで、その情報を表示する新しい視覚化機能を作成します。

1. **「新規視覚化」**をクリックし、**「視覚化の作成」**リンクを選択します。
![](./images/newvisualization.png) 

2. 視覚化機能のタイプとして**「折れ線グラフ」**を選択します。 初期化した状態の折れ線グラフでは、Y 軸に API 呼び出し数がセットアップされます。 このセットアップは、ここで使用するグラフに適しています。

3. 以下を選択します。
	* バケット・タイプ: **X 軸**
	* 集計: **日付ヒストグラム**
	* カスタム・ラベル: **時間** 
4. **「実行」**をクリックしてグラフを表示します。 **ヒント**: 必要に応じて、データを表示する時間フレームを調整してください。

   ![](./images/apichart1.png)

この現状のグラフでは、API 呼び出し数が時系列で表示されます。 そこで、API 呼び出し数をアプリケーション名ごとに表示します。

5. **「サブバケットの追加 (Add sub-buckets)」**ボタンをクリックします。
6. 以下を選択します。
	* バケット・タイプ: **分割行**
	* サブ集計: **条件**
	* フィールド: **app_name**
	* カスタム・ラベル: **アプリケーション**
	
   ![](./images/subbucket.png)
8. **「実行」**をクリックしてグラフを表示します。
9. **「保存」**をクリックして、グラフ名を `API Calls by App` にします。
10. コンテキストで視覚化機能を確認するために、その視覚化機能を Subscriber Dashboard に追加します。

   ![](./images/apichartfinal.png)
 
API 呼び出しや呼び出し元などに関する詳細情報を視覚化するのに役立つ情報は、他にもあります。 全 API イベントのリストは、API Connect の Knowledge Center にありますし、視覚化機能の作成時に条件のリストで確認することもできます。

## まとめ

API 分析の結果をさまざまなスタイルの組み合わせによって視覚化すると、何かの結論を引き出したり API データをさらに深く掘り下げたりすることができます。 その洞察結果を活用すれば、どの API を提供するか、API の置換や廃棄をいつ行うか、API をだれが利用しているか、といったことを判別しやすくなります。

例えば、「ACME」という名前のプロバイダーから入手した API のバージョン 1 (v1) とバージョン 2 (v2) をこの数年間実行してきたとします。 そのプロバイダーは、v2 のリリース時に v1 を非推奨にしました。 さらに、既存の v1 の利用者に対して、v2 に移行するためのタイムラインを設定しました。 その期日が近づいてきたころ、ACME は、大切なパートナーにサポートを提供するために、利用者が v1 からすぐに移行できるかどうかを確認することにしました。 

ACME は、ここで作成したような視覚化機能を駆使して、その情報を一目で分かるようにまとめることにしました。

このチュートリアルでは、API と利用者のデータを分かりやすく表示する機能を作成して組み合わせるために、いくつかのアクティビティーを実行しました。 視覚化機能とダッシュボードを使用して、API を適切に組み合わせて提供しているかどうかを確認するのに役立つデータをまとめるツールを短時間で作成しました。

---

## 次のステップ

[API およびバージョン管理の方法](tut_manage_version_landing.html)を学習します。

作成 > 管理 > 保護 > ソーシャル化 > **分析**  
