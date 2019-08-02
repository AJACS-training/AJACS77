
# 統合データベース講習会：AJACS番町3 <br>- jPOST の使い方 -
情報・システム研究機構
データサイエンス共同利用基盤施設
ライフサイエンス統合データベースセンター  
守屋 勇樹 moriya@dbcls.rois.ac.jp  
2019/08/07 JST

---
## 講習会の流れ  

今回の講習会では、ウェブブラウザを使って jPOSTdb の操作を行うことで、データベースの使い方を練習していきます
- 概要
  - jPOSTdbの概要
  - データのしぼりこみ
  - データセットページの概要
  - タンパク質ページの概要
  - Slice(データセットグループ)を作成してみる
  - ２つのSliceを比較してみる

---
#### 講習に際しての注意とお願い

- みんなで同じ回線を使って同時にアクセスするとサイトにつながりにくくなることが予想されます。
  - 資料を見ながら自力で進められそうな方はどんどん先に、そうでない方は一緒にすすめていきましょう。
  - サイトの反応が悪い時はタイミングをずらして実行してみてください。
  - 反応が無いからと言って何度もクリックするとますます繋がらなくなってしまいます。おおらかな気持ちで臨みましょう。
- わからないことがあったら挙手にてスタッフにお知らせください。
  - 遠慮は無用です(そのための講習会です!)。おいてけぼりは楽しくありません。
- 今回のコースでは一応Google Chromeを推奨しますが、Firefox、Safari、Edge、Operaなどのモダンブラウザでも問題ないと思います。動かなかったら今後の課題に加えますので教えて下さい。ただしInternet Explorerは古すぎるので動作を保証していません。モバイル機器での操作。動作も一部未対応です。
---
## jPOSTdbとは
jPOSTdbは質量分析に基づくプロテオームデータを"再解析"をし、その結果を収録したデータベースです。

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpost.png)

jPOSTrepに登録したデータを直接見れるわけではありません。

jPOSTdbの特徴
- データセット毎にプロテオームデータを俯瞰できます
  - Missing Protein探索やKEGG Pathwayへのマッピングができます
- タンパク質毎に同定されたペプチドやPTM、isoformの情報を見ることができます
- 興味のあるデータセット複数を切り出して、データを俯瞰できます（Slice）
- 簡易的なツールを用いてSlice間の比較を行うことができます

---
## [jPOSTdb webサイト](https://globe.jpostdb.org/)

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_01.png)

- Topページ
  - 最初に、データベースに入っているデータセットの生物種の割合を示したチャートが出ます
    - マウスカーソルをホバーさせることで、詳細が表示されます
  - 下にはデータセットのリストテーブルが表示されます
    - 2019/8/7時点で103データセットが収録されています
    - "DS59_1" というのがjPOSTdbでのデータセットのIDになっています
  - 上のpie chartのある部分はデータセットの絞り込みを行うフォームになっています

---
## データセットを絞り込んでみよう
- 例えばhumanで絞りこみをしてみましょう
  - テキストエリアをクリックすると候補が表示されます。クリックで選択されます
  - pie chartをクリックすることでも選択できます

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_02.png)

- テーブルのリストが66データセット、14,620タンパク質に減りました
- 生物種以外に、Sample type、Cell line、Organ、Disease、Mofdification、Instrumentで絞り込みが行なえます
- "+" ボタンをクリックすることで、複数のカテゴリで絞り込みを行うことができます

---
## データセットを検索してみよう
- 一旦全部の絞り込みを外しましょう
- テーブルの上にワード検索Boxがあります。キーワードに関連したデータセットが検索されます
  - データがまだ少ないので、今回は"fibroblast"で検索します

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_03.png)

- 9つのデータセットが引っかかり、5,711タンパク質が収録されていました

---
## データセットの中身を見ていこう
- テーブルの "DS87_1" をクリックしてデータセットDS87_1の中身を表示しましょう

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_04.png)

- データセットのメタデータがまとめられたテーブルが表示されます
- Project ID、Project title、Project descriptionはリポジトリに登録したときのものが表示されます
- Sampleの情報、統計情報、データをまとめてDLするリンクがあります

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_05.png)

- 同定されたタンパク質の染色体毎の数を表示しています
  - UniProt IDベースのカウントになるので、遺伝子数とは厳密には異なります

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_06.png)

- Protein existenceのレベルの内訳を表示しています
  - ヒトはneXtProtに基づいており、それ以外の生物種はUniProtのデータに基づいています
  - それぞれのタンパク質のリストを見ることができます

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_07.png)

- データセットのタンパク質をKEGG Pathwayにマッピングすることができます

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_08.png)

- 色はスペクトルカウントに基づいた色になっており、青が少なく、赤が多いことを意味しています

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_09.png)

