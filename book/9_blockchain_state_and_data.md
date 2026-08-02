# 第9章 ブロックチェーンの状態とデータ

ブロックチェーンには、取引の履歴と、その履歴を順に適用した現在の状態があります。本章ではTransaction、Block、**State**、**History**の関係を整理し、エクスプローラーで**オンチェーン**情報を読む方法を学びます。

## この章の学習目標

- Transaction、Block、History、Stateの関係を状態遷移として説明できる。
- UTXO ModelとAccount Modelの残高・二重支払い防止方法を比較できる。
- Explorerの表示をOn-chain事実と外部Annotationに分けて読める。

> **最重要ポイント:** **Historyは状態変更の入力列、Stateはその入力を順に適用した現在結果**です。残高はWalletの内部ではなくStateから導かれます。

## 9.1 Blockchain Data

### 9.1.1 Transaction

Transactionは状態変更の入力です。誰がどの操作を要求し、どの署名で承認し、どの手数料条件を指定したかが記録されます。

一つのTransactionが複数の残高やコントラクト状態を変えることもあります。入力データだけでなく、実行結果や発生したEventを合わせて読む必要があります。

### 9.1.2 Block

Blockは、合意された順序で並ぶTransactionの集合です。ヘッダーには親ブロック、Transaction集合の要約、状態の要約、時刻や提案者に関する情報などが含まれます。

Transactionの順序が変わると実行結果も変わり得ます。Blockはデータをまとめるだけでなく、状態遷移の順序を確定する単位です。

### 9.1.3 State

Stateは、特定のブロック時点における残高、コントラクトの保存値、連番などの現在値です。ノードは前のStateへBlock内のTransactionを順に適用して新しいStateを計算します。

多くのチェーンでは状態全体を要約するルートハッシュをブロックへ記録します。ノードごとの計算結果が一致することで、同じ状態へ到達したと確認できます。

### 9.1.4 History

Historyは、**Genesis Block**から現在までに確定したBlockとTransactionの列です。現在残高だけでは分からない「どの操作によって今の状態になったか」を検証できます。

全履歴を保存するには大きな容量が必要です。一部のノードは検証済みの古い中間状態を削除し、Archive Nodeが過去の任意時点への照会を提供します。

## 9.2 Accountと残高

### 9.2.1 Account

Accountは、アドレスで識別され、資産や状態と関連付けられる主体です。利用者の鍵で操作する外部所有アカウントと、コードによって動作するコントラクトアカウントを区別するチェーンもあります。

アドレスは必ずしも実在の一人と一対一ではありません。一人が複数アドレスを持ち、複数人が一つのアカウントを共同管理することもあります。

### 9.2.2 Balance

Balanceは、ある時点でアドレスが利用可能な資産量です。ネイティブ資産の残高はプロトコルのStateに、トークン残高はToken ContractのStateに記録されることが一般的です。

ウォレット表示では、小数桁、未確定取引、ステーキング中資産などの扱いが異なる場合があります。用途に応じて「総量」「利用可能量」「確定量」を区別します。

### 9.2.3 UTXOという考え方

**UTXO**（Unspent Transaction Output）モデルでは、過去のTransactionが作成した未使用の出力を資産の単位として管理します。送金時は一つ以上のUTXOを入力として全額消費し、宛先分と必要なら自分へのお釣りを新しい出力として作ります。

同じUTXOを二度使えないことが**二重支払い**防止の基礎です。残高は、そのアドレスの鍵で使用できるUTXOの合計として計算されます。

### 9.2.4 Account Modelという考え方

**Account Model**では、各アカウントに残高と連番などを持たせ、Transactionによって値を直接増減します。銀行口座に近い見方ができ、スマートコントラクトの複雑な状態を表現しやすい方式です。

同一アカウントからのTransaction順序はNonceなどの連番で管理します。UTXOとAccount Modelはデータ構造や並列処理、プライバシーの特性が異なります。

## 9.3 Explorer

### 9.3.1 Explorerとは

Blockchain Explorerは、ノードから取得したオンチェーンデータを検索・表示するWebサービスです。Tx Hash、Address、Block HashやBlock Numberから、記録された状態を確認できます。

Explorerの画面は便利な解釈レイヤーであり、ブロックチェーンそのものではありません。重要な確認では複数Explorerや自分のノードと照合します。

### 9.3.2 Transactionの確認

Transaction画面では、成功・失敗、確認数、送信元、宛先、Value、Fee、入力データ、Eventを確認します。Token Transfer欄はEventから抽出された表示である場合が多く、実際の状態差分と一致するかに注意します。

