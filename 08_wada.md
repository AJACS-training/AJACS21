[[AJACS21]]

&size(25){R/Bioconductorを使った遺伝子発現解析～導入と解析例～};　　担当：和田智


~目次
#contents

# [[&size(20){Rとは};>http://www.okada.jp.org/RWiki/?RjpWiki]] [#nfd15452]
&color(green){フリーウェアでオープンソースのデータ解析環境};
- データの操作や計算、可視化のためのソフトが統合されたもの
- 最新の解析手法のパッケージが公開・更新され、サンプルデータも豊富
- 対話的に実行可能
- Windows, MacOSX, UNIXとマルチプラットホームで動作

# [[&size(20){&#66;ioConductorとは};>http://www.bioconductor.org/]] [#k90d3923]
&color(green){生命科学分野のためのRパッケージプロジェクト};
- マイクロアレイデータなどの遺伝子発現プロファイルや質量分析データ、タンパク質相互作用データなどの解析パッケージ集

#  R/&#66;ioConductor の導入 [#g1423ef7]
## 【実習】R/&#66;ioConductorのインストール [#dd8bbf80]
- [[【参考動画】>http://togotv.dbcls.jp/20090313.html#p01]]http://lifesciencedb.jp/image/small_video_icon.png
+ [[http://cran.r-project.org/bin/windows/base/>http://cran.r-project.org/bin/windows/base/]]を開きます。
+トップにある[[「Download R 2.11.1 for Windows」>http://cran.r-project.org/bin/windows/base/R-2.11.1-win32.exe]]をクリックして、インストーラ（R-2.11.1-win32.exe）をダウンロードします。<br>
+ インストーラのダウンロードが完了したら、インストーラを実行します。
    -言語は日本語でOKのはずですが、インストールの途中で文字化けした場合、一度インストールを中止し、言語をEnglishにしてやり直してください。<br>
1.「Startup Option」のところで「Yes (customized startup)」を選んでください（コンポーネント選択の次の画面）<br>
2.　最初の二つはそのままでOK<br>
3.「Internet Access」のところで、プロキシ接続が必要な場合（企業や学校からつなぐ場合に必要となることがあります）は「Internet2」を選択します。<br>
4.　あとはそのままで全部OK<br>
+ インストールが完了すると、デスクトップに"R 2.11.1"のアイコンが作成されます。
+ アイコンをダブルクリックし、Rを起動します。<br>
+ Bioconductor の一括インストール<br>
1.
 source("http://bioconductor.org/biocLite.R")
と打ち込んでリターン<br>
2.
 biocLite()
と打ち込んでリターン<br>
3.
でインストールが始まります。<br>
<br><br>

+さらに必要なパッケージのインストールを行います。<br>
1. R 上部のメニューから「パッケージ」→「ダウンロードサイトの選択」を選択します。<br>
2. 「BioC annotation」を選んで OK<br>
3. R 上部のメニューから「パッケージ」→「パッケージのインストール」を選択します。<br>
4. Ctrlを押しながら、「hgu133plus2cdf」と「hgu133a.db」を選択して OK<br>
<br><br><br><br><br>


#  R/&#66;ioConductor を用いた解析例 [#k24eccfd]
## 【実習】R/&#66;ioConductorを用いたマイクロアレイデータの正規化 [#gf9cb857]
- [[皮膚の線維芽細胞からiPS細胞を作製したときのデータ>http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE18226]]を使用します。<br>
GEOに一斉にアクセスすると良くないので、生データは　http://bit.ly/sampledata　に置いてあります。<br>
- マイクロアレイの生データの取得方法については統合TVの[[NCBI Gene Expression Omnibus (GEO)からマイクロアレイの生データをダウンロードする方法>http://togotv.dbcls.jp/20081218.html#p01]]を参照してください。

        --

- [[【参考動画】>http://togotv.dbcls.jp/20090319.html#p01]]http://lifesciencedb.jp/image/small_video_icon.png
<br><br>
1. Rを起動します。<br>
2.「ファイル」の「ディレクトリの変更」をクリックして、マイクロアレイデータ（CELファイル）のあるフォルダを選択します。初期値のままならば「GSE18226_RAW」というフォルダです。<br>
3.
 library(affy)
と入力し、解析パッケージを読み込みます。<br>
4.
 write.exprs(justRMA(), file="RMA_expression.txt")
と入力します。少々時間がかかりますが、しばらくそのままで待ちます。何もエラーメッセージが出なければ、RMAで正規化されたデータがタブ区切りのテキストファイル（RMA_expression.txt）として保存されます。<br>
5.
 write.exprs(mas5(ReadAffy()), file="MAS5_expression.txt")
と入力します。MAS5による正規化はRMA以上に時間がかかると同時に、大量のメモリを消費するのでマシン環境によってはエラーが出ることがあります。同様に何もエラーが出なければ、MAS5で正規化されたデータがタブ区切りのテキストファイル（MAS5_expression.txt）として保存されます。<br>
6.
 write.exprs(mas5calls(ReadAffy()), file="MAS5calls_expression.txt")
と入力します。MAS5の Present / Absent コールがタブ区切りテキスト（MAS5calls_expression.txt）で保存されます。


## 【実習】R/&#66;ioConductorを用いた発現変動遺伝子（マーカー遺伝子）の抽出 [#i0ba8631]

- 今回の解析では前立腺癌細胞と正常細胞のデータセット「[[GSE12348>http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE12348]]」をRMAで正規化した発現データを使います。<br>
#ref(gse12348_rma.txt)<br>
をダウンロード（右クリックして「名前を付けてリンク先を保存」してください）し、先程使った「GSE18226_RAW」というフォルダに入れます。「ファイル」の「ディレクトリの変更」をクリックして、「GSE18226_RAW」フォルダを選択します。<br>
1.
 data <- read.table("gse12348_rma.txt", header=T, row.names=1)
と入力し、データを読み込みます。<br>
2.
 data[1:5,]
と入力すると、5行目までのデータを見ることができます。CA1-6が癌細胞、NEとNSが正常細胞です。<br>
3.
 mean_ca <- rowMeans(data[,c(1:6)])
 mean_n <- rowMeans(data[,c(7:9)])
と打ち込み、癌細胞と正常細胞群、それぞれの発現値の平均値を計算します。<br>
4.
 dif <- mean_ca - mean_n
平均した発現量の比を計算します。<br>
RMAで正規化した場合、発現値はlog2対数変換されていますので、log2（癌細胞/正常細胞）はこのような計算式になります。<br>
5.
 sum(dif > 2)
とすると、4倍以上高発現しているプローブ数が分かります。今回の解析ではこれらのプローブから更にt検定によって候補を絞り込みます。<br>
6.
 library(genefilter)                           #必要なパッケージの読み込み
 dif_list <- dif[dif > 2]                      #前準備
 dif_data <- as.matrix(data[names(dif_list),]) #前準備
 label <- c(0,0,0,0,0,0,1,1,1)                 #前準備
t検定のための準備です。<br>
7.
 tt <- rowttests(dif_data, factor(label)) #t検定の実行
 p_value <- tt$p.value
 names(p_value) <- names(dif_list)
このように打ち込むと、高発現している候補遺伝子全てに対してt検定を行い、そのp-valueを取り出すことができます。<br>
8.
 p_value_b <- p_value * length(p_value)   #補正
 p_value_sig <- p_value_b[p_value_b<0.05] #p<0.05のプローブを抽出
これで、癌細胞で有意に高発現しているプローブの抽出ができました。
 p_vslue_sig
と入力すると、結果が出ます。<br><br><br>
### レポートの作成 [#h167d748]
- 文献などから情報を得たり、更に解析を進めるために、抽出したプローブにアノテーションを付ける必要があります。そこで
 library(annaffy)                                       #必要なパッケージの読み込み
 report <- aafTableAnn(names(p_value_sig),"hgu133a.db") #アノテーションを付加
 saveHTML(report, "report.html")                        #html形式でレポートを作成
このように入力することでレポートを作成することができます。
    -さまざまなデータベースのリンクから、情報を得ることができます。


## その他のマイクロアレイデータ解析 [#w7f833b3]
- [[東京大学大学院農学生命科学研究科の門田幸二さん>http://www.iu.a.u-tokyo.ac.jp/~kadota/]]が自身のHPで公開されている「[[(Rで)マイクロアレイデータ解析>http://www.iu.a.u-tokyo.ac.jp/~kadota/r.html]]」が非常に有用です。<br>
- コピペで結果が出せるよう書かれていることに加え、それを実行できるサンプルデータも用意されていますので、このページを参考にしつつ、自分のやりたい解析をやってみましょう。


        --
