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

# Mga Prinsipyo ng Disenyo

Matapos ang paglikha ng kahanay na blockchain sa Binance Chain ecosystem, dalawang blockchain ang tatakbo ng sabay upang magbigay ng iba't ibang mga serbisyo. Ang bagong kahanay na chain ay tatawaging “**Binance Smart Chain**” (pinaikli na “**BSC**” para sa mga seksyon sa ibaba), habang ang umiiral na mainnet ay tatawagin pa rin na “**Binance Chain**” (pinaikli na “**BC**” para sa mga seksyon sa ibaba).

Narito ang mga prinsipyo ng disenyo ng **BSC**:

1. **Malayang Blockchain**: sa panteknikal na salita, ang BSC ay isang nagsasariling blockchain, sa halip na isang layer-2 na solusyon. Karamihan sa mga pangunahing kakayahan ng BSC na panteknikal at pang-negosyo ay dapat na umiiral sa loob ng sarili niya upang maaari pa rin itong tumakbo nang maayos kahit na huminto pansamantala ang BC ng maikling panahon.
2. **Pagkatugma sa Ethereum**: Ang unang praktikal at malawak na ginagamit na platform para sa Smart Contract ay ang Ethereum. Upang samantalahin ang medyo maunlad na mga aplikasyon at komunidad nito, pinili ng BSC na maging katugma sa umiiral na Ethereum mainnet. Nangangahulugan ito na ang karamihan sa **dApps**, mga bahagi ng ecosystem, at mga iba't ibang kasangkapan ay gagana sa BSC at mangangailangan ng wala o kaunti lamang na mga pagbabago; Mangangailangan ang BSC node ng katulad (o medyo mas mataas) na katangian ng hardware at kakayahan upang tumakbo at mapatakbo. Ang ganitong pagpapatupad ay dapat mag-iwan ng lugar para sa BSC na makahabol sa karagdagang mga pagsulong ng Ethereum.
3. **Staking na Kaakibat sa Pagkakasundo at Pamamahala**: Ang pagkakasundo na nakabase sa Staking ay mas mainam sa kapaligiran at nag-iiwan ng mas may kakayahang umangkop na pamamaraan sa pamamahala ng komunidad. Inaasahan, ang ganitong uri ng pakakasundo ay kayang magbigay ng mas mahusay na pagtakbo ng network sa [proof-of-work](https://en.wikipedia.org/wiki/Proof_of_work) na sistema ng blockchain, mga halimbawa nito ay ang mas mabilis na oras ng pagbuo ng bloke at mas mataas na kapasidad sa transaksyon.
4. **Native Cross-Chain na Komunikasyon**: ang BC at BSC ay parehong papatakbuhin na may sariling suporta para sa cross-chain na komunikasyon sa pagitan ng dalawang mga blockchain. Ang protocol ng komunikasyon nila ay dapat na bi-directional, desentralisado, at di nangangailangan ng tiwala. Tututukan nito ang paglipat ng mga digital na assets sa pagitan ng BC at BSC, halimbawa, ang [BEP2](https://github.com/binance-chain/BEPs/blob/master/BEP2.md) na mga token, at kalaunan, iba pang mga token ng BEP na ipapakilala sa paglaon. Dapat pangalagaan ng protocol ang minimum ng iba pang mga bagay na nakalagay sa estado ng mga blockchain, na may ilang mga pagbubukod lamang.