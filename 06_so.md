[[AJACS21]]

        --
目次

#contents
        --
#  ゲノム情報の可視化 [#rb06956a]
##  Cytoscapeとは [#o39ff2f1]
- Cytoscapeは、グラフ（ネットワーク）の可視化と解析のためのオープンソース・プラットフォームです
    - [[Cytoscapeプロジェクト公式ページ:http://www.cytoscape.org/]]
    - [[Cytoscape Web:http://cytoscapeweb.cytoscape.org/]]
    - [[Cytoscape Wiki:http://cytoscape.wodaklab.org/wiki/]]
    - [[Cytoscape公式日本語Wiki:http://cydoc.sourceforge.jp/cydocwiki/index.php?Cytoscape%20Japanese%20Documentation%20Project]]
    - そのほかのグラフビューア [#od9720c0]
        - [[Graphviz:http://www.graphviz.org/]]
        - [[Pajek:http://vlado.fmf.uni-lj.si/pub/networks/pajek/]]

## 【実習1】Cytoscape Webを使って、ヒトのタンパク質相互作用のデータを表示してみましょう [#d2e5eec6]
+1. Cytoscape Wikiの[[Example Data Set:http://cytoscape.wodaklab.org/wiki/Data_Sets]]のRual et al. (Nature 2005 437 (7062):1173-8)のデータを使います。
+2. データ：RUAL.sifは、そのままだと大きすぎるので、今回は100個の相互作用に絞ったデータ：[[RUALsubset.sif:http://charles.kazusa.or.jp/~so/ajacs/RUALsubset.sif]]を使います。
+3. [[ここから:http://charles.kazusa.or.jp/~so/ajacs/]]RUALsubset.sifをローカルにダウンロードするか、適当なファイルとして保存してください。
+3. [[Cytoscape Web:http://cytoscapeweb.cytoscape.org/]]のページにアクセスして「[[View showcase demo:http://cytoscapeweb.cytoscape.org/demo]]」をクリックします。
+4. Open fileをクリックして、先程のデータRUALsubset.sifを読み込み、ヒトタンパク質のタンパク質相互作用を表示させます。
+5. Layout > Mechanism から、異なったグラフ配置のアルゴリズムを試してみましょう。
+6. Visual styleからデザインを変更してみましょう。


## 【実習2】様々なゲノムブラウザーを眺めてみましょう [#c2f85954]
- [[Ensembl:http://www.ensembl.org/index.html]]
- [[UCSC Genome Browser:http://genome.ucsc.edu/cgi-bin/hgGateway]]
- [[WormBase:http://www.wormbase.org/db/gb2/gbrowse/c_elegans/]]
    - [[GBrowse:http://gmod.org/wiki/Ggb/]]
    - [[WebGBrowser2.0:http://webgbrowse.cgb.indiana.edu/cgi-bin/uploadData]]
- [[UTGB:http://utgenome.org/medaka/]]
- [[IGB:http://www.bioviz.org/igb/]]
        --
#  参考資料 [#f02ddc53]

## 【参考1】光合成微生物の遺伝子と論文の関係を[[Cytoscape:http://www.cytoscape.org/]]で俯瞰する [#h2fb38af]
- http://charles.kazusa.or.jp/~so/ajacs/syn_allgenes_ajacs.cys：Cytoscapeで開くとレイアウトされた状態で見ることが出来ます。検索等も可能。
- http://charles.kazusa.or.jp/~so/ajacs/syn_allgenes_cyt.txt：syn_allgenes_ajacs5.cysを描画するための遺伝子-文献(言及頻度）の二項関係データ、Synechocystis全遺伝子
- http://charles.kazusa.or.jp/~so/ajacs/syn_path00195_cyt.txt：syn_allgenes_ajacs5.cysを描画するための遺伝子-文献(言及頻度）の二項関係データ、Synechocystis光合成関連遺伝子

## 【参考2】情報可視化関連ページ [#wd00edc4]
- Powers of ten
    - [[本家のページ:http://www.powersof10.com/]]
    - [[Powers of ten展覧会:http://www.calacademy.org/exhibits/powers_of_ten/]]
    - [[動画:http://vimeo.com/819138]]
- Deep Zoom
    - [[Seadragon:http://www.seadragon.com/]]
- 参考文献
    -[[Visualizing Data:http://www.amazon.co.jp/Visualizing-Data-Ben-Fry/dp/0596514557/ref=sr_1_1?ie=UTF8&s=english-books&qid=1280961053&sr=1-1]]
    -[[The Visual Display of Quantitative Information:http://www.amazon.co.jp/Visual-Display-Quantitative-Information/dp/0961392142/ref=sr_1_cc_1?ie=UTF8&qid=1280960866&sr=1-1-catcorr]]

## 【参考3】論文と遺伝子の関係性を俯瞰する：[[genoDive >http://genodive.org/]] [#vfefaf42]
- 我々のプロジェクトで開発している、ゲノムブラウザー。リアルタイム性の高いズーム機能、直感的なユーザーインターフェースなどを念頭におき、ゲノム情報可視化の研究として開発中。
    - [[デモムービー:http://www.youtube.com/watch?v=FEQlVEAJe2k]]
    - [[操作マニュアル:http://wiki.kazusa.or.jp/Projects:genoDive_Pro_manual_j]]

##  【参考4】ゲノムブラウザーの使い方動画 [#mef63c8a]
- [[TogoTV Curated:http://togotv-curated.dbcls.jp/]]で、「ensembl」「 UCSC」などで検索する
- 米国のマニュアル作製企業 OpenHelxによるGBrowseの[[使い方:http://www.openhelix.com/gbrowse]]

        --
(for presentation 「情報可視化」 ver. 0.1  Shinobu Okamoto CC BY 2010-8-05 modified)
[[AJACS21]]
