
で、こっから使ってもらったとこで、どうやってチャットGPTが動いてるかって話を説明していきます。この話理解できてるのかなり資格関係だと少ないと思うので、

最初人間らしさがない機械ただの機械だったGPT君が人間らしくなるまでの物語を説明します。え。

ちょっとあれなんですね、ラグがあるのは僕がWi-Fiじゃなくて。あ、参加リクエストで止まってるって人か。

これ、大丈夫ですか？こっからちょっと、あの仕組みの説明でちょっとグってなると思います。Y=ax+b。

ということで、じゃあもう1回リンクを送っていただくとして、えっと人間の脳の中身って数億このニューロンっていう細胞があって、そこが繋がってるかどうかその信号が伝わるかどうかで物を考えたり覚えたりしてるんですけど、それを真似した構造が入ってます。

---
えっと、オノの回帰方程式って皆んな知らなすぎてマジでビビ。ごめんなさい。僕しかあれだった、なんかあ、すげえこんなのあるんだなってのを覚えてたんで。で、国試出てなかったらしいですけど。なんか乳歯の大きさを測ったら、え、そっから入ってくる永久歯の大きさがだいたい予想できるぞっていうのを見つけた先生が昭和35年にいて、の100人ぐらいの歯のサイズを計測してたんですかね。で、比例にするよっていうのを見つけたので、この点一杯の中の代表する線を引いて、乳歯の大きさがこれくらいだったから永久歯の大きさこれくらいだなっていうのを予測できる式を立てた先生がいるんです。

---
乳歯の大きさと永久歯の大きさの関係のデータから学習して、乳歯の大きさから考えて永久歯の大きさを予測するっていう定義から行くと、これもAIなんです。AIの定義自体がいっぱいあるからちょっと微妙なとこなんですけど。

---

で、これはどういう風に決まってるか、この線が決まってるかと言うと傾きがAで切片がBって話覚えてますかね？うちの奥さんはここでグってなってたんですけど、その傾きAが決まるとこの線の傾きが決まって、Bが決まるとこの上下を動かすのが決まって、1番これに近い線を引きましょうっていうことをしてるんですね。言い換えるとAとB、二つのつまみを調整して予測する計算式を立ててます。これ例えば、乳歯の大きさだけじゃなくて、他に身長とかも関係そうじゃないですか？なんとなくイメージですよ。それ身長も入れたらもっと、あの良い予測が立てられるんじゃないかとなってると、乳歯の大きさに掛ける数字、身長に掛ける数字と、この高さ、切片を決めて3つのつまみを回して予測できる式を立てるってことになるんです。ここが伝わって欲しい。

---

でもじゃあ株価とかって直線引けますかって話になってくるんですね。こんなの予測不能だろうと思うんですけど、こういうなんかギザギザとかうねうねしたものを予測するためにさっきのニューロンの話が出てきて、いっぱい調整するつまみを作ると、こういううねうねのものも予測できるようになるんですね。その仕組みを使ったものが生成AIです。

---

で、この予測してるものが何かと言うと、こっからもう大丈夫。数字、数字出ません。数字出ないので。えっと、昔昔ある所に、おじいさんとおばあさんがいましたっていう文章の昔昔だけを見て次の言葉を当てましょうっていうゲームをさせてます。昔昔の次は点だったりあるだったり。昔昔の昔々遠あるとかに続くと思うんですけど、正解は点でした。あ、点であたっててたけどここ100%じゃないから、この正解率100%になるようにつまみを回しましょう。次はどんな言葉かな？あるっていう言葉なので、え、70%の予測だったので、これが100%になるようにまたつまみを回しましょうっていうのを人間が読むのに6300年分かかる文章で、え、正解率が上がるように訓練していくと、語彙爆発っていうの、あの1歳半ぐらいの赤ちゃんが急にいっぱい言葉を喋り出すっていうタイミングがあるんですけど、その時に、うーん、いろんなことができるようになるののそっくりな現象がAIにも起きて、ある一定の言葉以上を覚え出した途端に計算ができるようになったり翻訳もできるようになったりするんですね。これ創発的能力って名前がついてるんですけど。それ何だろうって考えた時に、これ答えじゃなくてこういう風なんじゃないかなって詳しい人が予測してるだけなんですけど。