---
## タンパク質をみてみよう
- ページ一番上の"Search"からTopの検索画面に戻れます
- テーブルを"Dataset"から"Protein"に切り替えます
- 表示されるデータの都合が良いので、今回は"BCLF1"で検索します

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_10.png)

- ヒトとマウスでタンパク質が引っかかりました
- Protein nameをクリックするとタンパク質ページに以降します。今回はヒトのBCLF1を見てみましょう

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_11.png)

- タンパク質の情報テーブルを表示しています
- ヒトのタンパク質の場合iMPAQT へのリンクがあります

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_12.png)

- タンパク質ブラウザを表示しています
  - スクロール操作で拡大縮小できます
- プルダウンメニューから幼児する情報を追加できます
  - Peptide: 検出されたペプチドのマッピング（Default）
    - 赤は同定数の多いペプチドを示しています
  - Phospho site: リン酸化部位
    - 軸の長さは検出された量を、そのポジションをカバーしているペプチドの数で補正した割合を示しています
    - "count" ボタンをクリックすると実数に変わります
  - P-site linkage: リン酸化部位のペプチド上での共起情報
  - UniProt annotation: UniProtに収録されている既知の修飾情報

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_13.png)

- isoform間、タンパク質間のペプチドの共有情報を表示しています
  - 同じ色のBoxが同一のペプチドになります

---
## Sliceを作ってみてみよう
- Sliceとは、データベースからユーサの興味のあるデータセットを切り出した、データベースのサブセットです
- iPS細胞のデータセットでSliceを作ってみよう
  - Topの検索ページで"iPS cell"でデータセットを検索します

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_14.png)

- テーブルの下にある"New Slice..."ボタンをクリックします

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_15.png)

- Slice作成画面に移動します
  - この画面でも絞り込み検索が可能です
  - わかりやすい名前をつけ、必要なら説明を入れましょう
- 今回はテーブルの上の３つDS81_1, DS81_2, DS81_3でSliceを作ります
  - ３つのチェックボックスにチェックを入れます
- "Add"ボタンをクリックすると、Sliceが作成されます

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_16.png)

- 選択したデータセットをまとめた情報が表示されます
  - 見方はデータセット毎のページと同様です

---
## Slice同士を比較してみよう
- jPOSTdbではSlice同士を比較する簡易な解析機能がついています
- もう一つ"fibroblast"でSliceを作成します
  - Sliceページのタブに並んでる"+"マークからも新規Sliceが作成できます

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_17.png)

- 2つのSliceを比較します
  - タブにあるチェックボックスをチェックして”Compare"ボタンをクリックします

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_18.png)

- 比較ページに移動します

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_19.png)

- 統計情報が表示されます
- また、簡易的な変動解析をすることができます
  - 現時点では定量データをあまり収録していないので、スペクトルカウントを補正して半定量をしています
    - スペクトルカウントはタンパク質に紐付いたスペクトルの数のことです
  - 今回は"Empirical Bayes estimation"を使います
    - Wilcoxon rank sum testはサンプル数が多いときによく使われます
    - Empirical Bayes estimationは比較的少ないサンプル数でも比較が可能です
    - Fold change of the meanは統計処理はしないので１サンプルでも比べられます

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_20.png)

- Volcanoプロットがj表示されます
  - 各プロットがタンパク質になります
  - 横軸がFold changeを示し、縦軸はp-valueになっています
  - 左（青）が発現量が低下したタンパク質、右（赤）が上昇したタンパク質を示しています
    - 青と赤で示されたプロットが有意な変動が見られたタンパク質ということになり、下のテーブルにリストが表示されています
    - Thresholdはユーザがバーを移動させることで変えられます
  - プロット左にある"both"ボタンをクリックすることで上昇したものだけ、下降したものだけを表示することもできます
  - Fold change of the meanの場合はヒストグラム風のプロットになります

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_21.png)

- 選択した有意な変動の見られたタンパク質リストを用いて、エンリッチメント解析を行うことができます
  - KEGG Pathway, GO, ChIP-Atlasなどを用いて解析ができます
  - 今回は"KEGG Pathway"のカテゴリでエンリッチメント解析をしてみましょう

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_22.png)

- ネットワークグラフが表示されます
  - 各ノードがカテゴリを示しています
  - ノードのサイズがカテゴリのタンパク質数を示しています
    - 白いノードはサイズの上限を設定しているので、色付きノードより大きく表示されません
  - 黄色からオレンジ色のノードはエンリッチしているカテゴリを意味しています
    - 色の濃いノードがとりエンリッチしています
- jPOSTdbは[ChIP-Altas](https://chip-atlas.org/)と連携しており、ヒトをはじめ、いくつかの生物種ではjPOSTdbで変動解析した結果をChIP-Atlasの解析フォームを用いてエンリッチメント解析ができます

![jpost](https://raw.githubusercontent.com/moriya-dbcls/jPOSTdb/master/2019/images/jpostdb_23.png)

