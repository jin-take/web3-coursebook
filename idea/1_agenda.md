# Web3 Study Agneda

## 第1章 Web3と分散型システム
### 1.1 Webの発展とWeb3
#### 1.1.1 Web1・Web2・Web3
#### 1.1.2 中央集権型と分散型
#### 1.1.3 Web3における所有と参加
#### 1.1.4 Trustlessという考え方
### 1.2 分散型システム
#### 1.2.1 単一管理者を持たないシステム
#### 1.2.2 Peer-to-Peer
#### 1.2.3 Permissionless / Permissioned
#### 1.2.4 分散化のメリットと代償
### 1.3 ブロックチェーンの位置付け
#### 1.3.1 分散型台帳
#### 1.3.2 BlockchainとWeb3の関係
#### 1.3.3 オンチェーンとオフチェーン
#### 1.3.4 ブロックチェーンが適する領域
## 第2章 ブロックチェーンの基本構造 ★重要
### 2.1 ブロック
#### 2.1.1 ブロックとは
#### 2.1.2 ブロックヘッダー
#### 2.1.3 トランザクション
#### 2.1.4 ブロックの識別
### 2.2 チェーン構造
#### 2.2.1 Previous Block Hash
#### 2.2.2 Genesis Block
#### 2.2.3 ブロックの連結
#### 2.2.4 改ざん耐性
### 2.3 Merkle Tree
#### 2.3.1 Merkle Treeの構造
#### 2.3.2 Merkle Root
#### 2.3.3 データ存在証明
#### 2.3.4 検証効率
## 第3章 ハッシュと暗号技術 ★重要
### 3.1 ハッシュ関数
#### 3.1.1 ハッシュとは
#### 3.1.2 固定長出力
#### 3.1.3 一方向性
#### 3.1.4 衝突耐性
### 3.2 ブロックチェーンとハッシュ
#### 3.2.1 データ識別
#### 3.2.2 改ざん検知
#### 3.2.3 ブロックの連結
#### 3.2.4 Transaction Hash
### 3.3 暗号技術の役割
#### 3.3.1 暗号化とハッシュの違い
#### 3.3.2 認証
#### 3.3.3 完全性
#### 3.3.4 暗号技術が保証するもの
## 第4章 公開鍵・秘密鍵・デジタル署名 ★最重要
### 4.1 公開鍵暗号
#### 4.1.1 Private Key
#### 4.1.2 Public Key
#### 4.1.3 Key Pair
#### 4.1.4 公開可能な情報と秘密にすべき情報
### 4.2 デジタル署名
#### 4.2.1 Signing
#### 4.2.2 Verification
#### 4.2.3 秘密鍵と署名の関係
#### 4.2.4 デジタル署名が証明するもの
### 4.3 所有とコントロール
#### 4.3.1 秘密鍵を持つ意味
#### 4.3.2 秘密鍵を失う意味
#### 4.3.3 秘密鍵漏洩
#### 4.3.4 「Not your keys, not your coins」の意味
## 第5章 ウォレットとアドレス ★最重要
### 5.1 Wallet
#### 5.1.1 Walletとは
#### 5.1.2 Blockchain Address
#### 5.1.3 WalletとBlockchainの関係
#### 5.1.4 残高はどこに存在するのか
### 5.2 Walletの分類
#### 5.2.1 Hot / Cold
#### 5.2.2 Custodial / Non-Custodial
#### 5.2.3 Software / Hardware
#### 5.2.4 分類軸の違い
### 5.3 鍵管理
#### 5.3.1 Seed Phrase
#### 5.3.2 HD Wallet
#### 5.3.3 Multi-Signature
#### 5.3.4 MPC
#### 5.3.5 鍵管理とリスク
## 第6章 トランザクション ★最重要
### 6.1 Transactionとは
#### 6.1.1 Transactionの役割
#### 6.1.2 Sender / Recipient
#### 6.1.3 Value
#### 6.1.4 Fee
### 6.2 Transactionの流れ
#### 6.2.1 Transaction生成
#### 6.2.2 Signing
#### 6.2.3 Broadcast
#### 6.2.4 Validation
#### 6.2.5 Block Inclusion
#### 6.2.6 Confirmation / Finality
### 6.3 Transactionの状態
#### 6.3.1 未確定
#### 6.3.2 成功
#### 6.3.3 失敗
#### 6.3.4 Transaction Hash
#### 6.3.5 二重支払い
## 第7章 ノードとP2Pネットワーク
### 7.1 Node
#### 7.1.1 Nodeとは
#### 7.1.2 Full Node
#### 7.1.3 Validator / Miner
#### 7.1.4 Light Client
### 7.2 P2P Network
#### 7.2.1 Peer
#### 7.2.2 データ伝播
#### 7.2.3 Transaction伝播
#### 7.2.4 Block伝播
### 7.3 Blockchain Network
#### 7.3.1 ネットワーク参加者
#### 7.3.2 検証
#### 7.3.3 データ共有
#### 7.3.4 障害耐性
## 第8章 コンセンサス ★重要
### 8.1 Consensus
#### 8.1.1 Consensusとは
#### 8.1.2 なぜ合意形成が必要なのか
#### 8.1.3 Byzantine Fault
#### 8.1.4 Finality
### 8.2 Proof of Work
#### 8.2.1 Mining
#### 8.2.2 計算資源
#### 8.2.3 インセンティブ
#### 8.2.4 攻撃耐性
### 8.3 Proof of Stake
#### 8.3.1 Stake
#### 8.3.2 Validator
#### 8.3.3 Reward
#### 8.3.4 Slashing
#### 8.3.5 PoWとの思想的な違い
## 第9章 ブロックチェーンの状態とデータ
### 9.1 Blockchain Data
#### 9.1.1 Transaction
#### 9.1.2 Block
#### 9.1.3 State
#### 9.1.4 History
### 9.2 Accountと残高
#### 9.2.1 Account
#### 9.2.2 Balance
#### 9.2.3 UTXOという考え方
#### 9.2.4 Account Modelという考え方
### 9.3 Explorer
#### 9.3.1 Explorerとは
#### 9.3.2 Transactionの確認
#### 9.3.3 Addressの確認
#### 9.3.4 Blockの確認
#### 9.3.5 オンチェーン情報の読み方
## 第10章 スマートコントラクト ★最重要
### 10.1 Smart Contract
#### 10.1.1 Smart Contractとは
#### 10.1.2 CodeとState
#### 10.1.3 Contract Address
#### 10.1.4 実行条件
### 10.2 Contract Interaction
#### 10.2.1 Read
#### 10.2.2 Write
#### 10.2.3 Function
#### 10.2.4 Parameter
#### 10.2.5 Event
### 10.3 Smart Contractの性質
#### 10.3.1 自動実行
#### 10.3.2 決定論
#### 10.3.3 不変性とアップグレード
#### 10.3.4 外部データとOracle
#### 10.3.5 Smart Contractの限界
## 第11章 トークンとデジタル資産
### 11.1 Native AssetとToken
#### 11.1.1 Native Asset
#### 11.1.2 Token
#### 11.1.3 両者の違い
#### 11.1.4 Token Contract
### 11.2 Fungibility
#### 11.2.1 Fungible Token
#### 11.2.2 Non-Fungible Token
#### 11.2.3 Ownership
#### 11.2.4 Transfer
### 11.3 Tokenの仕組み
#### 11.3.1 Balance
#### 11.3.2 Supply
#### 11.3.3 Mint
#### 11.3.4 Burn
#### 11.3.5 Approval / Allowance
## 第12章 ステーキング・DeFiの基本原理
### 12.1 Staking
#### 12.1.1 Stakingの目的
#### 12.1.2 Validator
#### 12.1.3 Delegation
#### 12.1.4 Reward
#### 12.1.5 Slashing
### 12.2 DeFi
#### 12.2.1 DeFiとは
#### 12.2.2 Smart Contractによる金融機能
#### 12.2.3 DEX
#### 12.2.4 Lending
### 12.3 Liquidity
#### 12.3.1 Liquidity
#### 12.3.2 Liquidity Pool
#### 12.3.3 AMM
#### 12.3.4 Slippage
#### 12.3.5 Collateral / Liquidation
## 第13章 スケーラビリティとクロスチェーン
### 13.1 Scalability
#### 13.1.1 処理能力
#### 13.1.2 分散性とのトレードオフ
#### 13.1.3 Layer 1
#### 13.1.4 Layer 2
### 13.2 Layer 2の考え方
#### 13.2.1 オフチェーン処理
#### 13.2.2 Rollup
#### 13.2.3 Data Availability
#### 13.2.4 Settlement
### 13.3 Cross-chain
#### 13.3.1 異なるBlockchain間の通信
#### 13.3.2 Bridge
#### 13.3.3 Lock / Mint
#### 13.3.4 Burn / Mint
#### 13.3.5 Cross-chain Risk
## 第14章 Web3セキュリティ ★最重要
### 14.1 セキュリティの基本
#### 14.1.1 秘密鍵漏洩
#### 14.1.2 Phishing
#### 14.1.3 誤署名
#### 14.1.4 誤送金
### 14.2 Smart Contract Risk
#### 14.2.1 Access Control
#### 14.2.2 Business Logic
#### 14.2.3 Reentrancy
#### 14.2.4 Oracle Risk
#### 14.2.5 External Call
### 14.3 Blockchain特有のリスク
#### 14.3.1 Consensus Attack
#### 14.3.2 Front Running / MEV
#### 14.3.3 Bridge Risk
#### 14.3.4 Protocol Risk
#### 14.3.5 Human Error
## 第15章 Web3の実務・リスク・総合理解
### 15.1 Web3サービスの構造
#### 15.1.1 User
#### 15.1.2 Wallet
#### 15.1.3 Blockchain
#### 15.1.4 Smart Contract
#### 15.1.5 Node / Infrastructure
### 15.2 Transactionを追跡する
#### 15.2.1 Walletで署名
#### 15.2.2 NetworkへBroadcast
#### 15.2.3 Nodeによる検証
#### 15.2.4 Consensus
#### 15.2.5 State更新
### 15.3 Web3におけるリスク判断
#### 15.3.1 TrustとVerification
#### 15.3.2 Custody Risk
#### 15.3.3 Smart Contract Risk
#### 15.3.4 Protocol Risk
#### 15.3.5 Operational Risk