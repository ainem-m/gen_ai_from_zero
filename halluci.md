LLM（大規模言語モデル）の**ハルシネーション（hallucination、幻覚）**とは、一見もっともらしく見えながら実際には正しくない文を生成する現象を指します [1]。この現象はLLMを活用する上で大きな課題となっており、以下のような特徴を持ちます [1]:
*   文法的に正しく、言語として大きな不自然さがない [1]。
*   内容が事実に反していたり、論理的な矛盾がある [1]。
*   信じ込んでしまいそうなくらい説得力がある [1]。

ハルシネーションはLLMの応用において非常に厄介な問題であり、様々な対策が研究されています [1]。

### ハルシネーションの分類

ハルシネーションは、主に以下の観点から分類されます。

1.  **事実性ハルシネーション (Factual Hallucination)** [2]
    *   **定義**: LLMが生成した文が**現実世界の事実と一致しない**場合に発生するハルシネーションです [2]。現実世界における事実関係と整合性がとれていない回答を指します [2]。
    *   **類型**:
        *   **事実との矛盾 (factual inconsistency)**: 現実世界の事実と矛盾することが検証可能なケース [3]。
            *   例: 「神奈川県の県庁所在地は、かながわ市です」という回答は、現実世界の事実（横浜市）と矛盾します [3]。
        *   **事実の偽造 (factual fabrication)**: 現実世界の事実に基づかないケースや、検証不能なケース [3]。
            *   例: 存在しない論文のURLを生成するなど、現実世界に根拠を見出せない「作り話」を生成するケースが該当します [3, 4]。

2.  **忠実性ハルシネーション (Faithfulness Hallucination)** [5]
    *   **定義**: LLMが生成した文が、**与えられたプロンプトや文脈と一致しない**場合に発生するハルシネーションです [2, 5]。内容が事実であるかどうかは別として、入力文の文脈や質問の意図と整合性がとれていない回答を指します [5]。
    *   **類型**:
        *   **指示不一致型 (instruction inconsistency)**: ユーザーの指示の意図とは異なる回答をするケース [5]。
        *   **文脈不一致型 (context inconsistency)**: ユーザーが提示している情報とLLMの回答が矛盾しているケース [5]。
        *   **論理不一致型 (logical inconsistency)**: LLMが生成した文が、論理的に自己矛盾しているケース [5]。
        *   **消極型 (ambiguity, under-informativeness)**: 明言を避けた曖昧な回答や、"I don't know"など無知を装った回答、LLMの悪用防止のための定型句を濫用するケース [5]。
    *   **ユーザーの指示に従い、指示不一致型や回答拒否（消極型の一部）は「幻覚」ではなくタスク失敗として扱います。** これらのケースは、LLMが質問の意図を理解できなかったり、回答を不必要に差し控えたりする挙動であり、ハルシネーション（事実と異なる内容を生成する現象）とは区別されるべきです [5]。
    *   **事実性との優先順位**: AIアバターとの会話目的であれば忠実性が重要ですが、仕事や勉強のサポート目的であれば事実性がより重要となります [6]。ただし、過去の誤った情報への過度な忠実性は、ハルシネーションが雪だるま式に増幅するリスクも指摘されています [6]。

3.  **内在型ハルシネーション (Intrinsic Hallucination)** [6]
    *   **定義**: 入力文に書かれた情報と、LLMによる生成文の間に**矛盾が存在する**ハルシネーションです [6]。
    *   例: 24時間営業の商業施設が多いという記述と、深夜営業が禁止されているという記述が同じ回答内に存在し、自己矛盾しているケースなどが挙げられます [7]。

