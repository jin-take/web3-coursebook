# 第11章 トークンとデジタル資産

ブロックチェーン上のデジタル資産には、ネットワーク自身が扱う**Native Asset**と、**Smart Contract**が定義するTokenがあります。本章では両者の違い、代替可能性、残高や発行量を管理する仕組みを学びます。

## この章の学習目標

- Native Asset、Token、Wrapped Assetを技術的な管理主体から区別できる。
- Fungible TokenとNFTでOwnershipとTransferの表現がどう異なるか説明できる。
- Mint、Burn、Supply、Approvalが資産価値と安全性へ与える影響を評価できる。

> **最重要ポイント:** Token名やSymbolは一意ではありません。**Chain IDとToken Contract Addressの組み合わせ**で資産を識別します。

## 11.1 Native AssetとToken

### 11.1.1 Native Asset

Native Assetは、ブロックチェーンのプロトコル自体が残高と移転を管理する資産です。Transaction Feeの支払い、**Validator**への報酬、ステーキングなど、ネットワーク運用に直接使われます。

Native Assetを送る処理はプロトコルの基本機能であり、通常はToken Contractを呼び出しません。ただし、別チェーン上ではブリッジされたTokenとして表現されることがあります。

### 11.1.2 Token

Tokenは、Smart Contractなどによって発行・管理されるデジタル資産です。残高、移転、発行、消却、権限制御といった規則がContractのCodeと**State**に定義されます。

同じチェーン上に多様なTokenを作れますが、名称やシンボルは重複可能です。資産を一意に見分けるには、チェーンと**Contract Address**を確認します。

### 11.1.3 両者の違い

Native Assetはプロトコル組み込み、TokenはContract上の記録という違いがあります。Tokenを送るTransactionでも、実行Feeには通常そのチェーンのNative Assetが必要です。

ウォレットでは似た残高表示になりますが、障害や停止権限、発行ルールは異なります。Wrapped Native AssetはNative Assetと価格連動を目指すTokenであり、技術的には別資産です。

### 11.1.4 Token Contract

Token Contractは、Addressごとの残高と、移転・承認・発行などの関数を提供します。共通規格へ準拠することで、ウォレットや取引所が同じインターフェースで多くのTokenを扱えます。

規格準拠は価値や安全性の保証ではありません。管理者権限、アップグレード可否、送金制限、手数料、ブラックリスト機能などCode固有の挙動を確認します。

## 11.2 Fungibility

### 11.2.1 Fungible Token

**Fungible Token**は、同じ種類・同じ数量であれば各単位を交換可能なTokenです。通貨、ポイント、ガバナンス投票権など、数量で管理する用途に適します。

代替可能性はContract上の数量表現を指し、市場で常に同じ価値を持つことまでは保証しません。凍結や履歴分析によって、実務上の受容性が変わることもあります。

### 11.2.2 Non-Fungible Token

**Non-Fungible Token**（NFT）は、Token IDごとに区別される非代替性Tokenです。デジタルアイテム、会員証、証明書、現実資産に関する記録などに利用できます。

NFTが示す権利はContractと関連規約によって決まります。画像ファイル自体、著作権、商標権、現物所有権が自動的に移転するとは限りません。

### 11.2.3 Ownership

TokenのOwnershipは、ContractのState上で特定Addressに残高またはToken IDが関連付けられている状態です。対応する鍵を使って、規則の範囲でTransferや承認を行えます。

複数署名WalletやContractが所有者になることもあります。技術的な操作権限と法的・経済的な所有権を区別して評価します。

### 11.2.4 Transfer

Transferは、Token ContractのStateを更新し、送信元から宛先へ残高またはToken IDを移す処理です。成功すると通常はTransfer Eventが発生し、ウォレットやExplorerが表示へ反映します。

誤ったAddressへのTransferは原則として取り消せません。送信制限や受取側Contractの非対応で資産を動かせなくなる場合もあります。

## 11.3 Tokenの仕組み

### 11.3.1 Balance

Fungible Tokenでは、Addressから数量への対応表としてBalanceを管理します。NFTでは、Token IDからOwnerへの対応や、Ownerが持つ個数を管理します。

表示上の小数桁はContractが提供するメタデータであり、State内部は整数で記録されます。桁数を誤ると数量を大きく取り違えるため注意します。

### 11.3.2 Supply

Supplyは、発行済みTokenの総量を表します。上限固定、継続発行、アルゴリズムによる増減など、設計はTokenごとに異なります。

Total Supplyと市場で実際に流通するCirculating Supplyは同じとは限りません。ロック、運営保有、ブリッジ保管分などを含むか確認します。

### 11.3.3 Mint

