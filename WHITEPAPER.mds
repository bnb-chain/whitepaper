# BNB Smart Chain

## Table of Contents

- [BNB Smart Chain](#bnb-smart-chain)
- [Motivation](#motivation)
- [Evolution of BNB Chain](#evolution-of-bnb-chain)
- [Design Principles](#design-principles)
- [Token Economy](#token-economy)
    - [Native Token](#native-token)
    - [Seed Fund](#seed-fund)
    - [Real-Time Burning](#real-time-burning)
- [Consensus and Validator Quorum](#consensus-and-validator-quorum)
    - [Proof of Staked Authority](#proof-of-staked-authority)
    - [Validator Set](#validator-set)
    - [Validator Election](#validator-election)
- [System Contracts](#system-contracts)
- [Reward Distribution](#reward-distribution)
- [Security and Finality](#security-and-finality)
- [Governance](#governance)
- [Slashing and Penalties](#slashing-and-penalties)
    - [Double Sign](#double-sign)
    - [Malicious Fast Finality Vote](#malicious-fast-finality-vote)
    - [Unavailability](#unavailability)
- [Outlook](#outlook)

## Motivation

After its mainnet community launch in April 2019, Beacon Chain has exhibited its high speed and large throughput design. The primary focus of Beacon Chain is to support a native, low-latency, and high-performance decentralized exchange. Among the most requested features is programmable extendibility, specifically the implementation of smart contracts and virtual machine functions. To address this demand, we propose the BNB Smart Chain, running parallel to Beacon Chain, to facilitate a user-friendly smart contract environment.

BNB Smart Chain (BSC) is an EVM-compatible blockchain designed to bring programmability and interoperability to the BNB Chain ecosystem. As part of the broader BNB Chain, BSC aims to deliver a high-throughput, low-latency, and low-cost environment for decentralized applications (dApps) and digital assets. This whitepaper outlines the architecture, mechanisms, and evolutionary journey of BSC. While several years old, we maintain this paper because it continues to serve as a useful reference and an accurate representation of BNB Smart Chain.

## Evolution of BNB Chain

- **Initial Launch and Beacon Chain.** Beacon Chain, launched in April 2019, was designed to support the BNB DEX and exhibited high speed and large throughput. However, its lack of programmability and smart contract functionality posed limitations for developers and users.

- **Introduction of BNB Smart Chain.** To address these limitations, BNB Smart Chain was introduced in 2020, leveraging a parallel blockchain architecture to support smart contracts while retaining high performance for the DEX.

- **BNB Chain Fusion.** In November 2023, the BNB Chain Fusion proposal ([BEP-333](https://github.com/binance-chain/BEPs/blob/master/BEP333.md)) marked a significant shift. This proposal outlined the sunset of the Beacon Chain, merging its functionalities with BSC to create a unified, high-performance blockchain network. This fusion aimed to streamline operations, enhance security, and simplify the user experience on BSC.

- **opBNB.** Launched in 2023, opBNB is an Ethereum Virtual Machine (EVM)-compatible Layer 2 chain based on the Optimism OP Stack. It aims to revolutionize the blockchain industry by providing lower gas fees and democratizing access to blockchain technology.

- **BNB Greenfield.** Greenfield is a novel decentralized data storage network with a native bridge to BNB Smart Chain (BSC), which manages user rights, bucket creation, and file deletion to transform the way users interact with their data.

BNB Chain is a continuously evolving ecosystem with BSC at its core. As a critical financial system, BSC hosts the most crypto asset values. It also serves as the settlement and data availability layer for opBNB and other Layer 2 solutions, ensuring the security of layer2s. Additionally, BSC functions as the smart contract programming platform for Greenfield, facilitating data exchange and circulation within Greenfield.

BSC has evolved significantly from its initial dual-chain architecture, where staking, validation, and governance were delegated to the Beacon Chain. After the BC fusion, BSC transitioned into a fully autonomous chain, undergoing substantial architectural changes.

## Design Principles

Here are the design principles of BSC:

1. **Standalone Blockchain:** Technically, BSC is a standalone blockchain, instead of a layer-2 solution. Most BSC fundamental technical and business functions should be self-contained so that it can run well even if the BC stopped for a short period.

2. **Ethereum Compatibility:** The first practical and widely-used Smart Contract platform is Ethereum. To take advantage of the relatively mature applications and community, BSC chooses to be compatible with the existing Ethereum mainnet. This means most of the dApps, ecosystem components, and toolings will work with BSC and require zero or minimum changes; a BSC node will require similar (or a bit higher) hardware specification and skills to run and operate. The implementation should leave room for BSC to catch up with further Ethereum upgrades.

3. **Staking Involved Consensus and Governance:** Staking-based consensus is more environmentally friendly and leaves more flexible options to community governance. Expectedly, this consensus should enable better network performance over [proof-of-work](https://en.wikipedia.org/wiki/Proof_of_work) blockchain systems, i.e., faster blocking time and higher transaction capacity.

4. **Rapid Blocking Time and Fast Finality:** BSC will implement a fast finality mechanism, allowing for blocks to be finalized within two block confirmations under normal circumstances. This feature, combined with BSC's swift block time of 3 seconds, offers near-instant transaction finality and good user experience.

## Token Economy

BSC, opBNB, and Greenfield share the same token universe for BNB. This defines:

1. BNB can circulate on all networks and flow via a cross-chain communication mechanism.
2. The total circulation of the BNB should be managed across the three networks, i.e., the total effective supply of BNB should be the sum of the token's total effective supply across all networks.

### Native Token

BNB will run on BSC in the same way as ETH runs on Ethereum so that it remains as the "native token" for BSC. This means BNB will be used to:

1. Pay "fees" to deploy smart contracts on BSC.
2. Stake on selected BSC validators and get corresponding rewards.
3. Perform cross-chain operations, such as transferring token assets across BSC, opBNB, and Greenfield.

### Seed Fund

Certain amounts of BNB will be burnt on Beacon Chain and minted on BSC during its genesis stage. This amount is called "Seed Fund" to circulate on BSC after the first block, which will be dispatched to the initial validator set introduced at genesis.

### Real-Time Burning

To speed up the burning process of BNB and make BSC more decentralized, part of the gas fee will be burned. A fixed ratio of the gas fee collected by the validators will be burned in each block. The burning ratio can be governed by the BSC validators.

## Consensus and Validator Quorum

Based on the above design principles, the consensus protocol of BSC is to fulfill the following goals:

1. Blocking time should be shorter than the Ethereum network, e.g., 3 seconds.
2. It requires limited time to confirm the finality of transactions, e.g., around 10-seconds level or shorter.
3. There is no inflation of native token: BNB, the block reward is collected from transaction fees, and it will be paid in BNB.
4. It is compatible with the Ethereum system as much as possible.
5. It allows modern proof-of-stake blockchain network governance.

### Proof of Staked Authority

Although [Proof-of-Work (PoW)](https://en.wikipedia.org/wiki/Proof_of_work) has been recognized as a practical mechanism to implement a decentralized network, it is not friendly to the environment and also requires a large size of participants to maintain the security.

Ethereum and some other blockchain networks, such as MATIC Bor, TOMOChain, GoChain, xDAI, use [Proof-of-Authority (PoA)](https://en.wikipedia.org/wiki/Proof_of_authority) or its variants in different scenarios, including both testnet and mainnet. PoA provides some defense to 51% attack, with improved efficiency and tolerance to certain levels of Byzantine players (malicious or hacked). It serves as an easy choice to pick as the fundamentals.

Meanwhile, the PoA protocol is most criticized for being not as decentralized as PoW, as the validators, i.e., the nodes that take turns to produce blocks, have all the authorities and are prone to corruption and security attacks. Other blockchains, such as EOS and Lisk, introduce different types of [Delegated Proof of Stake (DPoS)](https://en.wikipedia.org/wiki/Delegated_proof_of_stake) to allow the token holders to vote and elect the validator set. It increases decentralization and favors community governance.

BSC here proposes to combine DPoS and PoA for consensus, so that:

1. Blocks are produced by a limited set of validators.
2. Validators take turns to produce blocks in a PoA manner, similar to Ethereum's Clique consensus design.
3. Validator set are elected in and out based on a staking-based governance.
4. To enhance network capacity, validators are permitted to produce consecutive blocks within specified parameters.

### Validator Set

The validator set is the group of nodes that are responsible for validating transactions and producing blocks on the BSC. The validator set is determined by the amount of staking each validator has, which reflects the amount of BNB staked by the validator and its delegators. The top validators with the most staking are selected as the active validator set, and they take turns to propose and vote on blocks. The rest of the validators are in the standby validator set, and they can join the active validator set if their staking increases or if some active validators drop out.

Any organization or individual can become part of the validator set by creating their validator on-chain and securing sufficient delegations. Similarly, they can opt-out by simply withdrawing all their BNB delegations. Validators can also be removed from the validator set by slashing, which is a penalty for misbehaving or being offline.

In the genesis stage, a few trusted nodes will run as the initial Validator Set. After the blocking starts, anyone can compete to join as candidates to elect as a validator.

### Validator Election

There are different roles for validators:

- **Cabinet:** the top K (which will be 21) validators who get the most chance of producing blocks.
- **Candidate:** the top (K, K+NumOfCandidates]) validators who get a small chance of producing blocks.
- **Inactive:** the rest validators who get no chance of producing blocks.

![image](./assets/validator-select.png)

The validator set roles are determined every 24 hours based on the latest staking information. After UTC 00:00, the consensus engine sorts validators and updates the BSC validator set with the ranking information.

### System Contracts

There are several built-in contracts (i.e., system contracts) to facilitate the BSC staking and validator election.

- **Validator Set Contract:** The contract periodically elects a validator set. The contract also serves as a vault for temporarily storing validator rewards.

- **System Reward Contract:** This contract acts as a vault to collect part of transaction fees. The funds are used for various public purposes, like distributing fast finality rewards.

- **Slash Contract:** This contract is used to keep track of the number of times a validator becomes unavailable and triggers penalties once a certain threshold is reached. Additionally, this contract also handles other types of slash events, such as double signing and malicious voting in fast finality.

- **Stake Hub Contract:** This contract serves as the entry point for managing validators and delegations, while also implementing the logic for slashing specific validators. For delegation/undelegation/redelegation operations, it will call different validators' implementation contracts to manage a user's stake.

### Reward Distribution
The staking reward comes from the transaction fee - when a block is produced, the majority of the block fee will be collected as reward for the validator who proposed the block.

Every day, a portion of the rewards collected will be directly sent to the operator account of the validator as commission, while the remaining portion will be sent to the corresponding validator credit contract. And when a user undelegates and claims his/her stakes, the accumulated reward and the original stake will be sent back to him/her.

## Security and Finality
Given there are more than (N/2+1) validators that are honest, PoA based networks usually work securely and properly. However, there are still cases where certain Byzantine validators may still manage to attack the network, e.g. through the "[Clone Attack](https://arxiv.org/pdf/1902.10244.pdf)". To secure as much as BC, BSC users are encouraged to wait until receiving blocks sealed by more than 2⁄3N+1 different validators. In that way, the BSC can be trusted at a similar security level to BC and can tolerate less than 1⁄3*N Byzantine validators.

Beside probabilistic finality, BSC proposes a fast finality mechanism to finalize a block, once the block has been finalized, it won't be reverted forever. Its idea is quite similar to [Casper FFG](https://arxiv.org/pdf/1902.10244.pdf). It takes several steps to finalize a block:

1. A block is proposed by a validator and propagated to other validators.
2. Validators use their BLS private key to sign for the block as a vote message.
3. Gather the votes from validators into a pool.
4. Aggregate the BLS signature if its direct parent block has gotten enough votes when
   proposing a new block.
5. Set the aggregated vote attestation into the extra field of the new block's header.
6. Validators and full nodes who received the new block with the direct parent block's
   attestation can justify the direct parent block.
7. If two continuous blocks have been justified, then the previous one is finalized.

## Governance
BSC introduces the native governance module, drawing inspiration from the OpenZeppelin Governor. Here are the key features of BSC Governance:

- **Proposal and Voting Rights**: Staking credit holders can propose and vote on governance matters.
- **Continuous Rewards**: Voters can keep earning staking rewards during the voting period.
- **Flexible Delegation**: Users can delegate their voting rights, enabling others to participate in governance.
- **Secure Execution**: Proposals undergo a time lock period before execution once passed.

BNB Chain governance involves a two-step process: **temperature check** and **final decision voting**. The temperature check, typically conducted through the [Snapshot](https://snapshot.org/#/) platform, allows any BNB holder to gauge community sentiment on a proposal. If the proposal receives enough support, it proceeds to the final decision voting phase. This phase often involves on-chain voting by validators or those with staked BNB, and the outcome determines whether the proposal is implemented or rejected.

## Slashing and Penalties
Slashing is a component of on-chain governance that penalizes malicious or negative actions. Anyone can submit a slash transaction on BSC, which involves providing evidence and paying fees. Successful submissions yield significant rewards. Currently, there are three types of slashable cases.

### Double Sign
It is quite a serious error and very likely a deliberate offense when a validator signs more than one block with the same height and parent block. The reference protocol implementation should already have logic to prevent this, so only the malicious code can trigger this. When Double Sign happens, the validator should be removed from the Validator Set right away.

Anyone can submit a slash transaction with the evidence of Double Sign to the BSC Slash Contract, which should contain the 2 block headers with the same height and parent block, sealed by the offending validator. Upon receiving the evidence, the contract will verify its validity.

The validator will be removed from the validator set, a predefined amount of BNB would be slashed from the self-delegated BNB of the validator.

### Malicious Fast Finality Vote
It is also a serious error when a validator signs two fast finality votes with the same target height or the span of one vote including the span of another vote. The reference protocol implementation should already have logic to prevent this, so only the malicious code can trigger this. When **Malicious Vote** happens, the validator should be removed from the Validator Set right away.

Anyone can submit a slash transaction with the evidence of Malicious Vote to the BSC Slash Contract. Evidence of malicious voting needs to be provided, which includes two conflicting votes and the voting key used for the signature. Upon receiving the evidence, the contract will verify its validity. The validator will be removed from the current set of validators, and the submitter will receive the reward from the system contract.

### Unavailability
The liveness of BSC relies on everyone in the Proof of Staked Authority validator set to produce blocks timely when it is their turn. Validators can miss their turn due to any reason, especially problems in their hardware, software, configuration or network. This instability of the operation will hurt the performance and introduce more indeterministic into the system.

There is an internal smart contract that records the missed blocking metrics of each validator. If the metrics exceed the set threshold, the blocking reward for the validator will not be given to them but shared with other validators performing better. This process aims to gradually remove poorly-operating validators from the set, reducing rewards for their delegators.

If the metrics stay above a higher threshold, the validator will be removed from rotation, and a set amount of BNB will be deducted from their self-delegated BNB. This action results in both validators and delegators not receiving their staking rewards.

## Outlook
It is hard to conclude for the BNB Chain, as it has never stopped evolving. Here below are the topics to look into so as to facilitate the community better for more usability and extensibility:

- **Parallel EVM**. Parallel EVM is an extension to the EVM that allows it to execute multiple instructions in parallel, which improves the performance of the network.
- **State Expiry**. Address the problem of increasing world state storage on the BNB Smart Chain, by removing expired storage state.
- **Non-stop Further Decentralization**.
- **Mass Adoption Infra**. The BNB Chain community is committed to making sure
public infrastructure is top-notch and provides foundational building blocks for large scale applications.