4.  **外在型ハルシネーション (Extrinsic Hallucination)** [6]
    *   **定義**: LLMの生成文の根拠が、**入力文の中に存在しない**ハルシネーションです [6]。つまり、元の文脈から論理的に確定できない新情報をLLMが勝手に追加するケースを指します [8]。
    *   例: 「Xさんは高校時代にバンドでギターを弾いていました。Xさんはダンスもできますか？」という質問に対し、「Xさんはダンスも得意です」と回答するケース。質問文にダンスのスキルに関する情報がないにもかかわらず、LLMが断定してしまう点が該当します [7, 8]。
    *   外在型ハルシネーションであっても、LLMの内部知識に基づいて事実と合致している場合もあります [8]。この場合、ユーザが見落としていた情報をLLMが適切に補ってくれたと肯定的に捉えるか、勝手に情報を追加したと問題視するかは、LLMの回答利用用途によって判断が必要です [8]。

### ハルシネーションが発生する主な原因

ハルシネーションの発生原因は、主に以下の3つに分類されます [9]。

*   **学習データに由来するハルシネーション** [9]:
    *   **学習データの誤情報やバイアス**: 学習データに含まれる誤った記述や俗説をLLMが模倣してしまうことがあります [10]。大規模なLLMほど記憶容量が大きく、このリスクが高い傾向があります [10]。また、LLMの学習日以降の最新情報が不足していることも原因となります [11]。
    *   **ロングテールの裾野に位置する知識の不足**: 学習データがジップの法則などに従い、稀な知識（ロングテールに位置する知識）は学習が不十分となり、ハルシネーションの原因になります [11, 12]。
*   **学習に由来するハルシネーション** [12]:
    *   **露出バイアス**: 自己回帰モデルの構造的な課題により、生成が長くなるにつれて誤差が蓄積され、ハルシネーションにつながる場合があります [12]。
    *   **RLHF（人間からのフィードバックによる強化学習）によって生じるハルシネーション**: LLMが人間の評価者に過剰に迎合し、「事実ではないが人間は好みやすい」回答（忖度）を生成するリスクがあります [13]。
    *   **ショートカット学習**: LLMが本質的な理解ではなく、キーワードの共起や文体など、非本質的なパターンを覚えてしまうことで、誤った推論を導き出すことがあります [13, 14]。
*   **推論時に生じるハルシネーション** [14]:
    *   **逆転の呪い**: 「AはBだ」を学習しても「BはAだ」という文の生成に失敗する現象が報告されています [14]。
    *   **系列位置効果**: プロンプトの中間に書かれた情報をLLMが活用しにくい傾向があることが指摘されています [15]。
    *   **知識の競合**: LLMの内部パラメータに埋め込まれた知識が、検索結果などの外部知識より優先され、忠実性ハルシネーションを引き起こすことがあります [15]。

### ハルシネーション抑制のための対策

ハルシネーションを抑制するための対策は多岐にわたります [16]。

1.  **学習データの改善** [16]
    *   **フィルタリング**: Webクローリングで収集したデータから、目的外の言語やドメイン外のデータ、不適切なコンテンツを除去します [17-21]。重複データの除去も行われます [18-20]。
    *   **合成データの利用**: LLMや既存のソフトウェアを用いて高品質なテキストデータを自動生成し、学習に使用します [22]。これにより、特定のバイアス（忖度など）の抑制も可能です [22]。
    *   **指示チューニングの改善**: LLMの性能は指示チューニングの品質に大きく影響されるため、少量の高品質なデータを使用することが重要です [23, 24]。
    *   **RLHFによるアラインメント**: 人間からのフィードバックを報酬としてLLMをチューニングし、人間にとって好ましい、より人間的な感覚に近づけた回答を生成するように調整します [25, 26]。報酬モデリングと強化学習（PPO、DPOなど）が用いられます [25-34]。

2.  **デコーディング方法の改善** [34]
    *   **ペナルティの導入**: すでに出力した単語と似た単語の繰り返し出力を抑制するため、類似度が高い単語にペナルティを課す方法が提案されています [35]。また、小規模な「アマチュア言語モデル」の振る舞いの違いを活用して、誤った単語の選択を抑制する方法もあります [35, 36]。
    *   **LLMの内部状態にもとづくデコーディング制御**: Transformerの浅い層（統語情報）と深い層（意味論・知識情報）の出力の差を利用することで、事実性を強調した生成が可能となります（DoLaなど）[36, 37]。

