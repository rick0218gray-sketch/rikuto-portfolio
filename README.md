# Rikuto | Data Science Portfolio

上智大学大学院の応用データサイエンス学位プログラムに所属し、2028年3月に修了予定です。機械学習、LLM、統計分析、Webアプリ開発に取り組んでいます。各プロジェクトの数値は、リンク先のリポジトリに記録した実測値または合成データでの動作確認の値です。

**English summary.** I am a graduate student in Applied Data Science at Sophia University, expecting to graduate in March 2028. This portfolio includes a machine-learning model selection app, a SmolVLA adaptation experiment, and an undergraduate study on mobile connectivity and GDP per capita. Every figure below is taken from the linked repository.

## プロジェクト一覧

| プロジェクト | 目的 | 取り組んだこと | 使用技術 | リンク |
| --- | --- | --- | --- | --- |
| [モデル比較・採用記録アプリ](#sklearn-map-lab) | モデルを選んだ理由まで残せる比較の流れを作る | Codexを活用した個人開発。データ診断から最終テスト・予測までを1画面のローカルWebアプリに実装 | Python、FastAPI、React、scikit-learn、PyTorch | [sklearn-map-lab](https://github.com/rick0218gray-sketch/sklearn-map-lab) |
| [SmolVLAのLoRA追加学習](#smolvlaのlora追加学習とlibero-plus評価) | 講座の課題を起点に、追加学習の効果を同条件で比較する | Claudeを活用し、学習データの選定数、LoRA設定、評価の試行数と集計を変更 | Python、SmolVLA、LeRobot、LoRA、LIBERO-plus | [smolvla-libero-lora](https://github.com/rick0218gray-sketch/smolvla-libero-lora) |
| [モバイル通信環境と一人当たりGDP](#モバイル通信環境と一人当たりgdpの国際パネル分析) | 通信環境と経済水準の関係を国・年パネルで調べる | 学部の卒業研究として、指標の選定、パネルの整形、推定仕様の比較を実施 | R、plm、パネルデータ分析 | [mobile-connectivity-panel](https://github.com/rick0218gray-sketch/mobile-connectivity-panel) |

## 機械学習・Webアプリ

### sklearn-map-lab

表データを取り込み、複数の機械学習モデルを共通の分割で交差検証し、採用・保留・却下の理由を保存してから最終テストを行うローカルWebアプリです。最終テストは採用確定後にだけ評価し、評価後は採用モデルを変更できない設計にしました。

- **確認できること**　バックエンドの14テストが通過し、6タスクの合成データで65のタスク・モデルの組合せと95種類の診断グラフの実行を確認。
- **数値の範囲**　掲載値はすべて合成データでの動作確認で、実データでの性能は評価していません。

## ロボット学習（Physical AI）

### SmolVLAのLoRA追加学習とLIBERO-plus評価

Physical AI講座の課題を出発点に、ロボットの視覚・言語・行動モデルSmolVLAへSpatialタスクの成功軌道でLoRA追加学習を行い、ベースと同じタスクID・試行数・評価seedで比較しました。

- **結果**　Spatial主評価は両モデルとも30/30。4スイートの追加評価ではベース28/33に対しLoRA版14/33で、GoalとLIBERO-10で低下しました。
- **注意**　複数の設定を同時に変えた単一seedの試行で、低下の原因は未検証です。成功数・試行数のCSVと再集計スクリプトを公開しています。

## 統計分析

### モバイル通信環境と一人当たりGDPの国際パネル分析

学部の卒業研究で、GSMA Mobile Connectivity Indexと世界銀行の指標を国・年で対応付け、国・年の固定効果、1年ラグ、交互作用を含む仕様を比較しました（R、plm）。

- **公開版の内容**　元の研究のデータ・論文・推定結果は含みません。固定シードで生成した架空のパネル（8か国・9年）で、二方向固定効果・1年ラグ・交互作用の1仕様をbase Rだけで再現できる手法デモです。

## 使用技術

- **機械学習・データ処理**　Python、pandas、scikit-learn、PyTorch
- **ロボット学習**　SmolVLA、LeRobot、LoRA、LIBERO-plus
- **Web開発**　FastAPI、React、Vite
- **統計分析**　R、plm、パネルデータ分析（二方向固定効果）
- **開発支援**　Codex、Claude
