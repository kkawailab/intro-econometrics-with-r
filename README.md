# Introduction to Econometrics with R - 練習問題集

「[Introduction to Econometrics with R](https://www.econometrics-with-r.org/)」の各章に対応した練習問題集です。全16章、各10問、計160問の練習問題と模範解答をJupyter Notebook形式で提供しています。

## 目次

- [概要](#概要)
- [必要な環境](#必要な環境)
- [セットアップ](#セットアップ)
- [使い方](#使い方)
- [練習問題一覧](#練習問題一覧)
- [使用パッケージ](#使用パッケージ)
- [ファイル構成](#ファイル構成)
- [更新履歴](#更新履歴)

## 概要

このリポジトリは、計量経済学の入門教科書「Introduction to Econometrics with R」の学習をサポートするための練習問題集です。

**特徴:**
- 全16章に対応した練習問題（各章10問）
- 各問題に模範解答付き
- Jupyter Notebook（Rカーネル）形式で実行可能
- 実際のデータセット（CASchools, Fatalities, HMDA等）を使用した実践的な問題
- 問題文・解説は日本語

## 必要な環境

- **R** (バージョン 4.0以上推奨)
- **Jupyter Notebook** with IRkernel
- **必要なRパッケージ** (下記参照)

## セットアップ

### 1. Rのインストール

#### Ubuntu/Debian
```bash
sudo apt-get update
sudo apt-get install r-base r-base-dev
```

#### macOS (Homebrew)
```bash
brew install r
```

#### Windows
[CRAN](https://cran.r-project.org/bin/windows/base/) からインストーラをダウンロード

### 2. Jupyter と IRkernel のインストール

```bash
# Python環境でJupyterをインストール
pip install jupyter

# RでIRkernelをインストール
R -e "install.packages('IRkernel', repos='https://cloud.r-project.org/')"
R -e "IRkernel::installspec()"
```

### 3. 必要なRパッケージのインストール

Rを起動して以下を実行：

```r
packages <- c(
  "AER",           # データセットと計量経済学関数
  "lmtest",        # 仮説検定
  "sandwich",      # 頑健標準誤差
  "car",           # 回帰診断
  "plm",           # パネルデータ分析
  "dynlm",         # 動的線形モデル
  "forecast",      # 時系列予測
  "vars",          # VARモデル
  "urca",          # 単位根検定
  "tseries",       # 時系列分析
  "strucchange",   # 構造変化検定
  "fGarch",        # GARCHモデル
  "dplyr",         # データ操作
  "ggplot2",       # 可視化
  "moments"        # 高次モーメント
)

install.packages(packages, repos = "https://cloud.r-project.org/")
```

### 4. リポジトリのクローン

```bash
git clone https://github.com/yourusername/intro-econometrics-with-r.git
cd intro-econometrics-with-r
```

## 使い方

### Jupyter Notebookの起動

```bash
jupyter notebook
```

ブラウザが開いたら、`exercises/` フォルダ内のノートブックを選択して開きます。

### ノートブックの構成

各ノートブックは以下の構成になっています：

1. **章のタイトルと概要** - 学習内容の説明
2. **必要なパッケージの読み込み** - 最初のコードセルで実行
3. **各問題（10問）**
   - 問題文（マークダウンセル）
   - 回答欄（空のコードセル）← ここに自分の回答を入力
   - 「模範解答」ヘッダー
   - 模範解答コード（実行済み）

### 学習の進め方

1. **問題を読む** - 問題文を理解する
2. **自分で解く** - 空の回答欄にコードを書いて実行
3. **模範解答と比較** - 自分の回答と模範解答を比較
4. **結果を確認** - 模範解答の出力を参考にする

## 練習問題一覧

### 第1章: Introduction（イントロダクション）
[exercises/chapter01_introduction.ipynb](exercises/chapter01_introduction.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 基本的な計算（算術演算、べき乗） |
| 2 | 変数への代入 |
| 3 | ベクトルの作成（数値、文字列、論理値） |
| 4 | ベクトルの操作（インデックス、条件抽出） |
| 5 | 基本的な統計関数（mean, sd, min, max） |
| 6 | データフレームの作成 |
| 7 | データフレームの操作 |
| 8 | 関数の作成 |
| 9 | 基本的なグラフ作成（散布図） |
| 10 | パッケージのインストールと読み込み |

### 第2章: Probability Theory（確率論）
[exercises/chapter02_probability_theory.ipynb](exercises/chapter02_probability_theory.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 確率変数と確率分布 |
| 2 | 期待値と分散の計算 |
| 3 | 正規分布のシミュレーション |
| 4 | 二項分布 |
| 5 | 同時分布と周辺分布 |
| 6 | 共分散と相関係数 |
| 7 | 条件付き期待値 |
| 8 | 大数の法則 |
| 9 | 中心極限定理 |
| 10 | モンテカルロシミュレーション |

### 第3章: A Review of Statistics（統計学の復習）
[exercises/chapter03_statistics_review.ipynb](exercises/chapter03_statistics_review.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 点推定量（標本平均） |
| 2 | 標準誤差の計算 |
| 3 | 母平均の区間推定 |
| 4 | 仮説検定（t検定） |
| 5 | p値の計算と解釈 |
| 6 | 二標本t検定 |
| 7 | 信頼区間と仮説検定の関係 |
| 8 | 第一種・第二種の過誤 |
| 9 | 検定の検出力 |
| 10 | 有限標本特性と漸近特性 |

### 第4章: Linear Regression with One Regressor（単回帰）
[exercises/chapter04_simple_regression.ipynb](exercises/chapter04_simple_regression.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | OLS推定（CASchoolsデータ） |
| 2 | 回帰係数の解釈 |
| 3 | 決定係数（R²）の計算 |
| 4 | 残差の分析 |
| 5 | 予測値の計算 |
| 6 | 回帰直線の可視化 |
| 7 | SER（標準誤差）の計算 |
| 8 | 外れ値の影響 |
| 9 | 対数変換 |
| 10 | OLS推定量の導出（シミュレーション） |

### 第5章: Hypothesis Tests and CI in SLR（単回帰の仮説検定）
[exercises/chapter05_hypothesis_tests_slr.ipynb](exercises/chapter05_hypothesis_tests_slr.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | t検定（係数の有意性） |
| 2 | 信頼区間の計算 |
| 3 | 両側検定と片側検定 |
| 4 | ダミー変数を使った回帰 |
| 5 | ロバスト標準誤差 |
| 6 | 不均一分散の検定 |
| 7 | 有意水準と検出力 |
| 8 | シミュレーション：t統計量の分布 |
| 9 | 予測区間 |
| 10 | 回帰結果の報告 |

### 第6章: Linear Regression with Multiple Regressors（重回帰）
[exercises/chapter06_multiple_regression.ipynb](exercises/chapter06_multiple_regression.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 重回帰モデルの推定 |
| 2 | 省略変数バイアス（OVB） |
| 3 | 自由度調整済み決定係数 |
| 4 | 多重共線性の検出（VIF） |
| 5 | 完全多重共線性 |
| 6 | OLS仮定の確認 |
| 7 | 標準化回帰係数 |
| 8 | 偏回帰プロット |
| 9 | モデル比較（AIC/BIC） |
| 10 | OLSの一致性（シミュレーション） |

### 第7章: Hypothesis Tests and CI in MR（重回帰の仮説検定）
[exercises/chapter07_hypothesis_tests_mr.ipynb](exercises/chapter07_hypothesis_tests_mr.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 個別係数のt検定 |
| 2 | F検定（モデル全体の有意性） |
| 3 | 結合仮説検定 |
| 4 | 係数の等値検定 |
| 5 | 信頼領域（信頼楕円） |
| 6 | 制約付き最小二乗法 |
| 7 | 単一係数の信頼区間 |
| 8 | 漸近理論とF検定 |
| 9 | 交差検定 |
| 10 | モデル選択とF検定 |

### 第8章: Nonlinear Regression Functions（非線形回帰）
[exercises/chapter08_nonlinear_regression.ipynb](exercises/chapter08_nonlinear_regression.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 多項式回帰 |
| 2 | 対数変換（log-level, level-log, log-log） |
| 3 | 交互作用項 |
| 4 | 二値変数との交互作用 |
| 5 | 二次関数モデル |
| 6 | 区分線形回帰 |
| 7 | 係数の解釈（弾力性） |
| 8 | 非線形効果の可視化 |
| 9 | モデル選択（線形 vs 非線形） |
| 10 | 予測と限界効果 |

### 第9章: Assessing Studies（研究の評価）
[exercises/chapter09_assessing_studies.ipynb](exercises/chapter09_assessing_studies.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 内的妥当性と外的妥当性 |
| 2 | 欠落変数バイアス |
| 3 | 測定誤差 |
| 4 | サンプルセレクションバイアス |
| 5 | 同時性バイアス |
| 6 | 外れ値と影響点 |
| 7 | モデルの特定化誤り |
| 8 | 感度分析 |
| 9 | 頑健性チェック |
| 10 | 研究結果の解釈 |

### 第10章: Regression with Panel Data（パネルデータ）
[exercises/chapter10_panel_data.ipynb](exercises/chapter10_panel_data.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | パネルデータの構造 |
| 2 | プールドOLS |
| 3 | 固定効果モデル |
| 4 | ランダム効果モデル |
| 5 | ハウスマン検定 |
| 6 | 時間固定効果 |
| 7 | 二元固定効果モデル |
| 8 | クラスター頑健標準誤差 |
| 9 | 差の差分析（DID基礎） |
| 10 | Fatalitiesデータの分析 |

### 第11章: Regression with Binary Dependent Variable（二値従属変数）
[exercises/chapter11_binary_dependent.ipynb](exercises/chapter11_binary_dependent.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 線形確率モデル（LPM） |
| 2 | LPMの問題点 |
| 3 | プロビットモデル |
| 4 | ロジットモデル |
| 5 | 限界効果の計算 |
| 6 | 予測確率 |
| 7 | モデルの適合度 |
| 8 | プロビットとロジットの比較 |
| 9 | 疑似決定係数 |
| 10 | HMDAデータの分析 |

### 第12章: Instrumental Variables Regression（操作変数法）
[exercises/chapter12_instrumental_variables.ipynb](exercises/chapter12_instrumental_variables.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 内生性問題 |
| 2 | 操作変数の条件 |
| 3 | 2SLS推定 |
| 4 | 第一段階回帰 |
| 5 | 弱い操作変数 |
| 6 | 過剰識別検定 |
| 7 | 複数の操作変数 |
| 8 | たばこ需要の分析 |
| 9 | IVとOLSの比較 |
| 10 | 操作変数の妥当性 |

### 第13章: Experiments and Quasi-Experiments（実験と準実験）
[exercises/chapter13_experiments.ipynb](exercises/chapter13_experiments.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | ランダム化比較試験（RCT） |
| 2 | 共変量の調整 |
| 3 | 差の差分析（DID）基礎 |
| 4 | 平行トレンド仮定 |
| 5 | 回帰不連続デザイン（RDD）基礎 |
| 6 | RDDの傾きの違い |
| 7 | RDDのバンド幅選択 |
| 8 | ファジーRDD |
| 9 | 複数期間のDID |
| 10 | 処置効果の異質性 |

### 第14章: Introduction to Time Series Regression（時系列入門）
[exercises/chapter14_time_series.ipynb](exercises/chapter14_time_series.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 時系列データの可視化 |
| 2 | AR(1)モデルの推定 |
| 3 | AR(p)の次数選択 |
| 4 | 分布ラグモデル |
| 5 | 時系列の予測 |
| 6 | 系列相関の検定 |
| 7 | Newey-West標準誤差 |
| 8 | 定常性とランダムウォーク |
| 9 | 見せかけの回帰 |
| 10 | GDPデータの分析 |

### 第15章: Estimation of Dynamic Causal Effects（動的因果効果）
[exercises/chapter15_dynamic_causal.ipynb](exercises/chapter15_dynamic_causal.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 動的因果効果の概念 |
| 2 | ラグ次数の選択 |
| 3 | ADLモデル |
| 4 | 外生性の仮定 |
| 5 | HAC標準誤差 |
| 6 | オレンジジュース価格分析 |
| 7 | 金融政策の効果 |
| 8 | VARモデル |
| 9 | 予測誤差分散分解 |
| 10 | 実データでの応用 |

### 第16章: Additional Topics in Time Series（時系列の追加トピック）
[exercises/chapter16_additional_topics.ipynb](exercises/chapter16_additional_topics.ipynb)

| # | 問題内容 |
|---|---------|
| 1 | 単位根とランダムウォーク |
| 2 | ADF検定 |
| 3 | PP検定とKPSS検定 |
| 4 | 共和分の概念 |
| 5 | Engle-Granger共和分検定 |
| 6 | 誤差修正モデル（ECM） |
| 7 | ボラティリティ・クラスタリング |
| 8 | GARCH(1,1)モデル |
| 9 | 構造変化の検定 |
| 10 | 実データでの応用 |

## 使用パッケージ

| パッケージ | 用途 |
|-----------|------|
| `AER` | 計量経済学データセット、ivreg() |
| `lmtest` | 仮説検定（coeftest, bptest等） |
| `sandwich` | 頑健標準誤差（vcovHC, NeweyWest） |
| `car` | 回帰診断（vif, linearHypothesis） |
| `plm` | パネルデータ分析 |
| `dynlm` | 動的線形モデル |
| `forecast` | 時系列予測 |
| `vars` | VARモデル |
| `urca` | 単位根検定 |
| `tseries` | 時系列分析 |
| `strucchange` | 構造変化検定 |
| `fGarch` | GARCHモデル |

## ファイル構成

```
intro-econometrics-with-r/
├── README.md                 # このファイル
├── CLAUDE.md                 # Claude Code用のガイド
├── .gitignore
└── exercises/
    ├── chapter01_introduction.ipynb
    ├── chapter02_probability_theory.ipynb
    ├── chapter03_statistics_review.ipynb
    ├── chapter04_simple_regression.ipynb
    ├── chapter05_hypothesis_tests_slr.ipynb
    ├── chapter06_multiple_regression.ipynb
    ├── chapter07_hypothesis_tests_mr.ipynb
    ├── chapter08_nonlinear_regression.ipynb
    ├── chapter09_assessing_studies.ipynb
    ├── chapter10_panel_data.ipynb
    ├── chapter11_binary_dependent.ipynb
    ├── chapter12_instrumental_variables.ipynb
    ├── chapter13_experiments.ipynb
    ├── chapter14_time_series.ipynb
    ├── chapter15_dynamic_causal.ipynb
    └── chapter16_additional_topics.ipynb
```

## 更新履歴

### 2024-12-13
- 全16章のノートブックを実行し、出力結果を保存
- CLAUDE.mdを追加（Claude Code用のガイダンス）
- .gitignoreを追加

### 2024-12-12
- 初版リリース
- 全16章、各10問、計160問の練習問題を作成
- 各問題に模範解答を追加
- Jupyter Notebook（Rカーネル）形式で作成

## ライセンス

MIT License

## 参考文献

- Stock, J. H., & Watson, M. W. (2015). *Introduction to Econometrics* (3rd ed.). Pearson.
- Hanck, C., Arnold, M., Gerber, A., & Schmelzer, M. (2020). *Introduction to Econometrics with R*. https://www.econometrics-with-r.org/

## 貢献

Issue や Pull Request は歓迎します。
