[[講習会のページに戻る>AJACS21]]

&size(36){次世代シーケンサの活用法/データの解析法 };
        --
~目次
#contents
        --
#  はじめに [#l06694f4]

> 勇をたのみにがむしゃらに相手を選ばず戦っている。
>これは弱冠の者の行為である。
> 強い相手を避け、弱い者を選んで戦い、進退のツボを心得る。
> これは壮年にならなければ出来ぬことだ。

##  アンケート [#raeddd42]
- すでに次世代シーケンサーからのデータ解析やっている: 3

//- すでに新型シーケンサーのデータがあって困っている：
//- これから新型シーケンサーのデータが出てくる予定がある：
//- 新型シーケンサーを使ってみたい：
//- 使う予定はない：

##  これまでの新型シーケンサー応用例 [#u5c5c8d7]
- Whole Genome Shotgun(WGS): ゲノム配列解読
- resequence: 個体差(DNA配列)
- RNA-seq: 遺伝子発現(RNA or cDNA配列)
- ChIP-seq: 転写因子結合配列
- epigenome: メチル化されたDNA配列

// [[実際にSRAではどうなっているの？>http://tswp.dbcls.jp/SpotfireWeb/ViewAnalysis.aspx?file=/SRA/SRA201005]]

##  サンプル [#jb229bab]
- 一種類の生物種
    - ゲノム配列有・ゲノムアノテーション有：ヒトや有名モデル生物（マウス、ラット、ショウジョウバエなど）~
ゲノムマッピング→既存ゲノムアノテーション（RefSeq）と比較
    - ゲノム配列有・ゲノムアノテーション無：ブタとかカイコとか~
ゲノムマッピング→近縁種のゲノムアノテーションと比較~
    - ゲノム配列無・ゲノムアノテーション無~
unigene作るのと同じようにMEGABLAST
- メタゲノム（複数の生物種が混在）~
既知の配列すべてに対して配列類似性検索

##  戦術 [#s3d41426]

&size(30){基本的にはこれまでの大量DNA配列解析と同じ→「これまで」のレベルに持って行くところをまずやる};

- ゲノムマッピング(Reference Genome Mapping)~
それぞれの断片がゲノム中のどこに由来するものか、マッピングする。
- de novo assembly~
先見的な知識なしに解読した配列をつなぎ合わせる(assembly)。
- ゲノム（遺伝子）アノテーションと比較~
新しいものかどうかは、これまで分かっているものと比較しないと不可能。そのためには、ちゃんとアノテーション（キュレーション）されたリファレンスが必要。

