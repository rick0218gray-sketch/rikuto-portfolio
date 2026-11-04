# Rikuto | Data Science Portfolio

上智大学大学院の応用データサイエンス学位プログラムに所属し、2028年3月に修了予定です。機械学習、LLM、統計分析、Webアプリ開発に取り組んでいます。

**English summary.** I am a graduate student in Applied Data Science at Sophia University, expecting to graduate in March 2028. This portfolio includes a machine-learning model selection app, a SmolVLA adaptation experiment, and an undergraduate study on mobile connectivity and GDP per capita.

## 開発・研究成果

| プロジェクト | 目的と担当 | 使用技術 | 確認できる内容 |
| --- | --- | --- | --- |
| [sklearn-map-lab](https://github.com/rick0218gray-sketch/sklearn-map-lab) | モデルを選んだ理由まで残せるよう、Codexを活用してローカルWebアプリを開発 | Python、FastAPI、React、scikit-learn | データ診断、共通分割でのモデル比較、採用理由の記録、ホールドアウト評価。合成データで再現可能 |
| [SmolVLAのLoRA追加学習とLIBERO-plus評価](https://github.com/rick0218gray-sketch/smolvla-libero-lora) | 講座の課題を起点に、Claudeを活用してLoRAの学習設定と評価手順を改良 | Python、SmolVLA、LeRobot、LoRA、LIBERO-plus | Spatialは両モデル30/30。4スイート集計はベース28/33、LoRA版14/33。設定の変更点と実測集計を公開 |
| [モバイル通信環境と一人当たりGDPの国際パネル分析](https://github.com/rick0218gray-sketch/mobile-connectivity-panel) | 学部卒業研究として、通信指標の選定、国・年パネルの整形、推定仕様の比較を実施 | R、plm | 二方向固定効果、1年ラグ、交互作用を含む分析例。公開版は合成データで実行可能 |

## 使用技術

- **機械学習・データ処理**　Python、pandas、scikit-learn、PyTorch
- **Web開発**　FastAPI、React、Vite
- **統計分析**　R、plm、パネルデータ分析
