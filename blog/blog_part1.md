
# ゼロからはじめる生成AI入門①生成AIを触ってみよう


この記事は[ゼロから始める生成AIセミナー](peatix)のセミナー導入部「生成AIを触ってみよう」までのスライド・内容をまとめたものです。セミナー内容は４つぐらいの記事にわけて投稿していく予定です。  
この記事を読めば、「生成AIってなに？」状態からでも、「実際に自分のスマホでChatGPTを使う」まで、全部ひとりでできます！  
セミナーを開催できたのは、運営してくださった原嶋先生（会場代足りなかった分自腹！！！）や、準備期間中に家事育児を引き受けてくれた奥さんのおかげです。ほんとに感謝しかありません。

そんなわけで、この記事には投げ銭ボタンをつけています。いただいた分は、原嶋先生にこっそりお礼したり、奥さんにちょっといいワインを買ったりする予定です。

もし`いい記事だったな` `原嶋先生すごい` `奥さん偉っ`と感じていただけたら、コーヒー１杯分でも、応援してもらえるととても嬉しいです。

## 目的
**生成AI**（ChatGPTやGeminiなど）を使ってみたいけど、「なんだか難しそう…」と感じているあなたに向けて今の**生成AIの等身大を伝えたい！！**という思いで書きました。
	•	**ゼロ知識**でも大丈夫：スマホやパソコンが苦手な方でも、一歩ずつ分かりやすく説明します。
	•	**ゼロ予算**でも始められる：今、各社がこぞって無料枠を提供中。使わないなんてもったいない！
ぜひこの記事をきっかけに、生成AI活用の「はじめの一歩」を踏み出してみていただきたいんです、始めましょう、すぐに！コワクナイヨ！！！！！


## 生成AIってなんだ？

### アイスブレイク：実はみんなAI使ってます

では最初にアイスブレイク[^1]として、ひとつ質問です。