3.  **モデル構造の改良** (これらの技術は、直接のハルシネーション対策というよりも、LLMの基礎的な性能、特に長文処理能力を向上させるための改良です。)
    *   **自己アテンションの改良**: 長文処理のボトルネックとなる自己アテンションの計算量を削減するための手法です [38]。
        *   **フラッシュアテンション**: GPU上のデータ転送を最適化し、計算を高速化します [39, 40]。
        *   **スパースアテンション**: すべてのトークンペア間の計算を避け、一部のみに限定することで計算量を削減します（Reformer、BigBirdなど）[38]。
        *   **線形アテンション**: カーネル関数を用いて計算量を線形オーダに削減します（Performerなど）[41-44]。
    *   **位置符号の改良**: 長文を効率的に扱えるよう、位置情報の注入方法を工夫します [45, 46]。
        *   **ALiBi**: 線形バイアスで相対位置関係を表現します [47]。
        *   **RoPE (Rotary Positional Embedding)**: 回転行列を用いて位置情報を埋め込みます [48]。
        *   **位置内挿 (Positional Interpolation, PI)**: 学習済みのLLMで扱える文脈長を、位置符号の範囲を引き伸ばすことで拡大します [47, 49]。
    *   **状態空間モデル (State Space Model, SSM)**: Transformerの欠点を克服し、長文を効率的に処理するための新しいアーキテクチャ（RetNet、RWKV、Mambaなど）が注目されています [47, 50-53]。

4.  **プロンプトエンジニアリング (Prompt Engineering)** [52]
    *   LLMの内部に手を触れずに、入力（プロンプト）の工夫によってLLMの挙動を制御する手法です [52, 54]。
    *   **思考の連鎖 (Chain-of-Thought, CoT)**: LLMに思考過程を段階的に出力させることで、より正確な推論を促し、ハルシネーションを抑制します [54]。
    *   **自己整合性プロンプト (Self-consistency Prompt)**: 複数の思考経路を生成させ、最も一貫性のある回答を選択します [55]。
    *   **出力の検証 (Verification)**: LLMが生成した情報の誤りを検証器（Verifier）によって確認し、品質を改善します [55]。
        *   **CoVe (Chain-of-Verification)**: 生成された回答内の各主張に対し、検証用の質問を生成して正確性を確認します [56, 57]。
        *   **自己検証 (Self-verification)**: LLMに自身の推論ステップの妥当性を検証させることで、途中で生じるハルシネーションの連鎖を防ぎます [57, 58]。
    *   **プロンプトの自動生成**:
        *   **方向性刺激プロンプティング (Directional Stimulus Prompting, DSP)**: 補助的なLLMでヒントを生成し、メインのLLMの回答を誘導します [59]。
        *   **マルチエージェント型LLM**: 複数のLLMエージェントに異なる役割を与えて対話させることで、協力的に問題を解決し、最終的な出力の品質を向上させます [60, 61]。
        *   **LLMフレームワーク**: LangChainやLlamaIndexなどのフレームワークを活用し、複雑なプロンプトパイプラインを効率的に開発します [62]。

