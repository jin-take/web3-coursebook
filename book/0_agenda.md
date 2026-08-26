# Web3 Study 目次

本書は、Web3とBlockchainの基礎から、Wallet、Transaction、Smart Contract、DeFi、Security、実務上のRisk判断までを段階的に説明する教科書です。

個別の用語を暗記するのではなく、各技術がなぜ必要とされ、どのような仕組みで動き、ほかの要素とどのようにつながっているかを理解できる構成としています。章タイトルを選択すると、各章の本文へ移動できます。

## 目次

1. [第1章 Web3と分散型システム](1_web3_and_decentralized_systems.md)
   - Webの発展とWeb3
   - 中央集権型と分散型の違い
   - Blockchain、Wallet、Token、Smart Contract、dAppの関係

2. [第2章 ブロックチェーンの基本構造](2_basic_structure_of_blockchain.md)
   - 分散型台帳とBlock
   - Previous Block HashによるChain構造
   - Merkle Treeによる効率的な検証

3. [第3章 ハッシュと暗号技術](3_hashing_and_cryptography.md)
   - Hash関数の性質
   - Data識別と改ざん検知
   - 暗号化、Hash、認証、完全性の違い

4. [第4章 公開鍵・秘密鍵・デジタル署名](4_public_keys_private_keys_and_digital_signatures.md)
   - 公開鍵暗号と鍵Pair
   - Digital Signatureの生成と検証
   - 秘密鍵による操作権限と、法的な所有との違い

5. [第5章 ウォレットとアドレス](5_wallets_and_addresses.md)
   - Walletの役割とBlockchain Address
   - Hot・Cold、Custodial・Non-Custodialなどの分類
   - Seed Phrase、HD Wallet、Multi-Signature、MPCによる鍵管理

6. [第6章 トランザクション](6_transactions.md)
   - Transactionの構成要素
   - 作成、署名、Broadcast、検証、Blockへの取り込み
   - Confirmation、Finality、失敗、二重支払いの防止

7. [第7章 ノードとP2Pネットワーク](7_nodes_and_p2p_networks.md)
   - Full Node、Archive Node、Validator、Miner、Light Client
   - P2P NetworkにおけるTransactionとBlockの伝播
   - RPCを通じたApplicationとNodeの接続

8. [第8章 コンセンサス](8_consensus.md)
   - 分散環境における合意形成
   - Proof of Workの計算競争と経済的安全性
   - Proof of StakeのStake、Validator、Reward、Slashing
   - ForkとFinality

9. [第9章 ブロックチェーンの状態とデータ](9_blockchain_state_and_data.md)
   - Transaction、Block、History、Stateの関係
   - UTXO ModelとAccount Model
   - Blockchain Explorerを用いた記録の確認

10. [第10章 スマートコントラクト](10_smart_contracts.md)
    - CodeとStateを持つProgramとしてのContract
    - Read、Write、Function、Parameter、Event
    - 決定論的実行、実行Cost、Oracle、Upgrade、管理権限

11. [第11章 トークンとデジタル資産](11_tokens_and_digital_assets.md)
    - Native AssetとSmart Contract Tokenの違い
    - Fungible TokenとNon-Fungible Token
    - Balance、Supply、Mint、Burn、Approval、Allowance

12. [第12章 ステーキング・DeFiの基本原理](12_fundamentals_of_staking_and_defi.md)
    - Staking、Delegation、Reward、Slashing
    - Smart Contractによる金融機能
    - DEX、Liquidity Pool、AMM、Lending、Collateral、Liquidation

13. [第13章 スケーラビリティとクロスチェーン](13_scalability_and_cross_chain.md)
    - 処理性能、分散性、SecurityのTrade-off
    - Layer 1、Layer 2、Rollup、Data Availability、Settlement
    - Bridge、Cross-chain Message、異なる信頼Model

14. [第14章 Web3セキュリティ](14_web3_security.md)
    - 秘密鍵漏洩、Phishing、誤署名、誤送金
    - Smart ContractのAccess ControlとBusiness Logic
    - Consensus Attack、MEV、Oracle、Bridge、GovernanceのRisk

15. [第15章 Web3の実務・リスク・総合理解](15_web3_practice_risk_and_comprehensive_understanding.md)
    - User、Wallet、Application、Node、Blockchainのつながり
    - 一つの操作が署名され、検証され、Stateへ反映されるまで
    - Custody、Contract、Protocol、Infrastructure、Operational Risk
    - Web3における信頼と検証の考え方

## 本書の読み方

第1章から順番に読むことで、Web3を構成する要素を一つの流れとして理解できます。

前半では、Blockchain、Hash、鍵、Wallet、Transaction、Node、Consensusといった基盤を扱います。中盤では、State、Smart Contract、Token、Staking、DeFiを説明します。後半では、Layer 2、Cross-chain、Security、実務上のRisk判断へと範囲を広げます。

各章では、用語の定義だけでなく、次の観点を本文の中で説明します。

- その仕組みが必要とされる理由
- どのような順序で処理されるか
- 何を保証し、何を保証しないか
- ほかの技術とどのように関係するか
- 利用時にどのようなRiskが生じるか

BitcoinやEthereumなどの固有名詞は、普遍的な仕組みを理解するための具体例として扱います。変更されやすい数値や一時的な仕様ではなく、長期的に利用できる概念と大枠の構造を中心に説明します。
