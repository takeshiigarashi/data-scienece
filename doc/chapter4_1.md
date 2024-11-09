<script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-mml-chtml.min.js">
</script>
<script type="text/x-mathjax-config">
 MathJax.Hub.Config({
 tex2jax: {
 inlineMath: [['$', '$'] ],
 displayMath: [ ['$$','$$'], ["\\[","\\]"] ]
 }
 });
</script>

# 4.1 画像データ・動画データの性質と処理

## 標本化、量子化、符号化

A-D変換: アナログ画像をデジタル情報に変換すること

**標本化（サンプリング）** アナログ画像を等間隔の格子状に区切る処理。格子１つ１つが画素（ピクセル）。**１つの画素は１つの単色**を表す。

- **解像度** １インチあたりの画素数（ピクセル数）。ppi(Pixels per inch)。
- **ジャギー** 解像度が低いときに、輪郭に現れるギザギザ
- **エイリアシング** 解像度が低いときに現れる本来存在しない縞模様（PCモニタを写真で取るとよく出てくる）

**量子化** 画素ごとに数値を割り当てること。量子化された値は、画像の色の濃淡（階調）を表す。

量子化レベルが1ビットの場合、各画素は０か１の２つの階調で表現される。
グレースケール画像でよくつかわれるのは8ビットで、各画素を白から黒までの256段階で表現する。

**符号化** 画素が保持している値を２進数にして、コンピュータで扱える形のデータに変換すること。

## 画像データの構成と性質

- グレースケール画像は「縦✕横」の２次元配列（値は8ビットで、ピクセルごとの輝度（明るさ）を表す）
- カラー画像は色という次元が加わって、３次元配列とされている。色はRGBの３つ（チャネルと呼ぶ）が必要で、それぞれ8ビット、合計で24ビットで表現される。

## 画像データの保存フォーマット

| |PNG|JPG|GIF|
|--|--|--|--|
|色数|フルカラー（24bit, 1677万色）|フルカラー（24bit, 1677万色）|256色|
|メリット|保存を繰り返しても画像が悪化しない|圧縮率を調整することでファイルサイズを小さくできる|ファイルサイズが小さい。動画を作れる|
|デメリット|ファイルサイズが大きい|保存を繰り返すたびに画質が劣化|色数が制限されている|

## 画像データの典型的な前処理

 <u>画像の特徴を抽出しやすくするための処理</u>

例
 - カラー画像をグレースケールに変更する処理
 - 被写体の色が際立つように、画像の明るさ、コントラスト、色相、彩度などを補正する補正処理
 - サイズの変更、統一する処理

 **フィルタ処理**:  さまざまなフィルタがある

 **ノイズ除去**: 画像認識では、ノイズがあると、ノイズを重要な特徴としてご認識してしまうことがある。

 ノイズ除去の手法として**平滑化**がある。平均フィルタ、メディアンフィルタ、重み付き平均値フィルタ、ガウシアンフィルタなどがある。
 平均フィルタは3x3領域の画素の平均をとって、中心画素を入れ替える方法。

 **リサイズとトリミング**: リサイズは拡大・縮小。トリミングは一部を切り落とすこと。

 **0-1正規化**: 画素値を0と1の間に揃えることで学習効率を上げる。

 **標準化**: 平均を引いて標準偏差で割る処理（標準化）。深いニューラルネットワークでは、何層も演算を繰り返すうちに分布が偏ってくることがある（**共変量シフト**と呼ぶ）。そこで、角層において定期的に標準化処理を行うことで、データの分布の偏りを補正する。学習を早くするとともに、過学習を防止する効果がある。

標準化と似た処理として、主成分分析を組み合わせた**白色化**という処理もある。

**パディング**: 画像認識で使われるCNN（畳み込みニューラルネットワーク）では、１つの層から出力される特徴マップが元の画像よりも小さくなる。画像の縮小を回避したい場合、事前に画像の周りを0で埋める**パディング**を行う。

**グレースケールへの変換**: 機械学習ではカラー画像をグレースケール画像に変換することがある。

**画像処理のためのツール**

PythonにはOpenCVやPillowなどのツールが用意されている。

## 動画データの処理

動画データは<u>画像データの時系列データ</u>。

- **フレーム** 動画を構成する一枚一枚の画像
- **フレームレート** １秒間あたり何フレームを表示できるか。(fps)
- **エンコード** 映像データと音声データを圧縮すること
- **コンテナ** エンコードした映像データと音声データを１つにまとめる動画フォーマット
- **デコード** エンコードされた映像データと音声データをデコードすることで再生される。
- **コーデック** エンコード、デコードを双方向に行うことができるソフトウェア

|フォーマット|特徴|
|----------|----|
|MP4|多様なOSで再生可能。高画質ながら軽量|
|AVI|Windowsにおける動画の標準フォーマット。高画質だがデータサイズがおおきくなりがち|
|MOV|MacOSにおける動画の標準フォーマット。高画質だがデータサイズがおおきくなりがち。ビデオカメラにもよく使われる|
|FIV|YouTubeやニコニコ動画で使用|
|WebM|Gooleによって開発されてウェブ向けの軽量フォーマット|