5.  **外部知識活用にもとづく生成** [63]
    *   LLMの内部にない知識を外部から取得し、それを活用することでハルシネーションを抑制する手法です [63]。
    *   **検索拡張生成 (Retrieval-Augmented Generation, RAG)**: 検索エンジンを利用して、必要な情報が記述された文書を検索し、その検索結果をLLMへのプロンプトに組み込むことで、事実性の高い回答を生成させます [63, 64]。
        *   検索方法には、文字列の類似性に基づく**疎ベクトル検索**（TF-IDF、BM25など） [65-69] と、意味論的な類似性に基づく**密ベクトル検索**（DPR、文埋め込みなど）[69-74] があります。効率化のために近似最近傍探索（HNSW、IVF-PQなど）が利用されます [42, 43, 75, 76]。
        *   検索結果の質を高めるために、**クエリリライタ** [76, 77]や**リランカ** [78]を組み合わせることもあります。また、疎ベクトル検索と密ベクトル検索を組み合わせた**ハイブリッド検索**も有効です [79]。
    *   **ツール拡張生成 (Tool-Augmented Generation)**: LLMが外部の専門的なツール（SQL、Pythonインタプリタ、記号処理システム、物理シミュレータなど）を利用して、より正確な情報を取得したり、複雑な推論を行ったりする手法です [55, 58, 63, 80]。
        *   **Text-to-SQL**: 自然言語からSQLクエリを生成し、RDBMSから情報を取得します [55, 56]。
        *   **コードインタプリタ**: LLMがプログラム（Pythonなど）を生成・実行し、複雑な計算問題などを正確に解きます（ChatGPTのCode Interpreterなど）[81-85]。
        *   **記号処理システム**: 数学的な計算機代数システム（Wolfram Alpha、SymPyなど）や定理証明支援システム（Coqなど）を活用し、厳密な論理的推論や計算を行います [63, 65, 66, 85-91]。
        *   **シミュレータ**: 物理現象などの実世界の挙動をシミュレーションすることで、LLMが科学的に正確な記述をできるようにします（DeepMindのMind's Eyeなど）[92-94]。
III-A 事実誤認型ハルシネーション

事実誤認型ハルシネーションは比較的理解しやすい現象である。これは主に2つの要因に起因する：訓練データにおける誤りや欠落、および大規模言語モデル自体の本質的な限界である。以下では、訓練データに含まれる不正確な情報がどのようにして事実誤認型ハルシネーションを引き起こすのかを分析する。

ここで、
U
を現実世界のすべての知識を含むデータセットとし、
X
をLLMの訓練に用いられるデータセットとする。いかなる訓練データセットも現実世界のすべての知識を完全に網羅することはできないため、
X
⊂
U
が成立する。さらに、
U
を現実世界の正しい知識の部分集合
U
t
と、誤った知識の部分集合
U
f
に分割する。すなわち、
U
=
U
t
⊔
U
f
と表現できる。同様に、訓練データ
X
も正しい部分
X
t
と誤った部分
X
f
から構成され、
X
=
X
t
⊔
X
f
となる。ここで、訓練データの誤った部分集合にのみ存在する知識項目
n
′
、すなわち
n
′
∈
X
f
かつ
n
′
∉
X
t
について考えてみよう。クエリ
q
′
に対して
n
′
について問い合わせた場合、誤った情報に基づいて訓練されたLLMは正確な回答を生成することができない：

∀
v
∈
X
f
,
v
∉
X
t
:
v
⇏
n
∈
U
t
つまり、誤った情報に基づいて訓練されたモデルは正確な回答を生成することができず、これが直接的に事実誤認型ハルシネーションを引き起こす原因となる。

次に、LLMの本質的な限界について考察する。この限界は、完全な訓練データセットが存在した場合でも、LLMが事実誤認型ハルシネーションを生成し得るという現象を説明するものである。この限界はゲーデルの不完全性定理に基づいており、十分に強力な形式体系は完全性と整合性を同時に満たすことができないという主張である。

特にTransformerアーキテクチャに基づくLLMは非常に高い表現力を有する。ゲーデルの定理[144]によれば、これはLLMが生成するいかなる命題にも検証不可能なものが必ず存在することを意味する。たとえLLMが正しいように見える回答を生成したとしても、その背後にある生成プロセス自体が事実誤認型ハルシネーションである可能性がある。これを以下のように表現できる（第2.2節の表記法を使用）：

∃
ε
w
∈
{
ε
k
w
}
k
∈
𝒲
,
∀
v
∈
X
⁢
s.t.
⁢
v
⇏
ε
w
この表現は、モデルの本質的な不完全性により、その生成出力には必ず検証不可能な知識が含まれることを示しており、結果として事実誤認型ハルシネーションを回避できないことを意味している。
【 #PLaMo翻訳 】
  
