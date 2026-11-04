# Rikuto | Data Science Portfolio

上智大学大学院の応用データサイエンス学位プログラムに所属し、2028年3月に修了予定です。機械学習、統計分析、Webアプリ開発に取り組んでいます。

**English summary.** I am a graduate student in Applied Data Science at Sophia University, expecting to graduate in March 2028. This portfolio includes a machine-learning model selection app built with Codex, a SmolVLA adaptation experiment, a simulated quadruped futsal project, and a public demo of the methods from my undergraduate study on mobile connectivity and GDP per capita. The app and the demo run on synthetic data.

## 開発・研究成果

| プロジェクト | 内容 | 本人の関わり | 確認できること |
| --- | --- | --- | --- |
| [sklearn-map-lab](https://github.com/rick0218gray-sketch/sklearn-map-lab) | モデルを同じ分割で比較し、採用理由と最終テストの結果を記録するローカルWebアプリ | Codexを活用した個人開発 | 14テストの通過、実ブラウザでの操作、合成データでの結果の再現手順。[検証の詳細](https://github.com/rick0218gray-sketch/sklearn-map-lab#検証) |
| [SmolVLAのLoRA追加学習とLIBERO-plus評価](https://github.com/rick0218gray-sketch/smolvla-libero-lora) | 講座の課題を起点にしたLoRA追加学習の実験結果 | Claudeを活用してLoRAの学習設定と評価手順を改良 | Spatialは両モデル30/30。4スイート集計はベース28/33、LoRA版14/33。設定の変更点と実測集計を公開 |
| [四足ロボットの2対2フットサル](https://github.com/rick0218gray-sketch/physical-AI1-futsal) | Genesis上のUnitree Go2による2対2フットサル。LLM監督のお手本から模倣学習し、選手だけの自己対戦PPOで強化した講座の最終課題 | 環境、お手本、監督、学習、評価のコードを課題で作成（Claudeによる実装支援を含む） | 強化学習後はお手本に256試合で110勝132分14敗、得点140、失点21。シミュレーションのみ。動画の試合ではキーパーがゴール前にいた時間が6%で、役割を守っていない |
| [モバイル通信環境と一人当たりGDPの国際パネル分析](https://github.com/rick0218gray-sketch/mobile-connectivity-panel) | 学部卒業研究の概要と、推定手法を示す公開デモ | 卒業研究として通信指標の選定、国・年パネルの整形、推定仕様の比較を実施 | 二方向固定効果、1年ラグ、交互作用を含むRスクリプトを合成データで実行可能。[元の研究と公開デモの違い](https://github.com/rick0218gray-sketch/mobile-connectivity-panel#元の研究と公開デモの違い) |

<a href="https://github.com/rick0218gray-sketch/sklearn-map-lab"><img src="https://raw.githubusercontent.com/rick0218gray-sketch/sklearn-map-lab/main/docs/model-comparison.png" alt="sklearn-map-labのモデル比較画面（合成データ）" width="720"></a>

sklearn-map-labと卒業研究の公開デモの数値は、合成データでの動作確認の値です。実データでの性能と、卒業研究の推定結果は掲載していません。

## 使用技術

- **機械学習・データ処理**　Python、pandas、scikit-learn、PyTorch
- **Web開発**　FastAPI、React、Vite
- **ロボット学習**　SmolVLA、LeRobot、LoRA、LIBERO-plus、Genesis、模倣学習、PPO
- **統計分析**　R、パネルデータ分析（卒業研究では `plm`、公開デモではbase R）
