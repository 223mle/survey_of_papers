# Survey
Created by [Daiki Tsutsumi](https://tsutsumi-portfolio.wraptas.site/)<br>
自分が読んだ論文を一部まとめたものです。<br>

## Abstract, Attention
- このリポジトリは自分のサーベイを時系列順にまとめたものです.
- 研究素人の自分がまとめているため、要約や理解に間違いが含まれていることがあります. ご了承ください.
  - また、ただの感想も一部含んでいます.
  - 斜め読み、Abstractのみ読んだものも含まれています.
  - 引用がない図などは、まとめた論文から引用させて頂いてます.



# Survey Diary

## 【2023/01/25】**Classification and Assessment of English Scientific Papers Using Random Forests**<br>
[**[Kobayashi et al., IPSJ, 2011]**](#IPSJ-CH11090006)


母語話者の書いた科学論文と非母語話者の書いた科学論文をランダムフォレストで分類し、分類結果から母語話者(us)と非母語話者(jp)の科学論文を書く上での違いを考察. 非母語話者が頻繁に用いる表現として*on the other hand*などが挙げられており、これは日本人英語学習者は接続表現を過剰使用する傾向があると述べられている. 何か新しい発見をしたというよりは頻繁に用いる表現の差などから、既存の研究で判明していることを分析をして裏付けている感じ. また、ランダムフォレストに限らず色々なモデルを用いて精度比較をしているが、ランダムフォレストが一番精度良く80%を超える精度で正確に分類ができている. 2011年と10年以上昔の論文だが、自分がやろうとしている *論文分類->分類結果からの考察* を行っている. 2011年では両者に明確な差があったが、2023年現在はどうなのか気になる(BERTなどの言語モデルを持ちいた比較も気になる.)





# References
<a name='IPSJ-CH11090006'></a>[1] Yuichiro Kobayashi, Shosaku Tanaka, &Yoichi Tomiura. Classification and Assessment of English Scientific Papers Using Random Forests. In IPSJ, 2011.