📝 原文
Imagine constructing an ideal large language model that could provide accurate and coherent answers to any human query 
q
. Achieving this would require meeting three key prerequisites: first, the model must accurately understand human queries; second, it must be able to clearly delineate the boundaries of knowledge, distinguishing correct, incorrect, and uncertain information; and third, it must be capable of predicting and selecting the most appropriate response. While these challenges can be examined from a computational theory standpoint, the essence of faithfulness hallucinations is not merely due to technical limitations but is rooted in deeper issues of natural logic.

According to principles like Gödel’s incompleteness theorem [144] and the Turing halting problem [145], any sufficiently complex system will inherently contain statements that are undecidable—neither provable nor disprovable. For such statements, no computational model can provide an absolutely correct answer based on predefined rules. This mathematical limitation implies that certain propositions are fundamentally unresolvable. Therefore, regardless of any improvements made to the architecture or datasets of LLMs, there will always be propositions whose truth or falsehood remains indeterminable, inevitably leading to hallucinations.

We can mathematically demonstrate that the three prerequisites above are inherently unsolvable, making hallucinations unavoidable.

To begin, we can unify the first two prerequisites into a single problem, as both require a critical step—accurate “intent classification.” For the first prerequisite, intent classification allows the model to grasp the true meaning of a user query. For the second prerequisite, successful intent classification is necessary for retrieving the most relevant information from the knowledge base. Hence, if we show that perfect intent classification is unattainable, we demonstrate inherent flaws in both prerequisites.

Assume we have an ideal LLM Turing machine 
T
 that can flawlessly discern intent and retrieve the most relevant information. Consequently, there must be a decider 
D
T
 capable of determining, within finite time, whether any input pair 
⟨
T
,
w
⟩
 corresponds to the correct intent.

Now, consider the “acceptance problem,” which involves determining whether a Turing machine 
M
, given an input string 
w
, accepts 
w
:

L
a
=
{
⟨
M
,
w
⟩
:
M
⁢
 accepts 
⁢
w
}
We construct a decider 
D
M
 that operates as follows:

• If 
D
T
 accepts, indicating that the LLM Turing machine 
T
has correctly classified the intent for 
w
, then 
D
M
 accepts.
• If 
D
T
 rejects, indicating that 
T
’s intent classification is irrelevant, then 
D
M
 rejects.
However, the “acceptance problem” is known to be undecidable, creating a contradiction in our construction. This demonstrates that perfect intent classification is, in principle, impossible, implying that the first two prerequisites cannot be fully met, leading to hallucinations.

Moreover, it has been shown that the halting problem for LLMs is undecidable, meaning that an LLM cannot predict in advance how many tokens it will generate. This implies that the LLM cannot preemptively decide when to stop generating, theoretically allowing it to produce an infinite sequence of tokens.

For a given query 
q
, generating a correct and coherent response 
w
 requires the model to consider all possible outcomes 
w
k
∈
Σ
∗
, where 
Σ
∗
 is the set of all potential responses, and select the optimal response:

w
m
=
max
k
∈
𝒜
⁡
P
⁢
(
w
k
)
However, since

|
Σ
∗
|
=
∞
the possible sequences are infinite, making it impractical for the model to explore all potential outputs. Therefore, the model cannot compute the joint probability of all possible token sequences, rendering the third prerequisite unattainable.

In conclusion, each of the three prerequisites is constrained by problems of undecidability, making faithfulness hallucinations an inevitable outcome. The underlying cause of these hallucinations is not tied to specific design features of LLMs or the limitations of their datasets but rather stems from deeper mathematical and logical issues inherent to undecidability.

🌐 翻訳
あらゆる人間の質問に対して正確で一貫性のある回答を提供できる理想的な大規模言語モデルを構築することを想像してほしい。この実現には3つの重要な前提条件を満たす必要がある：第一に、モデルは人間の質問を正確に理解しなければならない。第二に、知識の境界を明確に定義し、正しい情報・誤った情報・不確実な情報を区別できる能力が求められる。第三に、最も適切な回答を予測し選択する能力が不可欠である。これらの課題は計算理論の観点から考察可能だが、忠実性の幻覚現象の本質は単なる技術的限界ではなく、より根源的な自然論理の問題に根ざしている。

