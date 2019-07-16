# WordCampサイトの構成

本稿ではWordCampサイトの構成についてまとめる。

## 基本情報

- 各WordCampサイトはマルチサイトの子サイトである。
- 各子サイトにはテーマ、プラグインなどを追加することが一切できない。参考：[保存版・WordCampサイトの作り方](https://capitalp.jp/2017/09/21/how-to-make-wordcamp-site/)
- 当然ながら、REST APIのエンドポイントを追加することもできないし、OAuth認証を追加することもできない。

## WordCampサイトの特殊性

WordCampサイトは通常のWordPressサイトと異なり、専用のプラグインがいくつか導入されている。特筆すべきものは下記の通り。

- [CampTix](https://ja.wordpress.org/plugins/camptix/) WordCamp用のプラグイン。チケット販売、一括メール送信、チケット販売データのエクスポートなど。ほかに `CampTix xxx` という名前で決済インテグレーションがインストールされている。
- WordCamp API WordCampサイトのAPIを追加するもの。
- WordCamp PostTypes WordCampにスピーカー、スポンサーなどの投稿タイプを追加するもの。

## 貢献方法

上記の通り、ほとんどのものは提供されているものを利用するだけなので、変更の余地がない。唯一可能なのはコアにコントリビュートすること。

- コアSlackの #meta チャンネルで議論可能。
- [Github](https://github.com/WordPress/wordcamp.org) VVVというvagrantベースの仮想環境が用意されている。ただし、全てのサイト（Codexとか）も入っているので、異常に重い。
