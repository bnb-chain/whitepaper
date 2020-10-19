# Binance Smart Chain

**Isang Kahanay na Binance Chain para Mapatakbo ang mga Smart Contracts**

_TANDAAN: Ang dokumentong ito ay kasalukuyang ginagawa. Mangyaring dumalaw ng madalas para sa mga pagbabago!_

## Talaan ng Nilalaman

- [Pagganyak](#pagganyak)
- [Mga Prinsipyo ng Disenyo](#mga-prinsipyo-ng-disenyo)
- [Pagkakasunduan at Korum ng mga Tagapagpatunay](#pagkakasunduan-at-korum-ng-mga-tagapagpatunay)
  * [Patunay ng Itinayang Awtoridad](#patunay-ng-itinayang-awtoridad)
  * [Korum ng mga Tagapagpatunay](#korum-ng-mga-tagapagpatunay)
  * [Seguridad at Kawakasan](#seguridad-at-kawakasan)
  * [Gantimpala](#gantimpala)
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
- [Pagtaya at Pamamahala](#pagtaya-at-pamamahala)
  * [Staking on BC](#staking-on-bc)
  * [Rewarding](#rewarding)
  * [Slashing](#slashing)
- [Tagahatid](#tagahatid)
  * [BSC Relayers](#bsc-relayers)
  * [Oracle Relayers](#oracle-relayers)
- [Outlook](#outlook)

# Pagganyak

Matapos ang [paglunsad](https://www.binance.com/en/blog/327334696200323072/Binance-DEX-Launches-on-Binance-Chain-Invites-Further-Community-Development) sa mainnet noong Abril 2019, ipinakita ng [Binance Chain](https://www.binance.org) ang disenyo nitong may mabilis at malaking throughput. Ang [Binance Dex](https://www.binance.org/trade) na isang native [decentralized application](https://en.wikipedia.org/wiki/Decentralized_application) o “dApp” kung saan nakatuon ang pansin ng Binance Chain, ay nakapagpakita ng mababang pagkaantala o latency na may maluwag na kapasidad sa pag tutugma ng milyun-milyong palitan at kalakalan sa maikling panahon.

Ang kakayahang umangkop at kakayahang magamit ay kadalasang may kabaligtarang relasyon sa kakayahang pagganap. Ang pagtutok sa pagbibigay ng isang madaling paraan ng pagkakaloob ng mga digital na asset at lugar ng pangangalakal ay nagdudulot din ng mga limitasyon. Ang pinakahinahanap na abilidad ng Binance Chain ay ang programmable na kakayahan nito na mai-extend, o sa madaling salita ang [Smart Contract](https://en.wikipedia.org/wiki/Smart_contract) at Virtual Machine na mga kakayahan. Ang mga tagapagbigay ng mga digital na asset at mga nagmamay-ari nito ay nahihirapan sa pagdagdag ng mga bagong disentralisadong kakayahan para sa kanilang mga assets o magpakilala ng anumang uri ng pamamahala at mga aktibidad sa kanilang komunidad.

Sa kabila ng mataas na pangangailangan na ito para sa paglagay ng Smart Contract na kakayahan sa Binance Chain, isa itong mahirap na desisyon. Ang pagtakbo ng isang Smart Contract ay maaaring makapagpabagal ng kalakalan at magdagdag ng mga mahirap matukoy na aspeto sa pangangalakal. Kung kayang tiisin ang kompromiso na iyon, maaaring maging isang deretsong ideya ang ipakilala ang isang bagong Virtual Machine na may mga katangian na batay sa [Tendermint](https://tendermint.com/core/), batay sa kasalukuyang protokol ng pagkakasunduan at sa pangunahing pagpapatakbo ng [RPC](https://docs.binance.org/api-reference/node-rpc.html) ng Binance Chain. Ngunit ang lahat ng ito ay magpapataas ng mga kinakailangan sa pag-aaral ng lahat ng mga aktibong mga komunidad ng dApp, at maaring hindi masyadong malugod na tanggapin.

Ipinapanukala namin ang isang kahanay na blockchain ng kasalukuyang Binance Chain upang mapanatili ang mataas na kakayahan sa pagganap ng native DEX blockchain habang suportado ang isang madaling gamitin na Smart Contract na kakayahan.

# Mga Prinsipyo ng Disenyo

Matapos ang paglikha ng kahanay na blockchain sa Binance Chain ecosystem, dalawang blockchain ang tatakbo ng sabay upang magbigay ng iba't ibang mga serbisyo. Ang bagong kahanay na chain ay tatawaging “**Binance Smart Chain**” (pinaikli na “**BSC**” para sa mga seksyon sa ibaba), habang ang umiiral na mainnet ay tatawagin pa rin na “**Binance Chain**” (pinaikli na “**BC**” para sa mga seksyon sa ibaba).

Narito ang mga prinsipyo ng disenyo ng **BSC**:

1. **Malayang Blockchain**: sa panteknikal na salita, ang BSC ay isang nagsasariling blockchain, sa halip na isang layer-2 na solusyon. Karamihan sa mga pangunahing kakayahan ng BSC na panteknikal at pang-negosyo ay dapat na umiiral sa loob ng sarili niya upang maaari pa rin itong tumakbo nang maayos kahit na huminto pansamantala ang BC ng maikling panahon.
2. **Pagkatugma sa Ethereum**: Ang unang praktikal at malawak na ginagamit na platform para sa Smart Contract ay ang Ethereum. Upang samantalahin ang medyo maunlad na mga aplikasyon at komunidad nito, pinili ng BSC na maging katugma sa umiiral na Ethereum mainnet. Nangangahulugan ito na ang karamihan sa **dApps**, mga bahagi ng ecosystem, at mga iba't ibang kasangkapan ay gagana sa BSC at mangangailangan ng wala o kaunti lamang na mga pagbabago; Mangangailangan ang BSC node ng katulad (o medyo mas mataas) na katangian ng hardware at kakayahan upang tumakbo at mapatakbo. Ang ganitong pagpapatupad ay dapat mag-iwan ng lugar para sa BSC na makahabol sa karagdagang mga pagsulong ng Ethereum.
3. **Pagtaya na Kaakibat sa Pagkakasundo at Pamamahala**: Ang pagkakasundo na nakabase sa Pagtaya ay mas mainam sa kapaligiran at nag-iiwan ng mas may kakayahang umangkop na pamamaraan sa pamamahala ng komunidad. Inaasahan, ang ganitong uri ng pakakasundo ay kayang magbigay ng mas mahusay na pagtakbo ng network sa [proof-of-work](https://en.wikipedia.org/wiki/Proof_of_work) na sistema ng blockchain, hal. mabilis na oras ng pagbuo ng bloke at mas mataas na kapasidad sa transaksyon.
4. **Native Cross-Chain na Komunikasyon**: ang BC at BSC ay parehong papatakbuhin na may sariling suporta para sa cross-chain na komunikasyon sa pagitan ng dalawang mga blockchain. Ang protocol ng komunikasyon nila ay dapat na bi-directional, desentralisado, at di nangangailangan ng tiwala. Tututukan nito ang paglipat ng mga digital na assets sa pagitan ng BC at BSC, ibig sabihin, ang [BEP2](https://github.com/binance-chain/BEPs/blob/master/BEP2.md) na mga token, at kalaunan, iba pang mga token ng BEP na ipapakilala sa paglaon. Dapat pangalagaan ng protocol ang minimum ng iba pang mga bagay na nakalagay sa estado ng mga blockchain, na may ilang mga pagbubukod lamang.

# Pagkakasunduan at Korum ng mga Tagapagpatunay

Batay sa mga prinsipyo ng disenyo sa itaas, ang protokol ng pagkakasunduan ng BSC ay magpapatupad ng mga sumusunod na layunin:

1. Ang oras ng pag gawa ng bloke ay dapat na mas maikli kaysa sa Ethereum network, hal. 5 segundo lamang o mas maikli pa.
2. Nangangailangan ito ng limitadong oras upang kumpirmahin ang kawakasan ng mga transaksyon, hal. hanggang sa isang minuto o mas maikli pa.
3. Walang implasyon ng native token: BNB, ang gantimpala ng bloke ay nakolekta mula sa mga bayarin sa transaksyon, at babayaran ito gamit ang BNB.
4. Ito ay nagkakasundo sa Ethereum system hangga't maaari.
5. Pinapayagan nito ang modernong [patunay-ng-taya](https://en.wikipedia.org/wiki/Proof_of_stake) na pamamahala sa blockchain network.

## Patunay ng Itinayang Awtoridad

Bagaman ang Proof-of-Work (PoW) ay kinilala bilang isang praktikal na mekanismo upang magpatupad ng isang desentralisadong network, hindi ito mainam sa kapaligiran at nangangailangan din ng isang mataas na bilang ng mga kalahok upang mapanatili ang seguridad.

Ang Ethereum at iba pang mga blockchain network, tulad ng [MATIC Bor](https://github.com/maticnetwork/bor), [TOMOChain](https://tomochain.com/), [GoChain](https://gochain.io/), [xDAI](https://xdai.io/), ay gumagamit ng [Patunay-ng-Awtoridad (PoA)](https://en.wikipedia.org/wiki/Proof_of_authority) o ang mga uri nito sa iba't ibang mga sitwasyon, kabilang ang parehong testnet at mainnet. Nagbibigay ang PoA ng ilang depensa sa 51% na atake, na may pinahusay na liksi at pagpapaubaya sa ilang mga antas ng mga manlalaro ng Byzantine (may masamang hangarin o na-hack). Nagsisilbi itong isang madaling pagpipilian na hirangin bilang mga pangunahing kakayahan.

Samantala, ang PoA na protokol ay pinupuna dahil sa pagiging hindi kasing desentralisado ng PoW, dahil ang mga tagapagpatunay, o ang mga node na nagpapalit-palitan sa pagbuo ng mga bloke, ay mayroong lahat ng awtoridad kaya madaling matukso sa katiwalian at maatake ang seguridad. Ang iba pang mga blockchain, tulad ng EOS at Lisk, ay parehong nagpapakilala ng iba't ibang uri ng [Delegated Proof of Stake (DPoS)](https://en.bitcoinwiki.org/wiki/DPoS) upang payagan ang mga may hawak ng token na bumoto at piliin ang grupo ng mga tagapagpatunay. Nadadagdagan nito ang desentralisasyon at mas pinapaboran ang pamamahala ng komunidad.

Iminumungkahi ng BSC na pagsamahin ang DPoS at PoA para sa pagkakasunduan, upang:
1. Ang mga bloke ay ginawa ng isang limitadong grupo ng mga tagapagpatunay
2. Nagpapalit-palitan ang mga tagapagpatunay upang makabuo ng mga bloke sa pamamaraan ng PoA, katulad sa disenyo ng pagkakasunduan ng [Ethereum's Clique](https://eips.ethereum.org/EIPS/eip-225)
3. Ang hanay ng tagapagpatunay ay inihalal sa loob at labas batay sa isang pamamahalang nakabatay sa pagtaya

## Korum ng mga Tagapagpatunay

Sa yugto ng genesis, ang ilang mga pinagkakatiwalaang node ay tatakbo bilang paunang Hanay ng Tagapagpatunay. Matapos magsimula ang pag gawa ng bloke, ang sinuman ay maaaring makipagkumpitensya upang sumali bilang mga kandidato sa pagiging isang tagapagpatunay. Ang istado ng pagtaya ay magpapasiya sa nangungunang 21 pinaka tinayaang node na maging susunod na hanay ng tagapagpatunay, at ang gayong halalan ay uulitin bawat 24 na oras.

Ang **BNB** ay ang token na ginagamit upang maitaya para sa BSC.

Upang manatiling katugma ng Ethereum at maisulong sa mga gagawin pa lamang na mga protokol ng pagkakasunduan sa hinaharap, pipiliin ng BSC na umasa sa **BC** para sa pangangasiwa ng pagtaya (Mangyaring sumangguni sa “[Pagtaya at Pamamahala](#pagtaya-at-pamamahala)” na seksyon sa ibaba). Mayroong **dedikadong modyul ng pagtaya para sa BSC sa BC**. Tatanggapin nito ang pagtaya sa BSC mula sa mga may hawak ng BNB at kakalkulahin ang pinakamataas na tinayaang hanay ng node. Sa tuwing hatinggabi ng UTC, maglalabas ang BC ng isang mapapatunayan na `ValidatorSetUpdate` na mensaheng cross-chain upang abisuhan ang BSC na palitan ng pinakabago ang hanay ng tagapagpatunay nito.

Habang gumagawa ng karagdagang mga bloke, susuriin ng umiiral na mga tagapagpatunay ng BSC kung mayroong isang mensahe na `ValidatorSetUpdate` na naipadala sa BSC pana-panahon. Kung meron, babaguhin nila ang hanay ng tagapagpatunay pagkatapos ng isang **epoch na panahon**, ibig sabihin, isang paunang natukoy na bilang ng oras ng pag gawa ng bloke. Halimbawa, kung ang BSC ay gumagawa ng isang bloke tuwing 5 segundo, at ang epoch na panahon ay 240 bloke, ang kasalukuyang hanay ng tagapagpatunay ay susuriin at babaguhin ang hanay ng tagapagpatunay para sa susunod na epoch sa 1200 segundo (20 minuto).

## Seguridad at Kawakasan

Dahil mayroong higit sa ½\*N+1 na mga tagapagpatunay na matapat, ang mga network na nakabatay sa PoA ay karaniwang gumagana nang ligtas at maayos. Gayunpaman, may mga kaso pa rin kung saan ilang tagapagpatunay ng Byzantine ay maaari pa ring magawang atakein ang network, hal. sa pamamagitan ng “[Clone na Atake](https://arxiv.org/pdf/1902.10244.pdf)”. Upang maging kasing ligtas ng BC, hinihimok ang mga gumagamit ng BSC na maghintay hanggang sa makatanggap ng mga bloke na tinatakan ng higit sa ⅔\*N+1 magkakaibang mga tagapagpatunay. Sa ganoong paraan, ang BSC ay mapagkakatiwalaan sa katulad na antas ng seguridad sa BC at maaaring tiisin ang mas mababa sa ⅓\*N na mga tagapagpatunay ng Byzantine.

Sa 21 mga tagapagpatunay, kung ang oras ng bloke ay 5 segundo, ang ⅔\*N+1 na magkakaibang mga tatak ng tagapagpatunay ay mangangailangan ng haba ng oras na (⅔\*21+1)*5 = 75 segundo. Anumang mga kritikal na aplikasyon para sa BSC ay maaaring maghintay ng ⅔\*N+1 upang matiyak ang isang ligtas na kawakasan. Gayunpaman, bukod sa naturang pagkakaayos, ang BSC ay nagpapakilala ng **Pagbawas** na lohika upang maparusahan ang mga tagapagpatunay ng Byzantine para sa **doble na pagpirma** o **hindi magagamit**, na tatalakayin sa seksyong “Pagtaya at Pamamahala” mamaya. Ang Pagbawas na lohika na ito ay ilalantad ang mga may masamang hangarin na tagapagpatunay sa isang napakaikling panahon at gagawin ang “Clone na Atake” na napakahirap o labis na hindi kapaki-pakinabang upang maipatupad. Sa pagpapahusay na ito, ang ½\*N+1 o kahit na mas kaunting mga bloke ay sapat na bilang kumpirmasyon para sa karamihan ng mga transaksyon.

## Gantimpala

Lahat ng mga tagapagpatunay ng BSC sa kasalukuyang hanay ng tagapagpatunay ay gagantimpalaan ng mga **bayarin sa transaksyon sa BNB**. Dahil ang BNB ay hindi isang inflationary token, hindi magkakaroon ng mga gantimpala sa pagmimina gaya ng binibigay ng Bitcoin at Ethereum network, at ang bayad sa gas ay ang pangunahing gantimpala para sa mga tagapagpatunay. Dahil ang BNB ay mga utility token din na may iba pang mga gamit, tatangkilikin pa rin ng mga delegado at tagapagpatunay ang iba pang mga benepisyo ng paghawak ng BNB.

Ang gantimpala para sa mga tagapagpatunay ay ang mga bayarin na nakolekta mula sa mga transaksyon sa bawat bloke. Maaaring magpasya ang mga tagapagpatunay kung magkano ang ibabalik sa mga delegado na tumaya sa kanila ng kanilang BNB, upang makaakit ng mas maraming taya. Ang bawat tagapagpatunay ay magpapalitan upang makabuo ng mga bloke sa parehong posibilidad (kung mananatili sila sa 100% na pagka aktibo), sa gayon, sa pangmatagalan, ang lahat ng mga matatag na tagapagpatunay ay maaaring makakuha ng magkakatulad na laki ng gantimpala. Samantala, ang mga taya sa bawat tagapagpatunay ay maaaring magkakaiba, kaya nagdadala ito ng isang kontra-intuitive na sitwasyon na mas maraming mga gumagamit ang nagtitiwala at naglalaan sa isang tagapagpatunay, maaaring makakuha sila ng mas kaunting gantimpala. Kaya't ang mga makatuwiran na delegado ay may posibilidad na magtalaga sa isa na may mas kaunting taya hangga't ang tagapagpatunay ay mapagkakatiwalaan pa rin (ang walang katiyakan na tagapagpatunay ay maaaring magdala ng peligro na pagbawas). Sa huli, ang mga taya sa lahat ng mga tagapagpatunay ay magkakaroon ng mas kaunting pagkakaiba-iba. Ito ay talagang pipigilan ang konsentrasyon ng taya at ang “nanalo ay mananalo palagi” na problemang nakikita sa ilang iba pang mga network.

Ang ilang mga bahagi ng bayad sa gas ay igagantimpala din sa mga tagahatid para sa komunikasyon na Cross-Chain. Mangyaring mag-refer sa seksyong “[Tagahatid](#tagahatid)” sa ibaba.