[あなたは「AI」を使ったことがありますか？](https://strawpoll.com/xVg7160VGyr)  
（↑クリックで投票できます）

この質問、セミナーでも聞いてみたのですが、ほとんどの方が「使ったことある」と答えてくれました！

でも実は、「使ったことない」って人も、気づかぬうちにAIに助けられてる可能性大なんです。

- QRコードの読み取り
- 美肌加工アプリ
- Amazonのおすすめ商品
- 天気予報アプリ
- ルート検索（Googleマップとか）

…はい、これ全部、AIの力が使われてます。

つまり、生成AI[^2]（ChatGPTとか）に限らなければ、**私たちはすでにAIと共に生活してる**んです。

（「使ったことない」に投票する人もいるかな…と思ってスライド用意してたんですけど、さすがみなさん、バッチリ活用してらっしゃる…！）

### そもそもAIってなに？

AIは、単なる「計算する機械」ではありません。
たとえば電卓は、入力された計算式に対して正確な答えを一瞬で出しますが、自分で考えることはありません。つまり、電卓はAIではないんです。
では、AIとは何なのでしょうか？
日本人工知能学会の定義によると、

> 人工知能とは、大量の知識データに対して、高度な推論を的確に行うことを目指したもの

少しかみ砕くと、
> 「大量の情報を**学習**して、自分で**考え**、そこから**予測**するプログラム」

と言えます。

たとえば、先ほどお話しした天気予報アプリもそのひとつ。
これまでの天気データを**学習**し、明日の天気を**予測**して、みなさんに天気予報として提供してくれています。

また、翻訳アプリでも多言語の膨大な文章を**学習**し、ある言語から別の言語の表現を**予測**することで、翻訳を実現しています。

では、**生成AI**[^2]――たとえばchatGPTは、いったい何を学び、何ができるようになったのでしょう？

生成AIが学習したのは、人間が読むのに**約6300年**かかるとも言われる、**膨大な量の文章**です。
その文章から**言語を紡ぐ力**を学び取りました。

![言葉を紡ぐ力](01_kotoba_wo_tsumugu.png)

その結果…
- 要約・翻訳
- プレゼンやセミナーのアイデア出し
- プログラミングのコード作成
- 丁寧なメール文の下書き
- レシピの提案(**オススメ**の使い方です)
- 物語の創作
  
まで、幅広く活躍できるようになったのです。

### 生成AIの活用例
以下のリンクは、実際の私と生成AIとの会話です。  
どんな目的で、どんな風に使っているかイメージできるでしょうか？！

![alt text](06_whitening.png)
#### [ホワイトニングの院内掲示作製](https://chatgpt.com/share/683a4668-2d10-8008-8122-50556ef6c620)
画像を作るときはいきなり画像を作らせず、細かいことを決めてから作るのがコツです！

![alt text](07_neage.png)
#### [値上げのお知らせ文](https://chatgpt.com/share/683a47c4-94f8-8008-bc77-b5b04b9bbfa9)
こういう堅苦しい文章作るの、億劫ですよね、でもまずchatGPTに作ってもらえばそれをたたき台にしてスタートダッシュ決められます！

![alt text](08_outai.png)
#### [電話応対マニュアル作製](https://chatgpt.com/share/683a4904-0e18-8008-98e5-fc820bac89c8)
先輩にインタビューした内容を録音して、なんらかの方法で文字起こしすれば、こんな風にそこからマニュアル作りだって！

#### [(応用編)ホワイトニング後のCR充填の接着についての論文検索](https://chatgpt.com/share/683a4bed-66e4-8008-863d-886cf483983c)
いずれ解説する「プロンプトエンジニアリング」を応用すれば、無料枠のなかで多機能な論文検索も可能です！

### 生成AIはなにがすごいの？


80年くらい前に、「人工知能の父」とも言われる数学者チューリングがあるテストを考えました。  
> 「もし、文字だけの会話で“相手が人間かどうか”が見分けられなかったら、それってもうAIは人間っぽいってことじゃない？」

それが、いわゆる**チューリングテスト**[^3]。  
開発から80年経った今でも、AIの“人間らしさ”を測る指標として使われています。

そしてなんと今年。ChatGPTがこのテストで、**7割以上の人に“人間だ”と間違われた**んです！[^4]  
すごない！？！？（語彙力）

つまり、「それっぽく話す」どころか、   
**“自然に人間とやりとりできる”レベルにまで来ちゃってる**ってことなんです。

---

ここでみなさんにもchatGPTの威力を体験していただくためにチューリングテストっぽいものを用意しました！

[どちらがラクラミのツイート？](https://strawpoll.com/e2naXlDreyB)  
（↑クリックで投票できます）

この投票、セミナーではなんと真っ二つに割れました。  
私の[「聖なるアンパンマン爆誕」](https://x.com/lacramydent/status/1700371254296060051)が「AIっぽい」って思われるなんて…いや、そこはGPT-4.5の表現力がすごすぎたということで…！

---

で、何が言いたいかというと…

**生成AIの“すごさ”って、ただ計算ができるとかじゃないんです。**

- 絶妙な言い回しができる  
- ちょっとウィットに富んだ返しができる  
- まるで友だちみたいに、相談にのってくれる
  
![GPTくんは相棒](02_GPT_is_partner.png)

秘書、先生、プログラマー、料理人、…そして時には、ツッコミ役としても（笑）

**人間のように色々できることこそが、生成AIの真骨頂！**（そして、人間のようにときには間違うことも…）  
これが今、AIがここまで注目されてる理由のひとつなんです。


## 2大テーマ「今がチャンス」「信頼せよ、ただし検証せよ」

![2大テーマ](03_theme.png)

では、そんな生成AIとどう向き合い、どう使っていけばいいのか？
今日のセミナーで**特に**伝えたい2つのテーマがあります。
**今がチャンス！** そして **信頼せよ。ただし検証せよ！** の2つです。

### **今がチャンス！！**

実は今、生成AIを無料で触れる最大のチャンスなのです。

ChatGPTやGeminiなどのAIが1回動くだけで、重い処理になると**100円近くかかる**とも言われています。（と、セミナーで発言したのですが情報源を見つけることができませんでした、すみません！ただし、１日の運用コストで約9000万円かかっているとも言われています[^5]）  
それなのに、なぜ無料でサクサク使えるのか？

理由はシンプル。**今、この市場で覇権を取りたい**からです。

少し前に、PayPayやLINE PayなどのQR決済が“キャッシュバック合戦”を繰り広げていたのを覚えてますか？  
あれと同じ状況です。企業は最初の段階でユーザーに使ってもらって、「このサービス便利だな」と定着してもらいたい。だから、**今は赤字覚悟で無料提供してる**んです。

しかも最近のAIは**進化のスピードがはんぱない**ので、触っているうちに「できること」がどんどん増えていきます。

最初は「あれ？意外とこれできないな…」って失望することもあるかもしれません。  
でもその先に、「自分じゃ絶対思いつかなかった！」っていうアイデアとか、「一人じゃだるすぎだった作業、任せられて超ラク！」みたいな経験が待ってます。

**だからこそ、「今、触ってる人」が圧倒的に得。**  
後から始めようと思っても、進化の波に乗れないとしんどくなる時期が来ます。

そうならないためにも、ぜひ今、はじめの一歩を踏み出しましょう。  
**始めるハードルは、思ってるよりずっと低いです。**
ではスマホを片手にレッツスタート！

### chatGPTのインストール(iPhone)
すでにインストールされている方は[最初にしてほしい質問]まで飛んでください

#### 0. chatGPTの入手

https://apps.apple.com/jp/app/chatgpt/id6448311069
まずはここをクリックするか、下のQRコードでapp storeを起動しましょう
![alt text](04_QR.png)


![alt text](05_appstore.png)
`入手`をタップ  
`chatGTP`というややこしい名前の偽アプリもあるので注意です！！

#### 1. アプリを起動したら「続ける」->「新規登録」を選択
![](09_step1.png)
ChatGPTアプリを開くと「ChatGPTへようこそ」という画面が表示されます。
画面右上の`新規登録`ボタンをタップします。

#### 2. 認証方法の選択
![alt text](10_step2.png)
今回はメールアドレスで登録する場合の例を紹介します。`新規登録` -> `続ける`をタップします。  
`Appleで続ける`などの選択肢もありますが、後にPCでログインすることも考えるとメールがおすすめです。

#### 3. メールアドレスの入力 -> パスワードの設定
![alt text](11_step3.png)
「アカウントの作成」画面で、ご自身のメールアドレスを入力し、`続ける`をタップします。  
設定したいパスワードを入力し、`続ける`をタップします。

#### 4. メールアドレスの確認（認証コードの入力）
![alt text](12_step4.png)
入力したメールアドレス宛に、ChatGPTから認証コード（ワンタイムパスワード[^6]）が届きます。
メールを確認し、記載された6桁の認証コードをアプリに入力してください。
> 例：「ChatGPTコードは422151です」と表示された場合は「422151」と入力します。

#### 5. 利用開始！！
![alt text](13_step5.png)
氏名(規約を読みましたが、実名のほうが無難だと思います)と生年月日を入力し、使用上の注意点について確認できたら、利用を開始できます！！！

### 最初にしてほしい質問
![alt text](14_nano_oral.png)
```
ナノ・オーラル合金で補綴はどう変わる？
```

めでたく利用開始できたら、ぜひ __最初に__ この質問をしてみてください。  
なんかすごい合金があるんですね…でもこれ…知らないぞ…

![alt text](15_nano_oral.png)
そうです、これ、**嘘です**

### 信頼せよ、ただし検証せよ
![alt text](16_trustbut.png)
超便利な生成AIですが、正しく使わないとこのようにスラスラと嘘をつくような悪いヤツ（AIに悪気はなし）にもなってしまうんです。  
そこで次回「ゼロからはじめる生成AI入門②生成AIのしくみ」編では生成AIのしくみについて解説する予定です！

### まとめ、そして応援のお願い

ここまで読んでくださり、本当にありがとうございます。  
「よし、ちょっくらやってみよう！」と思ってもらえたなら、これほど嬉しいことはありません。

もし「次の記事も気になる！」「応援したい！」と思っていただけたら、コーヒー1杯分でも大きな励みになります。  
（いただいたご支援は、セミナー運営を手伝ってくれた仲間や家族への感謝にも使わせていただきます☕️）

質問や「ここでつまづいた！」なども、ぜひコメント欄で教えてください。  
あなたの反応が、次回の記事を書くモチベーションにもなります！

[^1]: イベントの冒頭で、参加者の緊張をほぐすために行う簡単なやりとりや質問のことです。
[^2]: この記事では、ChatGPTやGeminiのように、文章や画像などのコンテンツを**生成**するAIを「生成AI」と呼びます。このようなAIは、大量のテキストデータを学習しており、自然言語の理解や生成を得意とします。特に言語モデルについては、**LLM（Large Language Model：大規模言語モデル）**と呼ばれています。
[^3]: COMPUTING MACHINERY AND INTELLIGENCE https://doi.org/10.1093/mind/LIX.236.433  <br>チューリングテストについての論文
[^4]: Large Language Models Pass the Turing Test https://doi.org/10.48550/arXiv.2503.23674 <br>GPT4.5がチューリングテストを突破した論文
[^5]: https://www.businessinsider.jp/article/269008/
[^6]: IDとパスワードという、記憶できる情報の他に認証方法を用意することでセキュリティを高める方法を多要素認証といいます。今回はメールアドレスが自分のものであると証明するためにワンタイムパスワードがメールに送られました。<br>たとえば銀行のATMを利用する時、「キャッシュカード（物理的なもの）」と「暗証番号（自分しか知らない情報）」の両方が必要ですよね。このように2つ以上の異なる方法で本人確認を行うことで、セキュリティを強化できるという考え方です。