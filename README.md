# Rikuto | Data Science Portfolio

上智大学大学院の応用データサイエンス学位プログラムに所属し、2028年3月に修了予定です。機械学習、統計分析、Webアプリ開発に取り組んでいます。

**English summary.** I am a graduate student in Applied Data Science at Sophia University, expecting to graduate in March 2028. This portfolio includes a machine-learning model selection app built with Codex and a public demo of the methods from my undergraduate study on mobile connectivity and GDP per capita. Both run on synthetic data.

## 開発・研究成果

| プロジェクト | 内容 | 本人の関わり | 確認できること |
| --- | --- | --- | --- |
| [sklearn-map-lab](https://github.com/rick0218gray-sketch/sklearn-map-lab) | モデルを同じ分割で比較し、採用理由と最終テストの結果を記録するローカルWebアプリ | Codexを活用した個人開発 | 14テストの通過、実ブラウザでの操作、合成データでの結果の再現手順。[検証の詳細](https://github.com/rick0218gray-sketch/sklearn-map-lab#検証) |
| [モバイル通信環境と一人当たりGDPの国際パネル分析](https://github.com/rick0218gray-sketch/mobile-connectivity-panel) | 学部卒業研究の概要と、推定手法を示す公開デモ | 卒業研究として通信指標の選定、国・年パネルの整形、推定仕様の比較を実施 | 二方向固定効果、1年ラグ、交互作用を含むRスクリプトを合成データで実行可能。[元の研究と公開デモの違い](https://github.com/rick0218gray-sketch/mobile-connectivity-panel#元の研究と公開デモの違い) |

<a href="https://github.com/rick0218gray-sketch/sklearn-map-lab"><img src="https://raw.githubusercontent.com/rick0218gray-sketch/sklearn-map-lab/main/docs/model-comparison.png" alt="sklearn-map-labのモデル比較画面（合成データ）" width="720"></a>

公開している数値はすべて合成データでの動作確認の値です。実データでの性能と、卒業研究の推定結果は掲載していません。

## 使用技術

- **機械学習・データ処理**　Python、pandas、scikit-learn、PyTorch
- **Web開発**　FastAPI、React、Vite
- **統計分析**　R、パネルデータ分析（卒業研究では `plm`、公開デモではbase R）
