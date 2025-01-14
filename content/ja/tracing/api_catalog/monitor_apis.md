---
further_reading:
- link: dynamic_instrumentation/
  tag: ドキュメント
  text: API カタログのセットアップ
- link: /monitors/
  tag: ドキュメント
  text: モニターによるアラート
- link: /synthetics/api_tests/
  tag: ドキュメント
  text: Synthetic API テスト
- link: /security/application_security/
  tag: ドキュメント
  text: アプリケーション セキュリティ モニタリング
is_beta: true
kind: ドキュメント
title: API のモニタリング
---

## 概要

API カタログにすべてのエンドポイントをセットアップし、チームの所有権を割り当てたら、管理と改善を開始できます。API カタログを使用して、次のようなアクティビティを開始します。

 - パフォーマンスが不十分な API の検出と調査。
 - レイテンシーやエラーレートなどのキーパフォーマンスメトリクスに基づくアラートの作成。
 - トリガーされたアラート、テスト結果、セキュリティシグナルの観点から API の信頼性を追跡。
 - Synthetic Monitoring による API テストの標準化とテストカバレッジの向上。


## パフォーマンスが不十分な API の検出と最適化の機会の特定

エンドポイントを確認する際、API エンドポイントの詳細を高解像度で見ることが役立ちます。

[API カタログエクスプローラー][2]のフィルター、ソート、検索オプションを使用して、関心のあるエンドポイントを見つけます。
エンドポイントをクリックすると、その詳細ページが表示されます。ここでは、パフォーマンス、エラー、問題、デプロイメント、モニター、所有権、依存関係マップ、およびメタデータ情報を一元的に確認できます。詳細ページから、エンドポイントにカスタムタグを追加することもできます。また、Datadog の他のエリアへのリンクを使用して、様々なタイプのテレメトリーを調査することもできます。

詳細ページでは、以下のことができます。
- 高いエラー率と多くのリクエスト数が示された場合、パス (例: `/checkout`) によって特定のエンドポイントを調査する。
- **Requests & Errors** グラフおよび相関する **Response Code** グラフを表示し、問題を特定する。
- トレース、ログ、エラーなど、関連するテレメトリーに移動する。

{{< img src="tracing/api_catalog/api-catalog-endpoint-details-pivot-to-traces.mp4" alt="エンドポイントをクリックするとエラーグラフと依存関係グラフが表示されます。関連するトレースをクリックすると、調査することができます。" video="true" >}}

詳細ページ上のグラフは、初期状態ではエクスプローラーページと同じ設定のスコープになっています。詳細ページで時間枠セレクタやその他のスコープのドロップダウンメニューを使用して、調査に合わせてそれらの設定を変更することができます。

## 期待されるパフォーマンスから外れたエンドポイントに対するアラート

エンドポイントが予期せぬ動作をした場合 (時折パフォーマンスが低下するような場合)、外れ値のデータを報告する場合 (パフォーマンスが極端に低下したり、稀なエラーが発生するような場合)、または望ましいしきい値を超えたメトリクスを達成した場合 (エラーレートが高い場合) にアラートを出すようにモニターをセットアップできます。

最新のモニターステータスはエクスプローラーに表示され、モニターがアラートを発している理由や対処方法に関する詳細情報を確認できます。また、クリックしてモニターを表示することで、調査を開始すべきかどうかを判断できます。

{{< img src="tracing/api_catalog/api-catalog-monitor.png" alt="API カタログエクスプローラーのモニターステータスメニューとモニター作成ボタン" style="width:40%;" >}}

API カタログから直接、**MONITORS** 列の **+ Monitor** をクリックして、**Latency** または **Error rate** に関するモニターを作成することもできます。モニターアラートのセットアップと管理に関する追加情報については、[アラート][1]をお読みください。

## API テストカバレッジの追跡と改善

Synthetic API テストを使用すると、エンドポイントの自動化された定期テストをセットアップできます。これによりテストが失敗した場合はアラートで通知されるため、問題を診断して修正できます。

エクスプローラーページの **API TESTS** 列には、どのエンドポイントにテストがあり、どれかが失敗しているかが表示されます。テストが失敗している場合は、テストステータスをさらに調査します。

{{< img src="tracing/api_catalog/api-catalog-tests.png" alt="API カタログエクスプローラーの API テストステータスメニューとテスト作成ボタン" style="width:40%;" >}}

このエンドポイントに対して別の Synthetic API テストを作成するには、**API TESTS 列**の **+ API Test** をクリックします。テストのセットアップについては、[Synthetic HTTP API テスト][3]のドキュメントを参照してください。

## セキュリティギャップの発見と解消

Datadog [Application Security Management (ASM)][4] により、エクスプローラーの **SECURITY SIGNALS** 列には、ASM がエンドポイントに関連するサービスに対する脅威を検出したかどうかが表示されます。この列で表を並べ替えると、どのエンドポイントが最も影響を受けているかを確認できます。コードまたはアップストリームの依存関係にある脅威や脆弱性を調査して対処するには、**View in ASM** をクリックします。

{{< img src="tracing/api_catalog/api-catalog-security-signals.png" alt="API カタログエクスプローラーのセキュリティシグナルステータスメニューと「ASM で表示」ボタン" style="width:60%;" >}}

## 参考資料

{{< partial name="whats-next/whats-next.html" >}}

[1]: /ja/monitors/
[2]: /ja/tracing/api_catalog/explore_and_catalog_apis/
[3]: /ja/synthetics/api_tests/http_tests/
[4]: /ja/security/application_security/threats/