---

例えばこれ読まなくていいです。推理小説が1冊あって最後の最後に簡単なことだよワトソン君。犯人は点々点。次の言葉を予測してくださいって言われたら、これって推理小説を読んで犯人を推理してるっていうのと同じことをやってると思いません？この正解率が上がるってことは推理小説読めるようになるっていうことなんですよね。なので人間らしさが芽生えたように見える。

---

で、論文もいっぱいやって、本当に人間と同じようなこと考えてるのかとかを調べてる人達がいっぱいいるんですけど、一つ紹介させていただきます。生成AIが概念を理解してるかっていうのにヒントになる論文なんですけど、男と女っていう言葉の違い、さっきのあの地図の話ですけど、とおいてめいの違いが同じってことはこの違い、つまり男女の違いを理解してるんじゃないかみたいな仮説があって、

---
そこでさっきのさっきのさっきのゲーム、さっきのゲーム出てこない。さっきのゲームが出てくるんですけど、ちょっと待ってくださいね。これ僕、僕の記録越えるの出ましたかね？

いやこれ絶対超えれないですよね。やってみました。これどんな風な感じかっていうと攻略法が2つあって、一つはこの中から選ぶ必要はないですよって言ったと思うんですけど、別にこの中の単語を選んでもいいので、ティッシュペーパーだったらティッシュペーパーって1個入れていいんですよね。そしたら全く一緒の単語なので点が上がるのと、ティッシュペーパーって、ティッシュペーパーって打ち間違えることあるじゃないですか？それも大体同じ意味だなって、その学習してる単語の中ににあるので、例えばティティッシュペーパーとかの打ち間違いも言うと、これで6000点ぐらいとかかな？あ、8000点行きましたね。っていう攻略法がありました。

でもまあこれは攻略法知っちゃうとなんかあんま面白くないんですけど、こう宇宙、宇宙宇宙みたいなんでやってるんですけど、なんか全体で見た時にちゃんと、うーん、AIがご飯とか天ぷら、天ぷらとエンパが一緒、なんか微妙ですけど。なんかそういう家電の塊とか、これが分かってるんじゃないかなっていう話でした。ちなみにこのプログラムもAIを使って書いてます。

---

ててててて。もう1回投票をしてもらいます。AIには知性があると思いますか？これ答えがある訳じゃなくて、本当に人間の知性のうちの一部をちゃんと再現できてってるっていう、うーん主張してる人と、うーん全然人間とは違うから、なんか同じ言葉を話すあくまで機械として接するべきだっていう人と、もうなんか人間のその喋る言葉能力自体がもう計算でできるような簡単な仕組みなんじゃないかって言ってる人と色々いるんですよね。

---

ということでまだ仕組み編が続きます。AIはどのように言葉を理解しているか？皆さんこれはご存知ですか？東雲色っていう色知ってる方。僕はこれ知らなかった、知らない色を探してたんですけど。

---

東の雲の色ってことで夜明けの色、オレンジ色が東雲色っていう名前がついてます。

---

ところでこの色、赤が255のうちの241、緑が144、青が114。この組み合わせでできる色どんな色でしょう？赤が強いので赤っぽくて。これ他の色が増えれば増えるほど明るくなってくるんですよね。で、真ん中分ぐらいに明るい色。オレンジっぽい色って分かると思うんですけど。これさっきの東雲色なんですよ。このようにあの色の名前はちょっと由来があったりなかったりするのであれですけど。色のことを数字の集まり。赤成分が241、緑成分が144、青成分が114。具体的な色が数字の集まりで表現できるっていう例を伝えました。これができると何が嬉しいかと言うと、

---
東雲色に青成分を足したらどんな色ですよとか、さっき数字が増えると明るくなりますよっていう話しましたが、減らすと暗くなるので暗い色だとどっちみたいなのを計算できるんですね。

で、さっきのゲームもそうですけど、王様引く男プラス女が女王様だよっていう計算もできるようになるわけなんです。

---

これグミとかキャンディとかチョコとかポテチのお菓子ですけど、このお菓子を甘さと酸っぱさの数字で表しましょうって言うと、グミは甘さが0.8酸っぱさが1.0。キャンディは甘さが0.9、酸っぱさが0.4。チョコは甘さだけ。ポテチは甘みも酸味もそんなにないよみたいな。そういう風に言葉を数字の集まりで表してます。今のAIだとだいたい1つの言葉を3000個から3万個の数字で表してるって言われてます。