失敗時はエラー理由や消費した計算量を調べます。文字列が表示されない場合でも、呼び出した関数や内部実行から原因を追跡できます。

### 9.3.3 Addressの確認

Address画面では、ネイティブ資産残高、Token残高、送受信履歴、コントラクトかどうかを確認できます。大量に送付された未知のTokenやNFTは、価値があるとは限らず、誘導目的のスパムの場合があります。

アドレスへラベルが表示されても、Explorer運営者による推定情報かもしれません。オンチェーン事実と外部の帰属情報を区別します。

### 9.3.4 Blockの確認

Block画面では、Block Number、Hash、Parent Hash、時刻、提案者、Transaction数、使用された計算量などを確認します。対象TransactionがどのBlockの何番目に含まれるかも追跡できます。

最新Block付近では一時的な分岐の影響を受けるため、正規チェーン上に残っているかと**Finality**を確認します。

### 9.3.5 オンチェーン情報の読み方

まず対象チェーンとネットワークを確認し、次にTx HashやAddressなど一次識別子で検索します。そのうえで、状態、ブロック時刻、送信元・宛先、Value、Fee、関数、Eventの順に事実を分解します。

表示されたトークン価格、アドレス所有者名、説明文などは外部データです。オンチェーンで直接証明できる情報と、Explorerが付加した解釈を区別することが分析の基本です。

## 検定対策：State遷移とデータ検証

### State Transition Function

Blockchainの状態更新は、概念的に `新State = F(旧State, Transaction)` と表せます。Block内のTransactionを順番に適用し、途中で無効なら拒否またはRevertします。全Nodeが同じ旧Stateと入力から同じ新Stateを得ることが、Consensus可能な実行の前提です。

Block HeaderにState Rootを含むChainでは、計算結果を短い値で比較できます。Rootが一致すればState全体が高い確率で一致しますが、RootだけからStateの内容を復元することはできません。

### UTXO ModelとAccount Model

| 観点 | UTXO Model | Account Model |
|---|---|---|
| 残高表現 | 未使用Outputの合計 | Account内のBalance |
| 二重支払い防止 | 同じUTXOを再消費できない | NonceとBalanceを検証 |
| お釣り | 新しいOutputとして作る | Balanceを直接減算 |
| 並列性 | 独立UTXOは判定しやすい | 同一Accountの順序依存 |
| Privacy | Address使い分けが比較的自然 | 一つのAccount履歴が結び付きやすい |
| Contract State | Script / 拡張方式による | 複雑な共有Stateを表現しやすい |

UTXOは「硬貨そのもの」ではなく、特定条件を満たす署名等で消費できる過去Transactionの出力です。Account ModelのBalanceも、各Nodeが共有するState上の数値です。

### State PruningとArchive

Full Nodeは全Blockを検証して現在Stateを得た後、過去Block時点の中間Stateを削除することがあります。これをPruningと呼びます。現在のTransaction検証には現Stateがあればよく、任意の過去時点を高速照会するにはArchive Dataが必要です。

Explorerや分析Serviceが過去のBalanceを表示できるのは、Archive NodeやIndexerが履歴を別形式で保持しているためです。

### Explorer調査の手順

1. Mainnet / Testnet、L1 / L2など対象Networkを確認する。
2. Tx HashからStatus、Block、Sender、Recipient、Feeを確認する。
3. Input DataをABIでDecodeし、呼び出しFunctionとParameterを確認する。
4. Receipt、Event、Internal Call、State差分を確認する。
5. Address Label、価格、日本円換算は外部情報として分離する。

同じToken Symbolを持つ偽Contractは作成できます。**Tokenを識別する基本単位は、ChainとContract Addressの組み合わせ**です。

### 確認問題

1. Explorerに表示されるAddress所有者Labelは、Consensusで確定した情報である。正しいか。
2. UTXO Modelで残高はどのように求めるか。
3. Full Nodeが必ず過去の任意時点のStateを即時照会できるとは限らない理由を述べよ。

#### 解答と解説

1. **誤り。** LabelはExplorer等が付加したOff-chain情報である場合が多い。
2. **その鍵の条件で消費できる未使用Outputを合計する。**
3. **Pruningによって古い中間Stateを削除できるため。** 過去照会にはArchive Nodeや履歴からの再計算が必要。

## まとめ

HistoryへTransactionが順序付けて記録され、その結果として現在のStateが導かれます。Explorerはこの関係を読む入口ですが、表示の由来を意識し、Transaction、Block、Addressを相互にたどって検証しましょう。
