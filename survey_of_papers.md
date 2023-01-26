# Survey
Created by [Daiki Tsutsumi](https://tsutsumi-portfolio.wraptas.site/)<br>
自分が読んだ論文を一部まとめたものです。<br>

2023(B3)~

## Table of Contents
- [Survey](#survey)
  - [Table of Contents](#table-of-contents)
  - [Abstract, Attention](#abstract-attention)
- [Survey Diary](#survey-diary)
  - [【2023/01/25】**Classification and Assessment of English Scientific Papers Using Random Forests**](#20230125classification-and-assessment-of-english-scientific-papers-using-random-forests)
  - [【2023/01/26】**学術論文PDFからの関連研究章と引用情報の抽出による論文執筆支援のためのデータセット構築**](#20230126学術論文pdfからの関連研究章と引用情報の抽出による論文執筆支援のためのデータセット構築)
  - [【2023/01/26】**学術論文における関連研究の執筆支援のための被引用論文の推定**](#20230126学術論文における関連研究の執筆支援のための被引用論文の推定)
- [References](#references)

<br>


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

## 【2023/01/26】**学術論文PDFからの関連研究章と引用情報の抽出による論文執筆支援のためのデータセット構築**<br>
[**[小林 et al, 言語処理学会, 2022]**](#nlp2022pdftodataset)


論文執筆支援の研究に用いる研究用データセットを拡充するため、PDF形式の論文から本文、引用に関わる情報を抽出する手法を提案. 背景として、Tex形式の論文で構築されたデータセットが存在する一方PDF形式の論文が多いので、PDFからの情報抽出を行い、データの拡充を目指している. Texと違い章タイトルを明記するような記号ない、などのPDF特有の困難を既存手法を上手く組み合わすことで高い精度を達成している.

## 【2023/01/26】**学術論文における関連研究の執筆支援のための被引用論文の推定**<br>
[**[小山 et al, 言語処理学会, 2021]**](#nlp2021pred_ref_paper)



関連研究の文章と引用関係の情報を用いて、どの論文を引用すべきか割り当てるタスク(引用文献割り当てタスク)と引用元論文と非引用論文のペアが適切であるかどうかを判定するタスク(引用文・被引用文献ペア適正性判定タスク)を行った. 引用文・被引用文献ペア適正性判定タスクでは、引用部分の文章と被引用論文のabstractをペアで学習させて正例である確率を出力する. 引用文献割り当てタスクでは関連論文をいくつか並べた際にどの論文が引用する論文として適しているかを出力する(下図). どちらもBERTやXLNetなどの言語モデルでAccuracy0.8程度の精度を出した.関連研究を引用する時に数多くの論文を調査する労力を削減することを大きな目的としていて、自分の目指している方向と近い(気がする).

<img width="232" alt="image" src="https://user-images.githubusercontent.com/69502527/214764563-ca32c522-fa0a-43c3-89e2-db9518f8e36d.png">









# References
<a name='IPSJ-CH11090006'></a>[1] Yuichiro Kobayashi, Shosaku Tanaka, &Yoichi Tomiura. Classification and Assessment of English Scientific Papers Using Random Forests. In IPSJ, 2011.

<a name='nlp2022pdftodataset'></a>[2] 小林恵大, 小山康平, 成松宏美, &南泰浩. 学術論文PDFからの関連研究章と引用情報の抽出による論文執筆支援のためのデータセット構築. In 言語処理学会 第28回年次大会 発表論文集, 2022, 03.

<a name='nlp2021pred_ref_paper'></a>[3]小山康平, 南泰浩, 成松宏美, 堂坂浩二, 東中竜一郎, 田盛大悟, &平博順. 学術論文における関連研究の執筆支援のための被引用論文の推定. In In 言語処理学会 第27回年次大会 発表論文集, 2021, 03.
