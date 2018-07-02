        --
目次

#contents
        --
#  BodyParts3D/Anatomographyとは [#tc8a24fa]
BodyParts3D(ボディパーツ3D)は人体各部位の位置や形状を3次元モデルで記述したデータベースです。Anatomography(アナトモグラフィー)を使って、BodyParts3Dから解剖学用語を選択して自由に人体のモデル図を作成できます。

#  BodyParts3D/Anatomographyの場所 [#x400f1d9]
- [[統合データベースプロジェクト:http://lifesciencedb.jp]]の「ツール＆解析サービス」から。
- [[トップページURL (http://lifesciencedb.jp/bp3d):http://lifesciencedb.jp/bp3d]]
- [[「BodyParts3D or Anatomography or アナトモグラフィー」でgoogle検索:http://www.google.co.jp/search?q=BodyParts3D&ie=utf-8&oe=utf-8&aq=t&hl=ja&client=firefox-a&rlz=1R1GGGL_ja___JP322]]

# 【実習1】基本的な操作手順を覚える [#a5091eff]

- 「Information」タブ→「ユーザガイド」→「[[Getting Started:http://lifesciencedb.jp/bp3d/info/userGuide/gettingStarted/index.html]]」をひと通り実施します。

# 【実習2】AQP3遺伝子の臓器別発現量を人体ヒートマップで表示し発現状況を可視化する [#ib574ea2]

+アクアポリン３(AQP3)という遺伝子の発現量ヒートマップを作成します。
++データソース：[[BioGPS(http://bipgps.gnf.org):http://biogps.gnf.org/#goto=genereport&id=360]]
#ref(aqp3.png,left)
+まだ、csvデータを直接取り込むインタフェースがありませんので、作成済みマップのリンクをクリックしてください。→
[[作製済みマップ:http://lifesciencedb.jp/bp3d/?tp_ap=av%3D09051901%26iw%3D640%26ih%3D590%26bcl%3DFFFFFF%26cf%3D0%26bv%3D2.0%26dt%3D20100603215605%26cx%3D-0.622%26cy%3D-984.5671%26cz%3D828.6308%26tx%3D-0.622%26ty%3D-96.5107%26tz%3D828.6308%26ux%3D0%26uy%3D0%26uz%3D1%26zm%3D0%26cm%3DN%26oid001%3DFMA7203%26osc001%3D300%26osz001%3DS%26oop001%3D1.0%26orp001%3DS%26oid002%3DFMA7394%26osc002%3D1500%26osz002%3DZ%26oop002%3D1.0%26orp002%3DS%26oid003%3DFMA7198%26osc003%3D1200%26osz003%3DS%26oop003%3D1.0%26orp003%3DS%26oid004%3DFMA9600%26osc004%3D1250%26osz004%3DS%26oop004%3D1.0%26orp004%3DS%26oid005%3DFMA7195%26osc005%3D1500%26osz005%3DS%26oop005%3D1.0%26orp005%3DS%26oid006%3DFMA7197%26osc006%3D250%26osz006%3DS%26oop006%3D1.0%26orp006%3DS%26oid007%3DFMA7163%26osz007%3DS%26oop007%3D0.1%26orp007%3DS%26lt%3D%26le%3D%26la%3D]] (レスポンスが遅い場合は[[｢作成済み画像｣>./readyMadeMap]]をクリックしてください)
+[[「臓器別に取得された数値を色情報に変換してヒートマップを作成するには」:http://lifesciencedb.jp/bp3d/info/userGuide/faq/value.html]]を参考に、発現量を入力できることを確認します。
+[[「Palletの中で選択した臓器にフォーカスするには」:http://lifesciencedb.jp/bp3d/info/userGuide/faq/focus.html]]を参考に、画像を見やすい大きさにします。

# 【実習3】BodyParts3D人体の特徴を確認する [#eb6dd876]

+モデル人体の身長を調べる
++確認方法
+++｢Bp3dViewer｣で｢人体｣アイコンをPalletにドラッグして、Palletに表示されるZmax(1670.79mm)とZmin(-13.5285mm)の値を確認。その値から168.4cm程度。

+左右の腎臓の高さを比較する
++確認方法（直感的）：
+++腎臓を[[Anatomographyで表示:http://lifesciencedb.jp/bp3d/?tp_ap=av%3D09051901%26iw%3D590%26ih%3D650%26bcl%3DFFFFFF%26cf%3D0%26bv%3D2.0%26dt%3D20100603232808%26cx%3D-16.4353%26cy%3D770.6758%26cz%3D1101.9546%26tx%3D-16.4353%26ty%3D-117.3805%26tz%3D1101.9546%26ux%3D0%26uy%3D0%26uz%3D1%26zm%3D3%26cm%3DN%26oid001%3DFMA7203%26ocl001%3DFF0000%26osz001%3DS%26oop001%3D1.0%26orp001%3DS%26oid002%3DFMA7197%26ocl002%3D0000FF%26osz002%3DZ%26oop002%3D1.0%26orp002%3DS%26lt%3D%26le%3D%26la%3D]] (レスポンスが遅い場合は[[｢作成済み画像｣>./hint3-3]]をクリックしてください)
++確認方法（数値的）：
+++確認方法（直感的）で作成したAnatomographyのPalletには｢腎臓｣だけがあり、｢左腎臓｣、｢右腎臓｣がないため、それぞれの高さは分からない。そこで、
+++画面上で｢左腎臓｣をクリック後、｢Pick｣タブに表示された｢左腎臓｣のチェックボックスをチェックし、Palletに追加して、Zmax(1117.5699mm)を確認
+++｢右腎臓｣についても同様の方法でZmax(1101.8199mm)を確認。


+右冠状動脈が上行大動脈の右大動脈洞から起こる
++確認方法：
+++[[Anatomographyで表示:http://lifesciencedb.jp/bp3d/?tp_ap=av%3D09051901%26iw%3D670%26ih%3D760%26bcl%3DFFFFFF%26cf%3D0%26bv%3D2.0%26dt%3D20100801161138%26cx%3D21.5629%26cy%3D-1009.8996%26cz%3D1243.63%26tx%3D21.5629%26ty%3D-121.8432%26tz%3D1243.63%26ux%3D0%26uy%3D0%26uz%3D1%26zm%3D3.4%26cm%3DN%26oid001%3DFMA7088%26osz001%3DZ%26oop001%3D0.3%26orp001%3DS%26oid002%3DFMA50039%26ocl002%3DFF0000%26osz002%3DS%26oop002%3D1.0%26orp002%3DS%26oid003%3DFMA3736%26ocl003%3D0000FF%26osz003%3DS%26oop003%3D1.0%26orp003%3DS%26lt%3D%26le%3D%26la%3D]](レスポンスが遅い場合は[[｢作成済み画像｣>./hint3-4]]をクリックしてください)
+++｢上行大動脈｣、｢右冠状動脈｣、｢心臓｣のアイコンが探しにくい場合は、画面左上の｢Data search｣で臓器名を入力して検索できます。

//+右肺が左肺よりも大きいことを確認
//++右肺と左肺の体積を表示
//++[[Anatomographyで表示して確認:http://lifesciencedb.jp/bp3d/?tp_ap=av%3D09051901%26iw%3D590%26ih%3D650%26bcl%3DFFFFFF%26cf%3D0%26bv%3D2.0%26dt%3D20100603233154%26cx%3D-1.3695%26cy%3D-994.9948%26cz%3D1244.0601%26tx%3D-1.3695%26ty%3D-106.9384%26tz%3D1244.0601%26ux%3D0%26uy%3D0%26uz%3D1%26zm%3D2.6%26cm%3DN%26oid001%3DFMA7195%26ocl001%3DFF0000%26osz001%3DS%26oop001%3D0.2%26orp001%3DS%26oid002%3DFMA7088%26ocl002%3D0000FF%26osz002%3DZ%26oop002%3D1.0%26orp002%3DS%26lt%3D%26le%3D%26la%3D]] (レスポンスが遅い場合は[[｢作成済み画像｣>./hint3-2]]をクリックしてください)

※現段階ではBodyParts3Dで観測できる全ての特徴が解剖学的に正しいとは限りませんので、正確には書籍等で確認してください。BodyParts3D作成過程を説明した[[:モデリングノート:http://lifesciencedb.jp/bp3d/info/userGuide/releaseNotes/index.html#rel2.0]]も参照ください

#  講習会資料(pdf)ダウンロード [#s02c3e49]

#ref(ajacs21Bp3d.pdf,left)

#  紹介動画 [#fedf3565]
- 統合TV
    -[[BodyParts3D/Anatomography の使い方 ～変更点の紹介編～:http://togotv.dbcls.jp/20100801.html]]
    -[[BodyParts3D/Anatomography の使い方 ～操作編～:http://togotv.dbcls.jp/20100803.html]]
- [[YouTube投稿動画:http://www.youtube.com/v/tWo377ImVVA&amp;hl=ja_JP&amp;fs=1]](英語、1min30sec)
