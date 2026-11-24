現地調査 WebGIS（閲覧用）

1. QGISで XYZ タイルを生成（ディレクトリ）を使用します。
   terrain: 微地形表現図、PNG、例 Z14～19
   contours: コンター線のみ、透過PNG、例 Z14～19
   labels: 標高値のみ、透過PNG、例 Z17～19
   タイルサイズ 256x256、TMS（Y反転）なし。
   保存先は tiles/terrain、tiles/contours、tiles/labels です。
   再出力する場合は、古いタイルを退避してから作成してください。
   出力ファイルは例 tiles/terrain/19/123456/234567.png のような形式です。
   フォルダ名・拡張子は小文字を使用します。

2. PCのEdgeまたはChromeで setup.html を開き、field-webgis フォルダを選択します。
   読み取り結果を確認して config.js を保存し、同名のファイルを上書きしてください。
   地図の範囲は各レイヤの最大ズームのタイル範囲から自動計算します。

3. index.html を開いて確認します。Leafletライブラリと地理院地図はインターネット経由です。
   ローカルファイルの動作はブラウザによって異なる場合があります。
   実際のGPS確認はHTTPSで公開したURLで行ってください。

4. Cloudflare Pages等の静的サイトに公開します。
   index.html、config.js、tilesフォルダを同じ階層に配置します。
   setup.htmlとREADME.txtは公開不要です。
   Pages無料プラン: 20,000ファイルまで。画面からの直接アップロードは1,000ファイルまで。
   1,000件を超える場合はGit連携またはWranglerを使用します。
   公開可能なデータのみ使用し、必要な出典を表示してください。

5. スマホで公開URLを開き、レイヤのON/OFF、透過率、現在地、調査範囲ボタンを確認します。
   現在地ボタンを押して位置情報を許可すると測位・追従を開始します。
   地図を手で動かすと追従を停止しますが、測位は継続します。
   現在地へボタンで追従を再開し、追従中にボタンを押すと測位を終了します。
   現在地はブラウザ内だけで処理し、位置情報の共有・記録機能はありません。
   地図画像の取得には通信が必要で、完全なオフライン用ではありません。

参照:
QGIS https://docs.qgis.org/3.44/en/docs/user_manual/processing_algs/qgis/rastertools.html
地理院タイル https://maps.gsi.go.jp/development/ichiran.html
Leaflet https://leafletjs.com/
Cloudflare Pages https://developers.cloudflare.com/pages/platform/limits/
