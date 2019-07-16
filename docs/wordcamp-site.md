# WordCampサイトの構成

本稿ではWordCampサイトの構成についてまとめる。

## 基本情報

- 各WordCampサイトはマルチサイトの子サイトである。
- 各子サイトにはテーマ、プラグインなどを追加することが一切できない。参考：[保存版・WordCampサイトの作り方](https://capitalp.jp/2017/09/21/how-to-make-wordcamp-site/)
- 当然ながら、REST APIのエンドポイントを追加することもできないし、OAuth認証を追加することもできない。

## WordCampサイトの特殊性

WordCampサイトは通常のWordPressサイトと異なり、専用のプラグインがいくつか導入されている。特筆すべきものは下記の通り。

- [CampTix](https://ja.wordpress.org/plugins/camptix/): WordCamp用のプラグイン。チケット販売、一括メール送信、チケット販売データのエクスポートなど。ほかに `CampTix xxx` という名前で決済インテグレーションがインストールされている。
- WordCamp API: WordCampサイトのAPIを追加するもの。
- WordCamp PostTypes: WordCampにスピーカー、スポンサーなどの投稿タイプを追加するもの。

## 貢献方法

上記の通り、ほとんどのものは提供されているものを利用するだけなので、変更の余地がない。唯一可能なのはコアにコントリビュートすること。基本的には以下の流れ。

1. [Meta Track](https://meta.trac.wordpress.org)で既存のチケットがないか検索。あればそれに参加。
2. チケットがなければ[作成](https://meta.trac.wordpress.org/newticket)する。コンポーネントは"wordcamp.org"を選択。
3. 議論が必要な場合はコミュニティチーム（[P2](https://make.wordpress.org/community/)、Slack #community-team）と相談する。技術的な内容はコアSlackの #meta または #meta-wordcamp チャンネルで議論可能。
4. 以下の環境を構築してプルリク・パッチを送る。

その他詳細: [Feature Requests for Community Sites](https://make.wordpress.org/community/feature-requests-for-community-sites/)、[Process for Feature Design and Implementation](https://make.wordpress.org/community/feature-requests-for-community-sites/design-implementation-process/)

### 環境設定
- [Github](https://github.com/WordPress/wordcamp.org) VVVというVagrantベースの仮想環境が用意されている。ただし、全てのサイト（Codexとか）も入っているので、異常に重い。
  - VVVのアドオンであるIan Dunnの[WordPress Meta Environment](https://github.com/iandunn/wordpress-meta-environment)にサンプルなどが含まれる。
- または[GitHubのWordCamp.orgレポジトリ](https://github.com/WordPress/wordcamp.org/)をクローンすることもできる。
  - レポジトリのクローンを使う場合は、CampTix、[CampTix](https://wordpress.org/plugins/search.php?q=camptix)、TagregatorプラグインをWordPress.orgレポジトリから入れる必要がある。[SupportFlow](https://github.com/SupportFlow/supportflow)はGitHubにある。
  - メタ環境の[provisionフォルダー](https://github.com/WordPress/meta-environment/tree/master/wordcamp.test/provision)にサンプルデータベース、wp-config ファイル、その他のコード・スクリプトがある。
