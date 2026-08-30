# chiku-mikke-data

「チクみっけ」アプリ用の、住所（町丁名）⇄ 地区名 対応データ置き場です。
アプリからは jsDelivr 経由でこのリポジトリのJSONを直接読み込みます。

## 構成

- `manifest.json` … 対応済み都道府県の一覧
- `prefectures/<都道府県slug>/manifest.json` … その県内の市区町村一覧（対応状況フラグ付き）
- `prefectures/<都道府県slug>/<市区町村slug>.json` … 実データ（町丁名⇄地区名）

## データを追加する時のルール

1. 該当自治体が「住所別地区確認表」のような資料を公開しているか確認する
2. 見つかったら、福井市のJSON（`prefectures/fukui/fukui-shi.json`）と同じ形式に整形する
3. `prefectures/<県slug>/manifest.json` の該当自治体の `available` を `true` に変更する
4. まだ県自体のフォルダが無い場合は `prefectures/<県slug>/` を新規作成し、
   トップの `manifest.json` にもその県を追加する