---

それをさっきのゲームみたいに地図で表すと、チョコがこの辺にいて、グミがこの辺にいて、キャンディがここにいて、ポテチがここにいて。で似たようなお菓子を探すみたいなことがこの空間の中でできる訳なんですね。ところがよくよく考えてみてください。グミって言ってもレモン味のグミとかメロン味のグミとかあるじゃないですか？それって数字変わってきちゃいますよね。同じグミなのに、グミって単語なのに、これが意味してる味が違うよっていうのに対応するための仕組みが


---

セルフアテンションって言って、これはあのこの単語自体がもうこのこれが発明されたのでチャットGPTができたよっていうぐらいのすごい仕組みなので、これはなんか簡単な言葉で言い換えれなかったんですけど。文の中の単語同士の関係性を計算するっていう仕組みで、関係性によって単語の意味を文脈に沿ったものに調整する。つまり試合に負けて泣きながら食べたグミは少しこれどんな味だったかって言ったらしょっぱい。グミなのにしょっぱいっていうのを理解できるようになってるんです。この仕組みのおかげで。

これもう一つ違う例を言うとすると、葉っぱがの絵がありました。葉っぱの絵がありました。これ書けんだっけ？書いて消せなかったら困るけど書きます。葉っぱがありました。葉っぱがありました。茎がまっすぐありました。さてここに何が来るでしょう？っていうゲームをやってるのとさっきの単語テストが同じような感じになるので。ここに葉っぱがあったら花はきれいな花ですねっていうのが分かると思うんですけど。葉っぱがありました。葉っぱがありました。茎がこんなんでした。位置がこんなんでした。じゃあここに来る花はどんなんでしょう？これはしおれてるっていうことをさっきのあの次の単語当てゲームの勉強の時に一緒に勉強することは出来るので。例えば水中それは苦しいっていうこれ元に戻せない、どこにどうやんだろう。あ、分からん。まあいいや。水中それは苦しいっていう時にそれっていうのが水中のことを表してるんだなっていうのをチャットGPTは理解できてるわけです。

---

ただこの計算て大変で、水中と他の単語に関係してるのがどんぐらい関係してるかっていうのに5回計算しなきゃない。点は他のところとなんかあんまり関係してなさそう。それは水中のことだよねってことはちょっと苦しいよねっていう風に計算してくと、この長話の文章で25回計算しなきゃない。これが100部105の単語だと1万回計算しなきゃなくて、1000語の文だと100万回計算しなきゃないんですね。これだいたいパソコンのCPUって頭脳が1秒間に計算できるのが1億回とかっていうの。1、2、3、4、5、6、7、8。そう、9乗まで行けるのかな？10億とかって言われてるので、それみんなが使ってってなった時にすごい大変ですよね。
※訂正: LLMで計算するのはGPUなので1秒間に1兆回〜1京回でした  

---

なので制限があります。1回に読める長さの制限があって、うーん1回のチャットの今までの経緯をちゃんと覚えてさっきの関係してるかなってのを計算してくれるんですけど、覚えてられるのはこれ調べたらプロプランじゃないか、プロプランだな。プロプランなのでお金払ってると文庫1冊分まで覚えてくれるんですけど、お金払ってないとだいたい4000字だから原稿用紙10枚分とかで、それ以前の会話は忘れちゃうっていう仕組みがあります。逆に言うとそこに入ってることは分かってて話をしてきます。

---

で、もう一つその6300年分の知識といってもこれ覚えさせるのにめちゃくちゃ時間がかかってる訳で、今、あのさっき使ってもらったチャットGPT4オムニっていうモデルでは、モデるってその何個か、その課金した人は強いAIを使えて、課金してない人は弱いのを使うみたいなのがあるんですけど、その課金してないで使えるやつの知識は確か去年の11月までの出来事しか知らないはずです。

---

という仕組みを使って、えっと、昔々ある所におじいさんとおばあさんがいましたを勉強しましたけど、じゃあ昔々に文章を続けてくださいねって言った時に、え、学んだ中から次に続きそうな確率をバーっと並べて、その中から1番可能性が高いやつだけを喋らせると失敗するんですよ。これちゃんと確率通りに70%の次は、ま10%を選ぶこともあったりっていう感じで文章を作ってます。

