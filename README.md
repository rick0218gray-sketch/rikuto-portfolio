# Rikuto | Data Science Portfolio

上智大学大学院の応用データサイエンス学位プログラムに所属し、2028年3月に修了予定です。機械学習、LLM、ロボット学習（シミュレーション）、統計分析、Webアプリ開発に取り組んでいます。各プロジェクトの数値は、リンク先のリポジトリに記録した実測値または合成データでの動作確認の値です。

**English summary.** I am a graduate student in Applied Data Science at Sophia University, expecting to graduate in March 2028. This portfolio includes a machine-learning model selection app, a SmolVLA adaptation experiment, two simulated robot-learning projects from a Physical AI course (a robot arm that runs learned ACT skills from Japanese commands planned by a local LLM, and 2v2 quadruped futsal trained by imitation learning and self-play PPO), and an undergraduate study on mobile connectivity and GDP per capita. Every figure below is taken from the linked repository.

## プロジェクト一覧

| プロジェクト | 目的 | 取り組んだこと | 使用技術 | リンク |
| --- | --- | --- | --- | --- |
| [モデル比較・採用記録アプリ](#sklearn-map-lab) | モデルを選んだ理由まで残せる比較の流れを作る | Codexを活用した個人開発。データ診断から最終テスト・予測までを1画面のローカルWebアプリに実装 | Python、FastAPI、React、scikit-learn、PyTorch | [sklearn-map-lab](https://github.com/rick0218gray-sketch/sklearn-map-lab) |
| [SmolVLAのLoRA追加学習](#smolvlaのlora追加学習とlibero-plus評価) | 講座の課題を起点に、追加学習の効果を同条件で比較する | Claudeを活用し、学習データの選定数、LoRA設定、評価の試行数と集計を変更 | Python、SmolVLA、LeRobot、LoRA、LIBERO-plus | [smolvla-libero-lora](https://github.com/rick0218gray-sketch/smolvla-libero-lora) |
| [日本語の指令で動くロボットアーム](#日本語の指令でロボットアームの学習済みスキルを順に動かす) | 日本語の指令を、学習した動作の列として実行する | 講座の最終課題。お手本の自動生成、スキル別のACT学習、ローカルLLMによる計画と評価、モデルの常駐実行を実装 | Python、ROS 2、Gazebo、LeRobot（ACT）、Ollama（Qwen2.5） | [physical-AI1-var1](https://github.com/rick0218gray-sketch/physical-AI1-var1) |
| [四足ロボットの2対2フットサル](#四足ロボットの2対2フットサル) | LLM監督の作戦に従うお手本から学び、自己対戦で強くする | 同講座の最終課題の追加作品。お手本の試合、模倣学習、自己対戦の強化学習、歩行方策の追加学習、評価を実装 | Python、Genesis、PyTorch、PPO（rsl_rl）、Ollama（Qwen2.5） | [physical-AI1-futsal](https://github.com/rick0218gray-sketch/physical-AI1-futsal) |
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

### 日本語の指令でロボットアームの学習済みスキルを順に動かす

Physical AI 応用1講座の最終課題です。Gazebo上のCRANE+ V2アームの6動作（お辞儀、左右を指す、握る、手を振る、うなずく）を、スクリプトで自動生成したお手本からスキルごとにACTで学習しました。日本語の指令はローカルLLMがJSON schemaで制約した動作の列に変換し、範囲外の指令は拒否、曖昧な指令は確認を返します。実装・デバッグにClaude、整理と草稿にCodexを使っています。

- **結果**　最終6スキルは各5/5。動作計画の40件評価はqwen2.5 3Bで33/40、7Bで36/40（ローカル8GB GPU）。モデルを常駐させ、1動作の所要時間を約40秒から約10秒に短縮しました。
- **注意**　同じ直立初期姿勢からの少数試行で、開始姿勢をずらすとbow・waveは各0/3でした。シミュレーションのみで、実機は動かしていません。
- **動画**　[YouTube](https://youtu.be/JBdugjrzdls) ／ [リポジトリ内のmp4（2分10秒）](https://github.com/rick0218gray-sketch/physical-AI1-var1/blob/main/crane_act/videos/submission_ad.mp4)

### 四足ロボットの2対2フットサル

同講座の最終課題の追加作品です。Genesis上でUnitree Go2 4体による2対2のフットサル環境を作り、ローカルLLMの監督が日本語の作戦指示を作戦パラメータに変換します。そのお手本の試合から戦術方策を模倣学習し、監督もルールも使わない選手だけの自己対戦（PPO）で強化しました。実装にはClaudeの支援を含みます。

- **結果**　強化学習後の方策はお手本に対し256試合で110勝132分14敗（得点140・失点21）。模倣学習のみでは20勝198分38敗でした。
- **注意**　シミュレーションのみです。強化学習後のキーパーがゴールを離れること、作戦パラメータによる動きの変化は未確認であることなど、限界をリポジトリに記載しています。
- **動画**　[提出動画（YouTube）](https://youtu.be/w7fTLleIA-0)

## 統計分析

### モバイル通信環境と一人当たりGDPの国際パネル分析

学部の卒業研究で、GSMA Mobile Connectivity Indexと世界銀行の指標を国・年で対応付け、国・年の固定効果、1年ラグ、交互作用を含む仕様を比較しました（R、plm）。

- **公開版の内容**　元の研究のデータ・論文・推定結果は含みません。固定シードで生成した架空のパネル（8か国・9年）で、二方向固定効果・1年ラグ・交互作用の1仕様をbase Rだけで再現できる手法デモです。

## 使用技術

- **機械学習・データ処理**　Python、pandas、scikit-learn、PyTorch
- **ロボット学習・シミュレーション**　SmolVLA、LeRobot（ACT）、LoRA、模倣学習、強化学習（PPO、rsl_rl）、LIBERO-plus、Genesis、ROS 2、Gazebo
- **LLM活用**　Ollama上のローカルLLM（Qwen2.5）、JSON schemaによる出力の制約、計画の評価セットによる比較
- **Web開発**　FastAPI、React、Vite
- **統計分析**　R、plm、パネルデータ分析（二方向固定効果）
- **実行環境・開発支援**　Google Colab、WSL2、Docker、Codex、Claude
