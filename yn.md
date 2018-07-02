[[講習会のページに戻る>AJACS21]]

&size(36){DDBJのNGSデータアーカイブ<br>DRA (DDBJ Sequence Read Archive)};
        --
~目次
#contents
        --

# 自己紹介 [#q8377e40]
- 44歳。木更津市／三島市在住。
- こんな人です。
    -http://charles.genes.nig.ac.jp/members/yn/
    -http://catlover.xrea.jp/d/
    -http://twitter.com/yaskaz

京大→遺伝研→かずさ→遺伝研DDBJ移動しながらと「ゲノム」と「情報」を扱ってきています。

#  DNA Data Bank of Japan (DDBJ) [#u7eb9dc8]

International Nucleotide Sequence Database Collaboration  (INSDC) のメンバー

- GenBank: http://www.ncbi.nlm.nih.gov/genbank/ (NCBI: http://www.ncbi.nlm.nih.gov/)
- ENA: http://www.ebi.ac.uk/ena/ (EBI: http://www.ebi.ac.uk)
- DDBJ: http://www.ddbj.nig.ac.jp/

#  新型シーケンサ [#a95a2dbd]

Next or New Generation Sequencer (NGS)

- 原理@youtube
    - マイクロビーズや固体担体を用い、DNA増幅(PCR)反応を超高密度化
    - 配列の解読は、固定した担体上で同時並行で行い、反応に伴う微細な発光をデジタルカメラで取得、時系列に同じスポットの発光を並べることで一度に数百万以上の配列決定を同時進行

> http://www.youtube.com/watch?v=kYAGFrbGl6E (Roshe 454)
> http://www.youtube.com/watch?v=77r5p8IBwJk (illumina)
> http://www.youtube.com/watch?v=nlvyF8bFDwM (ABI SOLiD)

##  NGSが可能にしたプロジェクトの例 [#u80a11d0]
- 1000ゲノム: http://www.1000genomes.org/
- 1001ゲノム: http://1001genomes.org/

#  DRA: 日本のNGSデータアーカイブです [#y0109e81]
- Sequence Read Archive (SRA): http://www.ncbi.nlm.nih.gov/sra
- SRA in ENA: http://www.ebi.ac.uk/ena/about/page.php?page=sra_submissions
- DRA (DDBJ SRA): http://trace.ddbj.nig.ac.jp/dra

##  DRAへの登録 [#p8b25b32]
- 日本語による説明: http://trace.ddbj.nig.ac.jp/dra/submission.shtml
- メタデータ（XML）とランデータ（配列関係データ）をセットで登録する形態
- 登録のためのインタフェイスD-wayから入ります
- メタデータはXMLで記述します。支援システムを用意しています
    -メタデータ作成システム（Flash版）:  https://trace.ddbj.nig.ac.jp/tools/contents/metaDefine
    -メタデータ確認システム: https://trace.ddbj.nig.ac.jp/tools/contents/metaChecker
- ランデータは一次データと配列データとで構成されます
    -登録するランデータはNGSの機種によって異なります
- 国際協力により、日米欧のデータはミラーされ、交換されています（いまのところ...）

##  DRAへの登録支援 [#u70c48de]
DRA pipeline (後述): http://p.ddbj.nig.ac.jp/ <br>【統合TV】「今日からはじめるDDBJ Read Annotation Pipeline」http://togotv.dbcls.jp/20100617.html

## 参考 [#l876ae73]
現在募集中の新学術領域研究「ゲノム研究分野支援」 http://www.genome-sci.jp/  で支援された解析情報は、公開可能なデータはすべてDRA, DDBJへ登録、公開していただくことになっています。皆様のデータ登録を楽にするための開発も鋭意すすめていきます。よろしくお願いします。