---

さてクイズです。生成AIが苦手な作業はどれでしょう？なんかここまで喋ってると何となく当たっちゃいそうな。あ、すごい結構皆さん反応してくれます。30票入ったいいかな？これずるいんですけど全部です。これさっきのあの言葉を数字で表してるっていう話をしましたが、多分10+20とかぐらいまでなら計算できます。花島先生。872掛ける977はあ、分かんないです。っていう感じで、いやそんぐらいになると、なんかこっちの数字が大きいかな、こっちの数字がちっちゃいかなぐらいの感覚しか持ってないので、計算しろって言われると困っちゃうんですよ。困った結果何が起きるかって言うと嘘作るんですよね。嘘を作ってなんか予測してるじゃないですか？これ多分次多分10じゃないんだけどなって思いながらも10になっちゃうみたいな。で最新情報取得は皆さん正解してましたもんね。で文字数カウントもちょっと難しい話になるんですけど、その単語の意味については知ってるんですけど、その単語が何文字ですよっていう情報は覚えてないので、文字数をカウントすることはできない。皆さんも原稿用紙に書いたら、あ1枚分だなって分かるけど、原稿用紙1枚書いたら、その字詰めの分とかで何文字書いたとかまでって分からないじゃないですか？でも大体これぐらいの長さだなぐらいは分かるので、まああんまり大きくは外れないんですけど、何時以内で答えてって言ってるのは、ちゃんと何時だよって数えて答えてる訳じゃなくて、だいたい原稿用紙1枚分ぐらいの答えかなみたいな感覚で答えてると思ってください。

---

でもAIって進化してるので、もう今年に入ってから色々機能が増えてるんです。さっきの花島先生にめちゃむちゃにした計算やる時って、じゃあ何するかって言うと電卓使いますよね。もうそれだけの話で、電卓とかその最新情報とかあ、分からないなと思った時に、例えばAIがその情報ちょっと分からないなって考えたとしたら、考える時って僕ら言葉でも考えたりするじゃないですか？なのでその質問が来た時に、ちょっとこれ電卓使いたいなと思った時には電卓を使って答えるバージョンがAIが呼ばれてます。プログラミングの時もプログラミングって1文字違うだけで動かなかったりするので、その時にもプログラミング用の機能が呼ばれてます。で検索する時も検索機能が呼ばれてます。元のその仕組みだけで全部完結してる訳じゃなくて、そのアプリの中ではファンクションコーリングって言うんですけど、いろんな機能をAIが考えて使ってる。でもさっき言った通り確率で動いてるので、その考えに至ってくれないこともあって、計算してねっていうのに計算してくれないことがあったりしたり、そういう動き方をするものが生成AIです。

---

前半のまとめに入ります。生成AIとは大量の文章から言葉の紡ぎ方を学んだプログラム。人間らしさで様々なことをやってくれます。言葉を数字の集まりとして理解し、その言葉が言葉同士がどんな風に関係してるかっていうのを考えて文脈を理解。あとはその文脈理解できるのはだいたい文庫本1冊分。その文庫本1冊分の会話の中の知識と事前に勉強したすごい量の知識を持ってます。でもその知識から検索して答えてる訳じゃなくて、その勉強したことからニュアンスを勉強して、あの確率で答えてます。でそれだけだとちょっとできることが少ないので、人間が考えているかの様に色んなツールを使って答えを出してくれるものです。

---

なので、えっと、序盤にも言いましたが、スーパーコンピュータだと思って答えを聞きましょうっていう風に使うんじゃなくて、ちょっと一緒に調べようよとかここ分からないんだけどみたいな使い方。完成版を出すんじゃなくて叩き台として出してもらったやつをちょっと修正すれば完成するよみたいなアイデア出しもそのこういうことをしたいっていうのはさすがに考えてくれないので、ゼロから1と出来上がった60から100を人間がやるみたいなイメージで使っていくものです。

ということで第1部間なので休憩に入ろうと思いますが質問がある方はチャットか会場の方だと挙手でお願いします。ということでお疲れ様でした。

---