##  解析ツールの現状 [#p2465e28]
- ウェブ上で動くフリーのものは鋭意開発中。それを以下で紹介。
- 共同研究環境としてGalaxyが使える（かも）
[[NGS Analyses in Galaxy>http://main.g2.bx.psu.edu/u/aun1/p/ngs-analysis-service]]
- 有償のソフトも出てきているようです（例えば、[[GenomeQuest>http://www.digital-biology.co.jp/j_product_detail.html?product_id=120]]）。
- Rでデータ解析する方法が東京大学 大学院農学生命科学研究科 アグリバイオインフォマティクス教育研究ユニットの門田幸二さんによって公開されています
    - [[(Rで)塩基配列解析（主に次世代シーケンサーのデータ） by 門田幸二>http://www.iu.a.u-tokyo.ac.jp/~kadota/r_seq.html]]
- ローカルで動くフリーなツールは多数開発＆公開されているので、それらを組み合わせて配列解析することはやる気さえあれば可能。DBCLSでは実際にResearch Assistantさん（それがメインの研究テーマではない大学院生）に技術開発をやってもらっています（統合牧場技術開発部）。
    - [[遺伝子発現情報を使い倒す～Transcriptome Sequenceによる遺伝子発現解析の実際～>http://togotv.dbcls.jp/20100709.html]] http://lifesciencedb.jp/image/small_video_icon.png
    - [[Chateau Togo>http://g86.dbcls.jp/~iNut/chateautogo/]]
    - [[Wolf Ears>http://g86.dbcls.jp/~yag/wordpress/]]

#  [[DDBJ Read Annotation Pipeline>http://trace.ddbj.nig.ac.jp/dra/index.shtml]]の使い方 [#xc707653]

- [[今日からはじめるDDBJ Read Annotation Pipeline>http://togotv.dbcls.jp/20100617.html]] (Reference Genome Mapping) http://lifesciencedb.jp/image/small_video_icon.png

1. [[統合データベースプロジェクトページ>http://lifesciencedb.jp/]] の「アーカイブ」にある[[DDBJリードアーカイブ>http://trace.ddbj.nig.ac.jp/dra/index.shtml]]をクリック<br>
2. 「解析パイプラインでデータを解析」もしくは上部にある「Pipeline」タブをクリック<br>
3. User ID: guest    Passwordは空白でログインできます<br>
4. まず、解析する配列ファイルを指定します。DRA (DDBJ Read Archive)に登録済みの場合はリストから選択、登録していない場合はファイルをアップロードします<br>
　1. DRAを指定した場合、データのメタデータ（サンプル名や実験条件など）が表形式で表示されます。データのダウンロードや閲覧が可能です<br>
　2. 解析に使用する配列データは一番下のテーブルから選択します<br>
5. 解析に使用するツールを選択します。ツール名はツールのオリジナルサイトにリンクされています。「Help」にあるアイコンをクリックするとそれぞれのツールのヘルプが表示されます<br>
　1. 既にゲノムが解読されている配列にマッピングする場合には「Reference Genome Mapping」を、新規にアセンブリする場合には「de novo Assembly」を選びます<br>
　2. 使用するツールにチェックを入れて「NEXT」<br>
6. 解析に使用するリード長を決定します<br>
　1. 「Quality Score」のボタンをクリックすると、配列セットのQualityスコアが表示されます<br>
　2. サンプルと（必要があれば）解析するリード長を指定して「confirm」をクリックします<br>
　3. 複数のサンプルがある場合には、それぞれのサンプルについて配列長を指定できます<br>
　4. 解析するすべてのサンプルを「confirm」したら、「NEXT」<br>
7. マッピングする場合、リファレンスとなるゲノムを指定します（de novo Assemblyの場合にはこの過程はスキップされます）<br>
　1. Majorな生物についてはあらかじめ登録されている中から選択します<br>
　2. リストにない場合には、ゲノム配列のIDを指定して配列をダウンロードします<br>
8. 解析プログラムのパラメータを指定します<br>
9. 解析終了のお知らせを受け取るメールアドレスを入力します（必須）。今回はゲストアカウントなので解析は実行できませんが、実際には「BACK」の右側に「RUN」ボタンがあります<br>
10. 左側にある「MENU」の「STATUS」から、解析の実行状況について確認できます<br>
11. 実行結果から、リファレンス配列（Chromosome）とMapping結果ファイル（out.sam、下から3番目）をダウンロードし、[[Tablet>http://bioinf.scri.ac.uk/tablet/]] などのViewerで結果を表示できます（ファイルサイズが大きいため、今回は省略します）

# [[MiGAP>http://migap.lifesciencedb.jp/]] の使い方 [#re46b80f]
- [[MiGAPの使い方～導入と基本操作～>http://togotv.dbcls.jp/20100624.html#p01]] http://lifesciencedb.jp/image/small_video_icon.png

1. [[統合データベースプロジェクトページ>http://lifesciencedb.jp/]]の「ツール＆解析サービス」にある[[MiGAP>http://migap.lifesciencedb.jp/]]をクリック<br>
2. 左上のバナーをクリック<br>
3. 「Login」からOpenIDでログイン<br>
4. 「Pipe Line」にアセンブリ済みの配列を アップロード or ペースト (Sample data をクリックすると入力ボックスにサンプル配列が入力される)<br>
5. 入力した配列が「直鎖状」か「環状」か、「真正細菌」の配列か「アーキア」の配列かを選ぶ<br>
6. 「Run」で計算開始<br>
7. 計算状況は「Current Process」から確認できます<br>
8. 「Change User Level」でユーザレベルを変えられます。Bronze = 初心者（すべてお任せ）、Silver = 中級者（プログラムのパラメータを自分で設定可能）、Gold = 上級者（解析プログラムを組み込んだりできるらしい）<br>
9. 計算が終了すると、「Pipe Line History」から結果を見ることができます<br>
　1. フォルダをクリックすると解析のサマリーと、各種ファイルのダウンロードリンクが表示されます（-a の付いているファイルがアノテーション付きの結果ファイル）<br>
　2. ゲノムマップ上をクリックすると、その部分が拡大される。矢印をクリックするとORFの詳細が表示される（chrome ではORFの詳細が表示されない。FireFoxはOK）<br>
　3. 例えば「result-aa.fasta」「result.csv」「result-a.csv」をダウンロードして中身を閲覧<br>

#  おわりに [#raba4acb]
> 大事の義は、
> 人に談合せず、
> 一心に究めたるがよし。