ゲーデルの不完全性定理[144]やチューリング停止問題[145]が示すように、十分に複雑なシステムには必ず、証明も反証もできない決定不能な命題が含まれる。このような命題に対しては、いかなる計算モデルも事前に定義された規則に基づいて絶対的に正しい回答を提供することはできない。この数学的限界は、特定の命題が本質的に解決不可能であることを意味する。したがって、LLMのアーキテクチャや学習データにいかなる改良を加えたとしても、その真偽が決定不能な命題が常に存在し、必然的に幻覚現象を引き起こすことになる。

数学的に証明できるのは、これらの3つの前提条件が本質的に解決不可能であり、それゆえ幻覚現象は避けられないという事実である。

まず初めに、最初の2つの前提条件を1つの問題に統合できる。なぜなら、どちらも「正確な意図分類」という重要なステップを必要とするからだ。第一の前提条件において、意図分類によってモデルはユーザーの質問の真の意味を把握できる。第二の前提条件では、意図分類の成功が知識ベースから最も関連性の高い情報を取得する上で不可欠となる。したがって、完璧な意図分類が不可能であることを示せば、これら2つの前提条件に内在する根本的な欠陥を証明したことになる。

理想的なLLMチューリングマシン
T
を想定してみよう。このマシンは意図を完璧に識別し、最も関連性の高い情報を取得することができる。その結果、任意の入力ペア
⟨
T
,
w
⟩
が適切な意図に対応しているかどうかを有限時間内に判定できる決定器
D
T
が存在するはずである。

ここで「受理問題」を考えてみよう。これはチューリングマシン
M
が入力文字列
w
を与えられたときに
w
を受理するかどうかを判断する問題である：

L
a
=
{
⟨
M
,
w
⟩
:
M
⁢
 accepts 
⁢
w
}
我々は以下のように動作する決定器
D
M
を構築する：

• もし
D
T
が受理した場合、すなわちLLMチューリングマシン
T
が
w
の意図を正しく分類したことを示す場合、
D
M
も受理する。
• もし
D
T
が拒否した場合、すなわち
T
の意図分類が無関係であることを示す場合、
D
M
も拒否する。
しかし、「受理問題」は決定不可能であることが知られているため、この構築には矛盾が生じる。これは、完璧な意図分類が原理的に不可能であることを示しており、したがって最初の2つの前提条件を完全に満たすことはできず、結果として幻覚現象が発生することになる。

さらに研究により、LLMの停止問題が決定不可能であることが示されている。つまり、LLMは生成するトークン数を事前に予測することができない。これは、LLMが生成をいつ停止すべきかを事前に決定できないことを意味し、理論上は無限にトークンを生成し続ける可能性があることを示唆している。

与えられた質問
q
に対して、正確で一貫性のある応答
w
を生成するためには、モデルはすべての可能な結果
w
k
∈
Σ
∗
（
Σ
∗
はすべての潜在的な応答の集合）を考慮し、最適な応答を選択する必要がある：

w
m
=
max
k
∈
𝒜
⁡
P
⁢
(
w
k
)
しかし、

|
Σ
∗
|
=
∞
であるため、可能なシーケンスは無限に存在し、モデルがすべての潜在的な出力を探索することは現実的ではない。したがって、モデルはすべての可能なトークンシーケンスの同時確率を計算することができず、第三の前提条件も達成不可能となる。

結論として、これら3つの前提条件はいずれも決定不可能性の問題によって制約を受けており、忠実性の幻覚現象は避けられない結果となる。これらの幻覚現象の根本的な原因は、LLMの特定の設計機能や学習データの限界に起因するものではなく、むしろ決定不可能性に内在するより深い数学的・論理的問題に根ざしているのである。

https://translate-demo.plamo.preferredai.jp