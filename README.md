# 生成AI を用いた統計学の学習用練習問題
以下の生成において，APIとして，gpt-4-1106-previewを用いて，temperature=1として実行した．
## 生成手順
問題文（ストーリー）と数値の生成を生成AIを用いて生成する．
## 検定問題のストーリー生成
### プロンプト
```
#命令文：あなたは大学で統計学を教える教師です．1標本t検定の問題文を条件を満たすように作成してください．作業は以下をstep-by-stepで進めること．
1. 問題文の条件と例文を確認する．
2. 条件を満たす問題文案を生成する．
3. 問題文案のみを結果として出力する．
#条件
・上側（または下側・両側）検定の問題文を1つ作成
・最終出力は問題文のみとする
・問題文中に検定パターンを書かない
・検定に適切なコンテキストを設定する
・母平均の値を必ず明記し該当部分を{mean}に置換
（標本サイズ（size），標本データ（data），有意水準
（alpha）についても同様）
・解説や解き方のヒントは問題文中に書かない
・母集団が正規分布にしたがうことを必ず明記
・指定された検定方法を行う必要性が明確
・冗長な表現や言い回しを用いず簡潔な文章にする
・問題文のみを出力結果とする
・問題文以外の余分な語句や記号は絶対に含めない
・問題文は必ず条件を満たしていること
・問題文例（上側，下側，両側，各2例ずつ．省略）
```
### 生成された問題文
ChatGPT　API（gpt-4-1106-preview）を用いて「1標本t検定の問題文」を作成した．
上側，下側，両側検定の各100問を作成した結果はcsvファイルを参照．
- 上側検定.csv：100問
- 下側検定.csv：100問
- 両側検定.csv：100問
## 数値生成
### プロンプト
```
#命令文
以下の問題文は、1標本t検定の計算問題文です。文中の適切な母平均{mean}と標準偏差{std}の値を1つずつ生成してください．生成結果はjson形式で数値を{mean}{std}のみを出力してください．
#問題文
（穴あきの問題文をここに1つ記載する．省略）
```
### 生成された数値
ストーリー生成で作成した両側検定100問に対して，上述のプロンプトから数値を生成する．
#### 1問に対して1個のパラメータ生成
各問に対して，1個ずつパラメータ生成した．

具体的な数値は，「両側検定_1個のパラメータ.csv」を参照．
#### 1問に対して100個のパラメータ生成
各問に対して，1個ずつパラメータ生成した．

「100個のパラメータ」のディレクトリを参照．

ファイル番号は両側検定100問に対応する．
