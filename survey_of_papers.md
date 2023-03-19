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
  - [【2023/01/26】**材料科学論文の表の意味解釈データセットの構築**](#20230126材料科学論文の表の意味解釈データセットの構築)
  - [【2023/01/27】**Scientific Paper Recommendation: A Survey**](#20230127scientific-paper-recommendation-a-survey)
  - [【2023/02/11】**Overview of the Third Workshop on Scholarly Document Processing**](#20230211overview-of-the-third-workshop-on-scholarly-document-processing)
  - [【2023/3/13】**論文の階層構造を活用した被引用数予測**](#2023313論文の階層構造を活用した被引用数予測)
  - [【2023/03/19】**文分類問題における精度と解釈性向上のための近傍事例の活用**](#20230319文分類問題における精度と解釈性向上のための近傍事例の活用)
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
* * *
## 【2023/01/26】**学術論文PDFからの関連研究章と引用情報の抽出による論文執筆支援のためのデータセット構築**<br>
[**[小林 et al, 言語処理学会, 2022]**](#nlp2022pdftodataset)


論文執筆支援の研究に用いる研究用データセットを拡充するため、PDF形式の論文から本文、引用に関わる情報を抽出する手法を提案. 背景として、Tex形式の論文で構築されたデータセットが存在する一方PDF形式の論文が多いので、PDFからの情報抽出を行い、データの拡充を目指している. Texと違い章タイトルを明記するような記号ない、などのPDF特有の困難を既存手法を上手く組み合わすことで高い精度を達成している.

* * *
## 【2023/01/26】**学術論文における関連研究の執筆支援のための被引用論文の推定**<br>
[**[小山 et al, 言語処理学会, 2021]**](#nlp2021pred_ref_paper)



関連研究の文章と引用関係の情報を用いて、どの論文を引用すべきか割り当てるタスク(引用文献割り当てタスク)と引用元論文と非引用論文のペアが適切であるかどうかを判定するタスク(引用文・被引用文献ペア適正性判定タスク)を行った. 引用文・被引用文献ペア適正性判定タスクでは、引用部分の文章と被引用論文のabstractをペアで学習させて正例である確率を出力する. 引用文献割り当てタスクでは関連論文をいくつか並べた際にどの論文が引用する論文として適しているかを出力する(下図). どちらもBERTやXLNetなどの言語モデルでAccuracy0.8程度の精度を出した.関連研究を引用する時に数多くの論文を調査する労力を削減することを大きな目的としていて、自分の目指している方向と近い(気がする).

<img width="232" alt="image" src="https://user-images.githubusercontent.com/69502527/214764563-ca32c522-fa0a-43c3-89e2-db9518f8e36d.png">

* * *
## 【2023/01/26】**材料科学論文の表の意味解釈データセットの構築**<br>
[**[加藤 et al., 言語処理学会, 2022]**](#nlp2022naist_create_dataset)



材料科学論文の表に記載されている物性や単位の検出とリンキングを行った. まずモデル構築のため、高分子論文集の論文約200本に含まれる表に対してアノテーションを行い、データセットを構築した. そして系列ラベリング、辞書マッチングを組み合わせた解析を行った. 正直な話、材料科学の話だったからか何をしているか分からない場面が多く、自分の言葉でまとめるのは難しかった.
> 日々多数出版される科学技術論文の全てを人手で読解する事は物理的に不可能であるため,論文から自動で情報抽出を行う技術の研究開発が求められる.

という文章に強く共感する. また、そのために様々な情報が含まれている表からの情報抽出に取り組むといった考え方も良い.
* * *

## 【2023/01/27】**Scientific Paper Recommendation: A Survey**<br>
[**[Xiaomei et al., IEEE, 2019]**](#SPR_survey)



Scientific Paper Recommendationに関してのサーベイ論文. 論文推薦に使われている推薦手法のContent-Base Filtering(CBF), Collaborative Filtering(CF), Graph-Based Method(GB), Hybrid Method(HM)の4つを利点、欠点を挙げながら簡単に解説している. その後に評価指標に関して解説し、最後に論文推薦システムの問題点をいくつか挙げている. 推薦アルゴリズムを解説している際、対象は既にいくつかの研究を行っている研究者に対しての推薦であり、これから研究をしたい学生などにとっては用いることができなそうなアルゴリズムだった. そこに関してはCOLD STARTという問題点として、「新規ユーザー、新規論文にとって上手く作用しない」と説明している. また、論文数が指数関数的に増えている現在の問題点としてSCALABILITYを挙げている. (Acceptされたのが2019で論文を出したのは2018だからか)本論文では深層学習を用いた推薦システムの解説がなかったため、現在ではこの問題点を解消しているのか気になる. Introductionが面白くて特に
> In academic research, recommender systems can provide papers for researchers and helps them quickly find the papers they need.

などは自分がやりたいことに近いと感じた.
* * *

~~言い訳ですが、就活のため期間が開きました~~

## 【2023/02/11】**Overview of the Third Workshop on Scholarly Document Processing**<br>
[**[Cohan et al., sdp, 2022]**](#ACL_sdp_overview)

タイトルの通り、the Third Workshop on Scholarly Document Processing(SDP)の概要を述べている. 基調講演3つの概要、NLP, 情報検索などの利用方法と課題、Shared Taskの紹介を主に行っている. 論文って感じでもない. Shared Taskってものがあるのか、という感じだ. Scholarly Document Processingという分野を知れた(一番知りたかったやつ)ので収穫.


* * *
~~就活中のため一時中断していました~~
## 【2023/3/13】**論文の階層構造を活用した被引用数予測**<br>
[**[hirako et al. 言語処理学会, 2023]**](#nlp2023_paper_pred)
被引用数の予測では、abstractを用いて本文の情報が活用されていないことが多い. この論文では、被引用数予測において本文を有効に活用することを目指し、論文の階層構造を活用した手法で行っている. 論文は文字数が多いため、Transformerベースのモデルに全文突っ込むと計算量が多いという問題点がある. この問題に関して、`Transformer自体の改善`と`入力する長い系列を分割して処理することで、計算量の増加を抑える`という主に2つのアプローチがある. 今回提案されている階層構造の概要は下図のようになっている. 階層構造(先頭)では、各節の見出しを一文目、内容を二分目としてBERTに入力し、セクション表現を生成. 階層構造(分割)では、各節の内容を50トークンずつオーバーラップさせながらチャンクに分割し、それぞれを用いてBERTでエンコードし、チャンク表現をMean Poolingする. このモデルを用いて一年後の被引用数を予測するタスクに取り組んだ結果、BERT(title+abstractを入力)を上回り、本文を活用する有用性が示された.



<img width="270" alt="image" src="https://user-images.githubusercontent.com/69502527/224657621-c5d9c72e-f99d-42e4-9c76-324835180ff6.png">


* * *

## 【2023/03/19】**文分類問題における精度と解釈性向上のための近傍事例の活用**<br>
[**[muraoka et al., 言語処理学会, 2023]**](#nlp2023_XAI_knn)






* * *




# References
<a name='IPSJ-CH11090006'></a>[1] Yuichiro Kobayashi, Shosaku Tanaka, &Yoichi Tomiura. Classification and Assessment of English Scientific Papers Using Random Forests. In IPSJ, 2011.

<a name='nlp2022pdftodataset'></a>[2] 小林恵大, 小山康平, 成松宏美, &南泰浩. 学術論文PDFからの関連研究章と引用情報の抽出による論文執筆支援のためのデータセット構築. In 言語処理学会 第28回年次大会 発表論文集, 2022, 03.

<a name='nlp2021pred_ref_paper'></a>[3]小山康平, 南泰浩, 成松宏美, 堂坂浩二, 東中竜一郎, 田盛大悟, &平博順. 学術論文における関連研究の執筆支援のための被引用論文の推定. In 言語処理学会 第27回年次大会 発表論文集, 2021, 03.

<a name='nlp2022naist_create_dataset'></a>[4] 加藤明彦, 近藤修平, 進藤裕之, &渡辺太郎. 材料科学論文の表の意味解釈データセットの構築. In 言語処理学会 第28回年次大会 発表論文集, 2022, 03.

<a name='SPR_survey'></a>[5] Xiaomei Bai, Mengyang Wang, Ivan Lee, Zhuo Yang, Xiangjie Kong, and Feng Xia. 2019. Scientific paper recommendation: A survey. IEEE Access, 7:9324–9339.

<a name='ACL_sdp_overview'></a>[6] Arman Cohan, Guy Feigenblat, Dayne Freitag, Tirthankar Ghosal, Drahomira Herrmannova, Petr Knoth, Kyle Lo, Philipp Mayr, Michal Shmueli-Scheuer, Anita de Waard, and Lucy Lu Wang. 2022. Overview of the Third Workshop on Scholarly Document Processing. In
Proceedings of the Third Workshop on Scholarly Document Processing. Association for Computational Linguistics, Gyeongju, Republic of
Korea, 1–6. https://aclanthology.org/2022.sdp-1.1

<a name='nlp2023_paper_pred'></a>[7] 平子潤, 笹野遼平, 武田浩一, 論文の階層構造を活用した被引用数予測. In 言語処理学会第29回年次大会 発表論文集. 2023, 3.

<a name='nlp2023_XAI_knn'></a>[8]村岡雅康, 趙陽, 文分類問題における精度と解釈性向上のための近傍事例の活用, In 言語処理学会第29回年次大会 発表論文集. 2023, 3.
