---
further_reading:
- link: /integrations/kafka/
  tag: Documentation
  text: Kafka インテグレーション
- link: /tracing/service_catalog/
  tag: Documentation
  text: サービスカタログ
kind: documentation
title: Data Streams Monitoring for Python のセットアップ
---

{{< site-region region="ap1" >}}
<div class="alert alert-info">Data Streams Monitoring は、AP1 リージョンではサポートされていません。</a></div>
{{< /site-region >}}

### 前提条件

Data Streams Monitoring を開始するには、Datadog Agent と Python ライブラリの最新バージョンが必要です。
* [Datadog Agent v7.34.0 以降][1]
* [Python Tracer v1.15.0 以降][2]

### インストール

Python は自動インスツルメンテーションを使用して、Data Streams Monitoring がエンドツーエンドのレイテンシーやキューとサービス間の関係を測定するために必要な追加のメタデータを挿入し抽出します。Data Streams Monitoring を有効にするには、Kafka にメッセージを送信する (またはメッセージを消費する) サービス上で `DD_DATA_STREAMS_ENABLED` 環境変数を `true` に設定します。

例:
```yaml
environment:
  - DD_DATA_STREAMS_ENABLED: "true"
```

### サポートされるライブラリ
Data Streams Monitoring は、[confluent-kafka ライブラリ][3]をサポートしています。

## その他の参考資料

{{< partial name="whats-next/whats-next.html" >}}

[1]: /ja/agent
[2]: /ja/tracing/trace_collection/dd_libraries/python
[3]: https://pypi.org/project/confluent-kafka/