Mintは、新しいTokenを作成してSupplyと特定AddressのBalanceを増やす処理です。誰が、どの条件で、どの上限までMintできるかは資産価値と安全性に直結します。

管理鍵が無制限Mint権限を持つ場合、その鍵の漏洩や運営者の判断で希薄化するリスクがあります。

### 11.3.4 Burn

Burnは、Tokenを使用不能にし、通常はSupplyを減らす処理です。利用者が自分のTokenを消却する場合や、プロトコルがFeeの一部を消却する場合があります。

単に誰も使えないAddressへ送る方式では、Total Supplyの計算上減少しないこともあります。Code上の定義を確認します。

### 11.3.5 Approval / Allowance

**Approval**は、所有者が別のAddressやContractへ、自分のTokenを一定量まで移動する権限を与える操作です。**Allowance**はその許可量を表します。DEXなどが利用者に代わってTokenを受け取る際に使われます。

無制限Approvalを残すと、承認先Contractが侵害された場合に残高を失う可能性があります。利用額だけを承認し、不要になった権限はRevokeします。

## 検定対策：Tokenの権利と実装を読む

### Native Asset・Token・Wrapped Asset

| 種類 | 管理する層 | Fee支払い | 主な追加リスク |
|---|---|---|---|
| Native Asset | Blockchain Protocol | 原則として利用できる | Consensus、Protocol |
| Token | Token Contract | 通常はNative Assetが別途必要 | Contract、Admin、発行権限 |
| Wrapped Native Asset | Custody / Contract | 通常は直接利用不可 | 交換比率、保管Contract |
| Bridged Token | Bridge Contract / 発行者 | 移動先ChainのNative Asset | Bridge、元Chain、償還能力 |

Wrapped Assetは、元資産を預けて同価値を目指すTokenを発行したものです。価格が同じであることをProtocolが必ず保証するのではなく、**元資産へ償還できる期待**が価格を支えます。

### Token Standardが定めるもの

Token Standardは、`balanceOf`、`transfer`、`approve` など共通InterfaceやEvent形式を定め、WalletやDEXとの互換性を作ります。しかし、次の内容はStandardだけでは保証されません。

- 発行上限やMint権限が安全であること。
- Transfer時に追加FeeやBlacklist処理がないこと。
- Tokenが現実資産や法的権利に裏付けられること。
- Priceが安定すること、または換金先が存在すること。
- CodeにBugやUpgrade Riskがないこと。

**規格準拠はInterface互換性であり、信用保証ではありません。**

### NFTのMetadataと保存場所

NFT Contractは、Token IDとOwnerに加え、Metadata URIを保持することがあります。URIが指すJSONに名称、画像URL、属性が記載されます。画像やMetadataがHTTP Serverや変更可能なCloud Storageにある場合、Contractが不変でも表示内容は変更・消失し得ます。

分散Storageを使う場合も、Content IDが固定されているか、Dataを長期保持するPinningや費用があるかを確認します。NFT OwnershipとMedia DataのAvailabilityは別問題です。

### Approvalの安全な運用

Allowanceは「一度の支払い」ではなく、承認先が将来実行できる権限です。無制限Approvalは再承認のFeeを省けますが、承認先の脆弱性やUpgradeで残高全体が危険になります。

署名だけでAllowanceを設定するPermit型機能では、On-chain Approval Transactionを省ける一方、Domain、Chain、期限、Nonceを確認しないとPhishing署名に悪用されます。**Transactionでなくても資産移転権限を与える署名が存在します。**

### Token価値を評価する情報

Supply Schedule、発行者保有比率、Vesting、Mint / Freeze権限、Liquidity、償還条件、収益や利用権の根拠を確認します。Market Capitalizationは一般にPriceとCirculating Supplyの積ですが、低Liquidityでは少額取引のPriceを全Supplyへ掛けた数字に過ぎません。

### 確認問題

1. 同じSymbolを持つTokenは、必ず同じ資産である。正しいか。
2. NFTを取得すると、画像の著作権も必ず移転するか。
3. Unlimited Approvalの主なRiskを述べよ。

#### 解答と解説

1. **誤り。** ChainとContract Addressで識別する。同じSymbolのContractは誰でも作成できる。
2. **必ずしも移転しない。** Contract、利用規約、法的契約が定める権利を確認する。
3. **承認先が侵害・悪用されたとき、現在および将来の残高を上限なく移転される可能性。**

## まとめ

Native AssetとTokenは見た目が似ていても、管理主体と実行経路が異なります。Tokenを評価する際は、Contract Address、発行・消却権限、Transfer制限、Approvalの残存、Tokenが表す権利を確認しましょう。
