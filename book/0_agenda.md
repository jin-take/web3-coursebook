# Web3 Study 目次

本書は、Web3とBlockchainの基礎から、Wallet、Transaction、Smart Contract、DeFi、Security、実務上のRisk判断までを段階的に学ぶための検定対策テキストです。章タイトルを選択すると、各章のページへ移動できます。

## 重要度

- **最重要**：仕組みの理解と安全な利用に必須となる分野
- **重要**：ほかの章を理解する前提となる分野
- 表記なし：全体像と応用力を身に付ける分野

## 目次

1. [第1章 Web3と分散型システム](1_web3_and_decentralized_systems.md)
   - Webの発展とWeb3
   - 分散型システム
   - Blockchainの位置付け

2. [第2章 ブロックチェーンの基本構造](2_basic_structure_of_blockchain.md) **重要**
   - Block
   - Chain構造
   - Merkle Tree

3. [第3章 ハッシュと暗号技術](3_hashing_and_cryptography.md) **重要**
   - Hash関数
   - BlockchainとHash
   - 暗号技術の役割

4. [第4章 公開鍵・秘密鍵・デジタル署名](4_public_keys_private_keys_and_digital_signatures.md) **最重要**
   - 公開鍵暗号
   - Digital Signature
   - 所有とControl

5. [第5章 ウォレットとアドレス](5_wallets_and_addresses.md) **最重要**
   - WalletとBlockchain Address
   - Walletの分類
   - Seed Phrase、HD Wallet、Multi-Signature、MPC

6. [第6章 トランザクション](6_transactions.md) **最重要**
   - Transactionの構成
   - 生成からFinalityまでの流れ
   - Transactionの状態と二重支払い

7. [第7章 ノードとP2Pネットワーク](7_nodes_and_p2p_networks.md)
   - Full Node、Validator、Miner、Light Client
   - P2P NetworkとData伝播
   - 検証、Data共有、障害耐性

8. [第8章 コンセンサス](8_consensus.md) **重要**
   - ConsensusとFinality
   - Proof of Work
   - Proof of Stake

9. [第9章 ブロックチェーンの状態とデータ](9_blockchain_state_and_data.md)
   - Transaction、Block、State、History
   - UTXO ModelとAccount Model
   - Blockchain Explorerの読み方

10. [第10章 スマートコントラクト](10_smart_contracts.md) **最重要**
    - Code、State、Contract Address
    - Read、Write、Function、Parameter、Event
    - Upgrade、Oracle、Smart Contractの限界

11. [第11章 トークンとデジタル資産](11_tokens_and_digital_assets.md)
    - Native AssetとToken
    - Fungible TokenとNFT
    - Balance、Supply、Mint、Burn、Approval

12. [第12章 ステーキング・DeFiの基本原理](12_fundamentals_of_staking_and_defi.md)
    - Staking、Delegation、Reward、Slashing
    - DEXとLending
    - Liquidity、AMM、Slippage、Liquidation

13. [第13章 スケーラビリティとクロスチェーン](13_scalability_and_cross_chain.md)
    - Layer 1とLayer 2
    - Rollup、Data Availability、Settlement
    - BridgeとCross-chain Risk

14. [第14章 Web3セキュリティ](14_web3_security.md) **最重要**
    - 秘密鍵漏洩、Phishing、誤署名、誤送金
    - Smart Contract Risk
    - Consensus Attack、MEV、Bridge Risk

15. [第15章 Web3の実務・リスク・総合理解](15_web3_practice_risk_and_comprehensive_understanding.md)
    - Web3サービスの全体構造
    - Transactionの追跡
    - Custody、Contract、Protocol、Operational Risk

## 推奨学習順序

基本的には、**第1章から第15章まで順番に学習**することを推奨します。特に第2〜6章は、後半のSmart Contract、DeFi、Securityを理解する前提です。

復習時は、次の目的別順序も利用できます。

- **Blockchainの仕組みを復習する**：第2章 → 第3章 → 第7章 → 第8章 → 第9章
- **WalletとTransactionを復習する**：第4章 → 第5章 → 第6章
- **Smart ContractとDeFiを復習する**：第10章 → 第11章 → 第12章 → 第13章
- **Securityと実務を復習する**：第14章 → 第15章
