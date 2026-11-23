# ポーズスキャナー

写真・ラフ画・棒人間から最大2人のポーズを作るWindowsアプリです。3D人形で姿勢を確認・修正し、CLIP STUDIO PAINT EXへ渡せるBVHを保存します。

## ダウンロード

[GitHub Releases の公開ベータ](https://github.com/SakuraYoshida328/pose-scanner-public/releases/tag/v0.1.0-beta.1) から `PoseScanner-0.1.0-beta.1-Windows-x64.zip` をダウンロードしてください。

1. Windows 11のx64環境に、Windows用64ビット版の [Python 3.12](https://www.python.org/downloads/release/python-31210/) を入れます。Tcl/Tkを含め、インストーラーでは「Add python.exe to PATH」をオンにしてください。
2. ZIPをすべて展開し、`Start Pose Scanner.cmd` をダブルクリックします。
3. 初回の確認で［はい］を押すと、PyPIからライブラリ、Googleの公式配布元から推定モデルを取得します。初回はインターネット接続と約2 GBの空き容量が必要です。

ZIP内の `Manual.html` は、ブラウザで開ける取扱説明書です。GitHubでも [詳しい操作ガイド](USER_GUIDE.md) を読めます。

## 使い方

［画像を開く］→［3Dポーズに変換］→［クリスタ用に保存］の順に操作します。1人だけ変換できたときは、［＋ 人物を追加］からもう1人を囲めます。［補助読み込み］と［細かく調整］で、関節の位置、画面外の扱い、奥行きを指定できます。

画像の解析はPC内で実行します。ポーズスキャナー自体はChatGPT、Blender、CLIP STUDIO PAINTを使わずに動作します。クリスタでBVHを適用する場合は、CLIP STUDIO PAINT EXを用意してください。

## ベータ版の確認範囲

全身の向き、重なった関節、人物同士の手の接触、奥行きには補正が必要な場合があります。2人のBVHは別々に保存され、クリスタ側で人形の相対位置を調整します。編集データ `.pose.json` には元画像が含まれます。
