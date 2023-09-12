# Paper


## 概要

* Paper: [To Trust or to Think: Cognitive Forcing Functions Can Reduce Overreliance on AI in AI-assisted Decision-making](https://dl.acm.org/doi/abs/10.1145/3449287)
* Date: 22 April 2021
* Authors: Zana Buçinca, Maja Barbara Malaya, Krzysztof Z. Gajos
* Accepted at:
* Keywords
  * 意思決定
  * XAI
  * 認知機能
* Point of View


### Introduction
AIへの過度な信頼を減らすためにXAIが研究されてたりするけど、上手くいっていない。  
AIへの過度な信頼はXAIだけでは解決できず、認知的強制機能(cognitive forcing functions)を導入する必要がある


### Related Work



## Dataset



## Method
- Simple Explainable AI(SXAI) Baselines
  - Explanation
    - 擬似AIが認識した皿上の食材と、認識した食材の中で最も炭水化物の多い食材の上位4つの代替品のリストが含まれている。代替品には推定炭水化物削減量と風味の類似性を示す特定の特徴ベースの説明が添付されている。説明とAIの代替が同時に示されている。
  - Uncertainty
    - Explanationと同様の説明＋「AIはその提案にX％の自信を持っています」というプロンプトも提示。このプロンプトはAIがその提案に自信のない場合のみに提示するよう設計。
- Cognitive Forcing Functions(CFF)
  - On demand
    - AIの提案をデフォルトでユーザーには提示せず、ユーザーが「AIの提案を見る」ボタンをクリックすることで提案と説明を見ることができるような設定。これは認知的強制機能の軽い形態。
  - Update
    - AIの助けを借りずにタスクを解き、解いた後にAIの提案と説明が表示され、回答を更新できるもの。
  - Wait
    - 「AIが画像を処理しています」というメッセージが表示され、AIの回答を見るのに待機させられる。先行研究により`遅いアルゴリズムがユーザーの正確さを向上させる`ことが示させられているらしい。AIの提案を待っている間にユーザーが仮説を形成し、仮説をサポートするかどうかの視点でAIの説明を評価すると考えられる。
- 



## Experiment
食事の画像が表示され、その中で最も炭水化物が多い食材を、炭水化物が少なく、風味が似ている食材に置き換えるタスク。  
1. まず、取り除く食材を選ぶ（約10の選択肢）
2. 取り除いた食材の代わりに新しい食材を選ぶ（約10の選択肢）

評価指標に関しては、書いてあったけどしっかり読んでいない。栄養系の指標が書かれていた。  
XAI系の研究、こういう栄養系のタスクが多い気がする。  
報酬設定することで本気で解くように設計されている。AIに依存するかどうかってここが大きい気がする。



<img src=./image/To_Trust_exp.png width=300>
## Result

SXAIはno AIに対して全ての指標に対してパフォーマンスを向上することができた。SXAIとCFFのスコア差に有意な違いはなかった。  
しかし、AIの予測が間違っていた場合、CFFはSXAIと比較して大きくパフォーマンスを向上させた。しかし、CFF、SXAIのどちらに対してもno AIの参加者の方が有意にパフォーマンスが高かった。
