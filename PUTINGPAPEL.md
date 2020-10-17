# Binance Smart Chain

**Isang Kahanay na Binance Chain para Mapatakbo ang mga Smart Contracts**

_TANDAAN: Ang dokumentong ito ay kasalukuyang ginagawa. Mangyaring dumalaw ng madalas para sa mga pagbabago!_

## Talaan ng Nilalaman

- [Pagganyak](#motivation)
- [Mga Prinsipyo ng Disenyo](#design-principles)
- [Consensus and Validator Quorum](#consensus-and-validator-quorum)
  * [Proof of Staked Authority](#proof-of-staked-authority)
  * [Validator Quorum](#validator-quorum)
  * [Security and Finality](#security-and-finality)
  * [Reward](#reward)
- [Token Economy](#token-economy)
  * [Native Token](#native-token)
  * [Other Tokens](#other-tokens)
- [Cross-Chain Transfer and Communication](#cross-chain-transfer-and-communication)
  * [Cross-Chain Transfer](#cross-chain-transfer)
  * [BC to BSC Architecture](#bc-to-bsc-architecture)
  * [BSC to BC Architecture](#bsc-to-bc-architecture)
  * [Timeout and Error Handling](#timeout-and-error-handling)
  * [Cross-Chain User Experience](#cross-chain-user-experience)
  * [Cross-Chain Contract Event](#cross-chain-contract-event)
- [Staking and Governance](#staking-and-governance)
  * [Staking on BC](#staking-on-bc)
  * [Rewarding](#rewarding)
  * [Slashing](#slashing)
- [Relayers](#relayers)
  * [BSC Relayers](#bsc-relayers)
  * [Oracle Relayers](#oracle-relayers)
- [Outlook](#outlook)

# Pagganyak

Matapos ang [paglunsad](https://www.binance.com/en/blog/327334696200323072/Binance-DEX-Launches-on-Binance-Chain-Invites-Further-Community-Development) sa mainnet noong Abril 2019, ipinakita ng [Binance Chain](https://www.binance.org) ang disenyo nitong may mabilis at malaking throughput. Ang [Binance Dex](https://www.binance.org/trade) na isang native [decentralized application](https://en.wikipedia.org/wiki/Decentralized_application) o “dApp” kung saan nakatuon ang pansin ng Binance Chain, ay nakapagpakita ng mababang pagkaantala o latency na may maluwag na kapasidad sa pag tutugma ng milyun-milyong palitan at kalakalan sa maikling panahon.

Ang kakayahang umangkop at kakayahang magamit ay kadalasang may kabaligtarang relasyon sa kakayahang pagganap. Ang pagtutok sa pagbibigay ng isang madaling paraan ng pagkakaloob ng mga digital na asset at lugar ng pangangalakal ay nagdudulot din ng mga limitasyon. Ang pinakahinahanap na abilidad ng Binance Chain ay ang programmable na kakayahan nito na mai-extend, o sa madaling salita ang [Smart Contract](https://en.wikipedia.org/wiki/Smart_contract) at Virtual Machine na mga kakayahan. Ang mga tagapagbigay ng mga digital na asset at mga nagmamay-ari nito ay nahihirapan sa pagdagdag ng mga bagong disentralisadong kakayahan para sa kanilang mga assets o magpakilala ng anumang uri ng pamamahala at mga aktibidad sa kanilang komunidad.

Sa kabila ng mataas na pangangailangan na ito para sa paglagay ng Smart Contract na kakayahan sa Binance Chain, isa itong mahirap na desisyon. Ang pagtakbo ng isang Smart Contract ay maaaring makapagpabagal ng kalakalan at magdagdag ng mga mahirap matukoy na aspeto sa pangangalakal. Kung kayang tiisin ang kompromiso na iyon, maaaring maging isang deretsong ideya ang ipakilala ang isang bagong Virtual Machine na may mga katangian na batay sa [Tendermint](https://tendermint.com/core/), batay sa kasalukuyang consensus protocol at sa pangunahing pagpapatakbo ng [RPC](https://docs.binance.org/api-reference/node-rpc.html) ng Binance Chain. Ngunit ang lahat ng ito ay magpapataas ng mga kinakailangan sa pag-aaral ng lahat ng mga aktibong mga komunidad ng dApp, at maaring hindi masyadong malugod na tanggapin.

Ipinapanukala namin ang isang kahanay na blockchain ng kasalukuyang Binance Chain upang mapanatili ang mataas na kakayahan sa pagganap ng native DEX blockchain habang suportado ang isang madaling gamitin na Smart Contract na kakayahan.
