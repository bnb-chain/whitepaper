# Binance Smart Chain

**Isang Kahanay na Binance Chain para Mapatakbo ang mga Matalinong Kontrata**

_PAALALA: Ang dokumentong ito ay kasalukuyang ginagawa. Mangyaring dumalaw ng madalas para sa mga pagbabago!_

## Talaan ng mga Nilalaman

- [Pagganyak](#pagganyak)
- [Mga Prinsipyo ng Disenyo](#mga-prinsipyo-ng-disenyo)
- [Pagkakasundo at Korum ng mga Tagapagpatunay](#pagkakasunduan-at-korum-ng-mga-tagapagpatunay)
  * [Patunay ng Itinayang Awtoridad](#patunay-ng-itinayang-awtoridad)
  * [Korum ng Tagapagpatunay](#korum-ng-tagapagpatunay)
  * [Seguridad at Kawakasan](#seguridad-at-kawakasan)
  * [Gantimpala](#gantimpala)
- [Ekonomiya ng Token](#ekonomiya-ng-token)
  * [Katutubong Token](#katutubong-token)
  * [Iba Pang Mga Token](#iba-pang-mga-token)
- [Cross-Chain na Paglipat at Komunikasyon](#cross-chain-na-paglipat-at-komunikasyon)
  * [Cross-Chain na Paglipat](#cross-chain-na-paglipat)
  * [BC patungo sa BSC na Arkitektura](#bc-patungo-sa-bsc-na-arkitektura)
  * [BSC patungo sa BC na Arkitektura](#bsc-patungo-sa-bc-na-arkitektura)
  * [Pag-timeout at Pangangasiwa ng Kamalian](#pag-timeout-at-pangangasiwa-ng-kamalian)
  * [Cross-Chain na Karanasan ng User](#cross-chain-na-karanasan-ng-user)
  * [Kaganapan sa Kontrata ng Cross-Chain](#kaganapan-sa-kontrata-ng-cross-chain)
- [Pagtaya at Pamamahala](#pagtaya-at-pamamahala)
  * [Pagtaya sa BC](#pagtaya-sa-bc)
  * [Paggantimpala](#paggantimpala)
  * [Pagbawas](#pagbawas)
- [Mga Tagahatid](#mga-tagahatid)
  * [Mga Tagahatid ng BSC](#mga-tagahatid-ng-bsc)
  * [Mga Orakulong Tagahatid](#mga-orakulong-tagahatid)
- [Pananaw](#pananaw)

# Pagganyak

Matapos ang [paglunsad](https://www.binance.com/en/blog/327334696200323072/Binance-DEX-Launches-on-Binance-Chain-Invites-Further-Community-Development) sa mainnet noong Abril 2019, ipinamalas ng [Binance Chain](https://www.binance.org) ang disenyo nitong may mabilis at malaking throughput. Ang [Binance Dex](https://www.binance.org/trade) na isang katutubong [decentralized application](https://en.wikipedia.org/wiki/Decentralized_application) o “dApp” kung saan nakatuon ang pansin ng Binance Chain, ay nakapagpakita ng mababang pagkaantala sa pagtutugma at malaking kapasidad sa pamamagitan ng paghawak ng milyun-milyong dami ng kalakalan sa maikling panahon.

Ang kakayahang umangkop at kakayahang magamit ay kadalasang may kabaligtarang relasyon sa kakayahang pagganap. Ang pagtutok sa pagbibigay ng isang madaling paraan ng pagkakaloob ng mga digital na asset at lugar ng pangangalakal ay nagdudulot din ng mga limitasyon. Ang pinakahinahanap na katangian ng Binance Chain ay ang programmable extendibility, o sa madaling salita ang [Matalinong Kontrata](https://en.wikipedia.org/wiki/Smart_contract) at Virtual Machine na mga kakayahan. Ang mga tagapagbigay ng mga digital na asset at mga nagmamay-ari nito ay nahihirapan sa pagdagdag ng mga bagong disentralisadong kakayahan para sa kanilang mga assets o magpakilala ng anumang uri ng pamamahala at mga aktibidad sa kanilang komunidad.

Sa kabila ng mataas na pangangailangan na maglagay ng Matalinong Kontrata na katangian sa Binance Chain, isa itong mahirap na desisyon. Ang pagtakbo ng isang Matalinong Kontrata ay maaaring makapagpabagal ng kalakalan at magdagdag ng mga hindi matukoy na aspeto sa pangangalakal. Kung kayang tiisin ang kompromiso na maidudulot nito, maaaring maging isang tapat na ideya ang ipakilala ang isang bagong Virtual Machine na may mga katangian na batay sa [Tendermint](https://tendermint.com/core/), batay sa kasalukuyang protokol ng pagkakasunduan at sa pangunahing pagpapatakbo ng [RPC](https://docs.binance.org/api-reference/node-rpc.html) ng Binance Chain. Pero ang lahat ng ito ay magpapataas ng mga kinakailangan sa pag-aaral ng lahat ng mga aktibong mga komunidad ng dApp, at posibleng hindi masyadong malugod na tanggapin.

Ipinapanukala namin ang isang kahanay na blockchain ng kasalukuyang Binance Chain para mapanatili ang mataas na kakayahang pagganap ng katutubong DEX blockchain habang suportado ang isang madaling gamitin na Matalinong Kontrata na kakayahan.

# Mga Prinsipyo ng Disenyo

Matapos ang paglikha ng kahanay na blockchain sa Binance Chain ecosystem, dalawang blockchain ang tatakbo ng sabay para magbigay ng iba't ibang mga serbisyo. Ang bagong kahanay na kadena ay tatawaging “**Binance Smart Chain**” (pinaikli na “**BSC**” para sa mga seksyon sa ibaba), habang ang umiiral na mainnet ay tatawagin pa rin na “**Binance Chain**” (pinaikli na “**BC**” para sa mga seksyon sa ibaba).

Narito ang mga prinsipyo ng disenyo ng **BSC**:

1. **Malayang Blockchain**: Sa panteknikal na salita, ang BSC ay isang nagsasariling blockchain, sa halip na isang layer-2 na solusyon. Karamihan sa mga pangunahing kakayahan ng BSC na panteknikal at pang-negosyo ay dapat na umiiral sa loob ng sarili niya para maaari pa rin itong tumakbo nang maayos kahit na huminto pansamantala ang BC ng maikling panahon.
2. **Pagkatugma sa Ethereum**: Ang unang praktikal at malawak na ginagamit na platform para sa Matalinong Kontrata ay ang Ethereum. Upang samantalahin ang medyo maunlad na mga aplikasyon at komunidad nito, pinili ng BSC na maging katugma sa umiiral na Ethereum mainnet. Nangangahulugan ito na ang karamihan sa **dApps**, mga bahagi ng ecosystem, at mga iba't ibang kasangkapan ay gagana sa BSC at mangangailangan ng wala o kaunti lang na mga pagbabago; Mangangailangan ang BSC node ng katulad (o medyo mas mataas) na katangian ng hardware at kakayahan para tumakbo at mapatakbo. Ang ganitong pagpapatupad ay dapat mag-iwan ng lugar para sa BSC na makahabol sa karagdagang mga pagsulong ng Ethereum.
3. **Pagtaya na Kaakibat sa Pagkakasundo at Pamamahala**: Ang pagkakasundo na nakabase sa Pagtaya ay mas mainam sa kapaligiran at nag-iiwan ng mas may kakayahang umangkop na pamamaraan sa pamamahala ng komunidad. Inaasahan na ang ganitong uri ng pakakasundo ay kayang magbigay ng mas mahusay na kakayahang pagganap ng network kaysa [proof-of-work](https://en.wikipedia.org/wiki/Proof_of_work) na sistema ng blockchain, hal. mabilis na oras ng pagbuo ng bloke at mas mataas na kapasidad sa transaksyon.
4. **Katutubong Cross-Chain na Komunikasyon**: Ang BC at BSC ay parehong papatakbuhin na may sariling suporta para sa cross-chain na komunikasyon sa pagitan ng dalawang mga blockchain. Ang protocol ng komunikasyon nila ay dapat na bi-directional, desentralisado, at di nangangailangan ng tiwala. Tututukan nito ang paglipat ng mga digital na assets sa pagitan ng BC at BSC, ibig sabihin, ang [BEP2](https://github.com/binance-chain/BEPs/blob/master/BEP2.md) na mga token, at kalaunan, iba pang mga tokens na BEP na ipapakilala sa paglaon. Dapat pangalagaan ng protocol ang minimum ng iba pang mga bagay na nakalagay sa estado ng mga blockchain, na may ilang mga pagbubukod lang.

# Pagkakasunduan at Korum ng mga Tagapagpatunay

Batay sa mga prinsipyo ng disenyo sa itaas, ang protokol ng pagkakasunduan ng BSC ay magpapatupad ng mga sumusunod na layunin:

1. Ang oras ng pag gawa ng bloke ay dapat na mas maikli kaysa sa Ethereum network, hal. 5 segundo lang o mas maikli pa.
2. Nangangailangan ito ng limitadong oras para kumpirmahin ang kawakasan ng mga transaksyon, hal. hanggang sa isang minuto o mas maikli pa.
3. Walang implasyon ng katutubong token: BNB, ang gantimpala ng bloke ay nakolekta mula sa mga bayarin sa transaksyon, at babayaran ito gamit ang BNB.
4. Ito ay nagkakasundo sa sistema ng Ethereum hangga't maaari.
5. Pinapayagan nito ang modernong [patunay-ng-taya](https://en.wikipedia.org/wiki/Proof_of_stake) na pamamahala sa blockchain network.

## Patunay ng Itinayang Awtoridad

Bagaman ang Proof-of-Work (PoW) ay kinilala bilang isang praktikal na mekanismo para magpatupad ng isang desentralisadong network, hindi ito mainam sa kapaligiran at nangangailangan din ng isang mataas na bilang ng mga kalahok para mapanatili ang seguridad.

Ang Ethereum at iba pang mga blockchain network, tulad ng [MATIC Bor](https://github.com/maticnetwork/bor), [TOMOChain](https://tomochain.com/), [GoChain](https://gochain.io/), [xDAI](https://xdai.io/), ay gumagamit ng [Patunay-ng-Awtoridad (PoA)](https://en.wikipedia.org/wiki/Proof_of_authority) o ang mga uri nito sa iba't ibang mga sitwasyon, kabilang ang parehong testnet at mainnet. Nagbibigay ang PoA ng ilang depensa sa 51% na atake, na may pinahusay na liksi at pagpapaubaya sa ilang mga antas ng mga manlalaro ng Byzantine (may masamang hangarin o na-hack). Nagsisilbi itong isang madaling pagpipilian na hirangin bilang mga pangunahing kakayahan.

Samantala, ang PoA na protokol ay pinupuna dahil sa pagiging hindi kasing desentralisado ng PoW, dahil ang mga tagapagpatunay, o ang mga node na nagpapalit-palitan sa pagbuo ng mga bloke, ay mayroong lahat ng awtoridad kaya madaling matukso sa katiwalian at maatake ang seguridad. Ang iba pang mga blockchain, tulad ng EOS at Lisk, ay parehong nagpapakilala ng iba't ibang uri ng [Delegated Proof of Stake (DPoS)](https://en.bitcoinwiki.org/wiki/DPoS) para payagan ang mga may hawak ng token na bumoto at piliin ang grupo ng mga tagapagpatunay. Nadadagdagan nito ang desentralisasyon at mas pinapaboran ang pamamahala ng komunidad.

Iminumungkahi ng BSC na pagsamahin ang DPoS at PoA para sa pagkakasunduan, para:
1. Ang mga bloke ay ginawa ng isang limitadong grupo ng mga tagapagpatunay
2. Nagpapalit-palitan ang mga tagapagpatunay para makabuo ng mga bloke sa pamamaraan ng PoA, katulad sa disenyo ng pagkakasunduan ng [Ethereum's Clique](https://eips.ethereum.org/EIPS/eip-225)
3. Ang hanay ng tagapagpatunay ay inihalal sa loob at labas batay sa isang pamamahalang nakabatay sa pagtaya

## Korum ng Tagapagpatunay

Sa yugto ng genesis, ang ilang mga pinagkakatiwalaang node ay tatakbo bilang paunang Hanay ng Tagapagpatunay. Matapos magsimula ang pag gawa ng bloke, ang sinuman ay maaaring makipagkumpitensya para sumali bilang mga kandidato sa pagiging isang tagapagpatunay. Ang istado ng pagtaya ay magpapasiya sa nangungunang 21 pinaka tinayaang node na maging susunod na hanay ng tagapagpatunay, at ang gayong halalan ay uulitin bawat 24 na oras.

Ang **BNB** ay ang token na ginagamit para maitaya para sa BSC.

Upang manatiling katugma ng Ethereum at maisulong sa mga gagawin pa lang na mga protokol ng pagkakasunduan sa hinaharap, pipiliin ng BSC na umasa sa **BC** para sa pangangasiwa ng pagtaya (Mangyaring sumangguni sa “[Pagtaya at Pamamahala](#pagtaya-at-pamamahala)” na seksyon sa ibaba). Mayroong **dedikadong modyul ng pagtaya para sa BSC sa BC**. Tatanggapin nito ang pagtaya sa BSC mula sa mga may hawak ng BNB at kakalkulahin ang pinakamataas na tinayaang hanay ng node. Sa tuwing hatinggabi ng UTC, maglalabas ang BC ng isang mapapatunayan na `ValidatorSetUpdate` na mensaheng cross-chain para abisuhan ang BSC na palitan ng pinakabago ang hanay ng tagapagpatunay nito.

Habang gumagawa ng karagdagang mga bloke, susuriin ng umiiral na mga tagapagpatunay ng BSC kung mayroong isang mensahe na `ValidatorSetUpdate` na naipadala sa BSC pana-panahon. Kung meron, babaguhin nila ang hanay ng tagapagpatunay pagkatapos ng isang **epoch na panahon**, ibig sabihin, isang paunang natukoy na bilang ng oras ng pag gawa ng bloke. Halimbawa, kung ang BSC ay gumagawa ng isang bloke tuwing 5 segundo, at ang epoch na panahon ay 240 bloke, ang kasalukuyang hanay ng tagapagpatunay ay susuriin at babaguhin ang hanay ng tagapagpatunay para sa susunod na epoch sa 1200 segundo (20 minuto).

## Seguridad at Kawakasan

Dahil mayroong higit sa ½\*N+1 na mga tagapagpatunay na matapat, ang mga network na nakabatay sa PoA ay karaniwang gumagana nang ligtas at maayos. Gayunpaman, may mga kaso pa rin kung saan ilang tagapagpatunay ng Byzantine ay maaari pa ring magawang atakein ang network, hal. sa pamamagitan ng “[Clone na Atake](https://arxiv.org/pdf/1902.10244.pdf)”. Upang maging kasing ligtas ng BC, hinihimok ang mga user ng BSC na maghintay hanggang sa makatanggap ng mga bloke na tinatakan ng higit sa ⅔\*N+1 magkakaibang mga tagapagpatunay. Sa ganoong paraan, ang BSC ay mapagkakatiwalaan sa katulad na antas ng seguridad sa BC at maaaring tiisin ang mas mababa sa ⅓\*N na mga tagapagpatunay ng Byzantine.

Sa 21 mga tagapagpatunay, kung ang oras ng bloke ay 5 segundo, ang ⅔\*N+1 na magkakaibang mga tatak ng tagapagpatunay ay mangangailangan ng haba ng oras na (⅔\*21+1)*5 = 75 segundo. Anumang mga kritikal na aplikasyon para sa BSC ay maaaring maghintay ng ⅔\*N+1 para matiyak ang isang ligtas na kawakasan. Gayunpaman, bukod sa naturang pagkakaayos, ang BSC ay nagpapakilala ng **Pagbawas** na lohika para maparusahan ang mga tagapagpatunay ng Byzantine para sa **dobleng pagpirma** o **hindi nagagamit**, na tatalakayin sa seksyong “Pagtaya at Pamamahala” mamaya. Ang Pagbawas na lohika na ito ay ilalantad ang mga may masamang hangarin na tagapagpatunay sa isang napakaikling panahon at gagawin ang “Clone na Atake” na napakahirap o labis na hindi kapaki-pakinabang para maipatupad. Sa pagpapahusay na ito, ang ½\*N+1 o kahit na mas kaunting mga bloke ay sapat na bilang kumpirmasyon para sa karamihan ng mga transaksyon.

## Gantimpala

Lahat ng mga tagapagpatunay ng BSC sa kasalukuyang hanay ng tagapagpatunay ay gagantimpalaan ng mga **bayarin sa transaksyon gamit ang BNB**. Dahil ang BNB ay hindi isang inflationary token, hindi magkakaroon ng mga gantimpala sa pagmimina gaya ng binibigay ng Bitcoin at Ethereum network, at ang bayarin sa gas ay ang pangunahing gantimpala para sa mga tagapagpatunay. Dahil ang BNB ay mga utility token din na may iba pang mga gamit, tatangkilikin pa rin ng mga delegado at tagapagpatunay ang iba pang mga benepisyo ng paghawak ng BNB.

Ang gantimpala para sa mga tagapagpatunay ay ang mga bayarin na nakolekta mula sa mga transaksyon sa bawat bloke. Maaaring magpasya ang mga tagapagpatunay kung magkano ang ibabalik sa mga delegado na tumaya sa kanila ng kanilang BNB, para makaakit ng mas madaming taya. Ang bawat tagapagpatunay ay magpapalitan para makabuo ng mga bloke sa parehong posibilidad (kung mananatili sila sa 100% na pagka aktibo), sa gayon, sa pangmatagalan, ang lahat ng mga matatag na tagapagpatunay ay maaaring makakuha ng magkakatulad na laki ng gantimpala. Samantala, ang mga taya sa bawat tagapagpatunay ay maaaring magkakaiba, kaya nagdadala ito ng isang kontra-intuitive na sitwasyon na mas madaming mga user ang nagtitiwala at naglalaan sa isang tagapagpatunay, maaaring makakuha sila ng mas kaunting gantimpala. Kaya't ang mga makatuwiran na delegado ay may posibilidad na magtalaga sa isa na may mas kaunting taya hangga't ang tagapagpatunay ay mapagkakatiwalaan pa rin (ang walang katiyakan na tagapagpatunay ay maaaring magdala ng peligro na pagbawas). Sa huli, ang mga taya sa lahat ng mga tagapagpatunay ay magkakaroon ng mas kaunting pagkakaiba-iba. Ito ay talagang pipigilan ang konsentrasyon ng taya at ang “nanalo ay mananalo palagi” na problemang nakikita sa ilang iba pang mga network.

Ang ilang mga bahagi ng bayarin sa gas ay igagantimpala din sa mga tagahatid para sa Cross-Chain na komunikasyon. Mangyaring mag-refer sa seksyong “[Tagahatid](#tagahatid)” sa ibaba.

# Ekonomiya ng Token

Ang BC at BSC ay naghahati sa parehong sandaigdig ng token para sa mga tokens na BNB at BEP2. Tinutukoy nito:

1. Ang parehong token ay maaaring umikot sa dalawang network, at dumadaloy sa pagitan ng mga ito ng magkabilaang direksyon sa pamamagitan ng mekanismo ng cross-chain na komunikasyon.
2. Ang kabuuang sirkulasyon ng parehong token ay dapat na pangasiwaan sa dalawang network, ibig sabihin, ang kabuuang epektibo na suplay ng isang token ay dapat na suma ng kabuuang epektibo na supply ng token sa parehong BSC at BC.
3. Ang mga tokens ay maaaring unang likhain sa BSC sa isang katulad na ayos sa ERC20 token na pamantayan, o sa BC bilang isang BEP2, pagkatapos ay nilikha sa kabila. Mayroong mga katutubong paraan sa parehong mga network para maidugtong ang dalawa at i-sigurado ang kabuuang supply ng token.

## Katutubong Token

Ang BNB ay tatakbo sa BSC sa parehong paraan tulad ng ETH na tumatakbo sa Ethereum para manatili ito bilang "katutubong token" para sa parehong BSC at BC. Nangangahulugan ito, bilang karagdagan sa BNB na ginagamit para bayaran ang karamihan sa mga bayarin sa Binance Chain at Binance DEX, gagamitin din ang BNB para:

1. magbayad ng "bayarin" para makapag lunsad ng mga matalinong kontrata sa BSC
2. itaya sa mga piling tagapagpatunay ng BSC, at makakuha ng kaukulang gantimpala
3. magsagawa ng mga operasyon na cross-chain, tulad ng paglipat ng mga token asset sa kabuuan ng BC at BSC

### Pondong Binhi

Ang ilang mga halaga ng BNB ay susunugin sa BC at huhulmahin sa BSC sa yugto ng genesis. Ang halagang ito ay tinatawag na "Pondong Binhi" para mag-ikot sa BSC pagkatapos ng unang bloke, na ipapadala sa paunang BC-patungo-sa-BSC na Tagahatid (inilarawan sa mga susunod na seksyon) at paunang itinakdang hanay ng tagapagpatunay na ipinakilala sa genesis. Ang mga BNB na ito ay ginagamit para magbayad ng mga bayarin sa transaksyon habang maaga para ilipat ang mas madaming BNB mula sa BC patungo sa BSC sa pamamagitan ng mekanismo ng cross-chain.

Ang BNB cross-chain na paglipat ay tinalakay sa isang susunod na seksyon, pero para sa paglipat mula sa BC patungong BSC, sa pangkalahatan ito ay para i-lock ang BNB sa BC mula sa pinagmulang address ng paglipat sa isang address na kontrolado ng sistema at i-unlock ang kaukulang halaga mula sa espesyal na kontrata papunta sa target na address ng paglipat sa BSC, o sa kabaligtaran, kapag ililipat mula sa BSC patungong BC, ito ay para i-lock ang BNB mula sa pinagmulang address sa BSC patungo sa isang espesyal na kontrata at palabasin ang naka-lock na halaga sa BC mula sa address ng sistema patungo sa target na address. Ang lohika ay nauugnay sa katutubong kodigo sa BC at isang serye ng mga matalinong kontrata sa BSC.

## Iba Pang Mga Token

Sinusuportahan ng BC ang mga tokens na BEP2 at paparating na [mga tokens na BEP8](https://github.com/binance-chain/BEPs/pull/69), na mga katutubong asset na maililipat at maibebenta (kung nakalista) sa pamamagitan ng mabilis na mga transaksyon at mababa sa isang segundong kawakasan. Samantala, dahil ang BSC ay katugma sa Ethereum, natural na suportahan ang mga tokens na ERC20 sa BSC, na kung saan dito ay tinatawag na “**BEP2E**” (na ang tunay na pangalan ay ipapakilala ng mga BEP sa hinaharap, potensyal itong sumasakop din sa BEP8). Ang BEP2E ay maaaring "Pinahusay" sa pamamagitan ng pagdaragdag ng ilang mga kakayahan para mailantad ang higit pang impormasyon, tulad ng denominasyon ng token, kahulugan ng katumpakan ng desimal at ang address ng may-ari na maaaring magpasya sa Token Binding sa mga kadena. Ang BSC at BC ay nagtutulungan para matiyak na ang isang token ay maaaring umikot sa parehong ayos na may kumpirmadong kabuuang panustos at magagamit sa iba't ibang mga kaso ng paggamit.

### Pagbigkis ng Token

Ang mga tokens na BEP2 ay ipapalawak para magsama ng isang bagong katangian para maiugnay ang token sa isang kontrata ng token ng BSC BEP2E, na tinatawag na “**Tagabigkis**”, at ang prosesong ito ng pagugnay ay tinatawag na “**Pagbigkis ng Token**”.

Ang Pagbigkis ng Token ay maaaring mangyari sa anumang oras matapos maging handa na ang BEP2 at BEP2E. Ang mga may-ari ng token na alinman sa BEP2 o BEP2E ay hindi kailangang mag-abala tungkol sa Pagbigkis, hanggang sa bago nila talagang nais na gamitin ang mga tokens sa iba't ibang mga sitwasyon. Ang mga tagapagbigay ay maaaring lumikha ng BEP2 muna o BEP2E muna, at maaari silang maibigkis sa ibang pagkakataon. Siyempre, hinihikayat para sa lahat ng mga tagapagbigay ng BEP2 at BEP2E na itakda nang maaga ang Pagbigkis pagkatapos ng pagbigay.

Ang isang tipikal na pamamaraan para maibigkis ang BEP2 at BEP2E ay magiging katulad sa ibaba:

1. Tiyaking kapwa ang token na BEP2 at ang token na BEP2E ay parehong umiiral sa bawat blockchain, na may parehong kabuuang supply. Ang BEP2E ay dapat mayroong 3 higit pang mga pamamaraan kaysa sa karaniwang ERC20 token na pamantayan:
    * `symbol()`: kunin ang simbolo ng token
    * `decimals()`: kunin ang bilang ng mga desimal na numero ng token
    * `owner()`: kunin ang **address ng may-ari ng kontrata ng BEP2E.** Ang halagang ito ay dapat na ipasimula sa taga-buo ng kontrata ng BEP2E para ang karagdagang pagbigkis na pagkilos ay maaaring magpatunay kung ang aksyon ay mula sa may-ari ng BEP2E.

2. Pagpasyahan ang paunang sirkulasyon sa parehong mga blockchain. Ipagpalagay na ang kabuuang supply ay *S*, at ang inaasahang paunang iikot na supply sa BC ay *K*, kung gayon dapat mag-lock ang may-ari ng S-K na dami ng token sa isang address na kontrolado ng sistema sa BC.

3. Katumbas nito, may *K* na dami ng mga tokens na naka-lock sa espesyal na kontrata sa BSC, na humahawak ng mga pangunahing kakayahan na pagbigkis at pinangalanang **TokenHub**. Ang tagapagbigay ng token na BEP2E ay dapat i-lock ang may *K* na dami ng mga tokens na iyon sa TokenHub, na magreresulta sa *S-K* na dami ng mga tokens na iikot sa BSC. Sa gayon ang kabuuang sirkulasyon sa 2 blockchain ay mananatili bilang *S*.

4. Ang nagbigay ng token na BEP2 ay nagpapadala ng transaksyon na pagbigkis sa BC. Kapag ang transaksyon ay matagumpay na naisakatuparan pagkatapos ng wastong pagpapatunay:
    * Naglilipat ito ng mga tokens na may *S-K* na dami sa isang address na kontrolado ng sistema sa BC.
    * Malilikha ang isang pakete na may hiling na cross-chain na pagbigkis, naghihintay para sa mga tagahatid na maghatid.

5. Ang mga Tagahatid sa BSC ay maghahatid ng pakete na may hiling na cross-chain na pagbigkis papunta sa **TokenHub** sa BSC, at ang kaukulang kahilingan at impormasyon ay ilalagay sa kontrata.

6. Ang may-ari ng kontrata at ang may-ari lang ang maaaring magpatakbo ng isang espesyal na pamamaraan ng kontrata ng TokenHub, ang `ApproveBind`, para mapatunayan ang hiling na pagbigkis para markahan ito bilang isang tagumpay. Kukumpirmahin nito:
    * ang token ay hindi pa nakabigkis;
    * ang pagbigkis ay para sa tamang simbolo, na may wastong kabuuang suplay at impormasyong desimal;
    * ang tamang lock ay tapos na sa parehong mga network;

10. Kapag nagtagumpay ang pamamaraang `ApproveBind`, mamarkahan ng TokenHub ang dalawang mga tokens na nakabigkis na at magkabahagi sa parehong sirkulasyon sa BSC, at ang istado ay ikakalat pabalik sa BC. Matapos ang pangwakas na kumpirmasyon na ito, ang address ng kontrata ng BEP2E at mga desimal ay isusulat sa token na BEP2 bilang isang bagong katangian sa BC, at ang mga tokens ay maaaring mailipat sa dalawang mga blockchain na magkabilaang direksyon. Kung nabigo ang ApproveBind, ang kaganapan ng kabiguan ay ikakalat din pabalik sa BC para palabasin ang mga naka-lock na token, at ang mga hakbang sa itaas ay maaaring subukang ulit sa paglaon.

# Cross-Chain na Paglipat at Komunikasyon

Ang cross-chain na komunikasyon ay ang pangunahing pundasyon para payagan ang komunidad na samantalahin ang istraktura ng dalawahang kadena:

* Ang mga user ay malayang lumikha ng anumang tokenization, mga produktong pampinansyal, at mga digital na assets sa BSC o BC ayon sa gusto nila
* ang mga item sa BSC ay maaaring manu-manong at naka-program na ikakalakal at ikakalat sa isang matatag, mataas na throughput, kasingbilis ng kidlat at magiliw na kapaligiran ng BC
* Maaaring mapatakbo ng mga user ang mga ito sa isang UI at ecosystem ng mga kasangkapan.

## Cross-Chain na Paglipat

Ang cross-chain na paglipat ay ang pangunahing komunikasyon sa pagitan ng dalawang mga blockchain. Sa madaling sabi ang lohika ay:

1. ang `transfer-out` blockchain ay ikakandado ang halaga mula sa mga address ng may-ari ng pinagmulan sa isang kinokontrol ng sistema na address/mga kontrata;
2. ang `transfer-in` blockchain ay bubuksan ang halaga mula sa kinokontrol ng sistema na address/ mga kontrata at ipadala ito sa mga target na address.

Dapat pahintulutan ng mensahe ng cross-chain na pakete ng paglipat ang BSC na mga Tagahatid at BC na mga **Orakulong Tagahatid** na patunayan:

1. Sapat na halaga ng mga token assets ay inalis mula sa pinagmulang address at naka-lock sa isang kontrolado ng sistema na mga address/mga kontrata sa pinagmulang blockchain. At maaaring makumpirma ito sa target na blockchain.
2. Ang mga wastong halaga ng mga token assets ay inilabas mula sa kontrolado ng sistema na mga address/mga kontrata at inilalaan sa mga target na address sa target na blockchain. Kung nabigo ito, makukumpirma ito sa pinagmulang blockchain, para ang naka-lock na token ay maaaring mailabas pabalik (maaaring ibawas ang mga bayarin).
3. Ang suma ng kabuuang sirkulasyon ng mga token assets sa kabuuan ng 2 mga blockchain ay hindi binago matapos makumpleto ang paglipat na kilos, kung magtagumpay man ang paglipat o hindi.

![cross-chain](./assets/cross-chain.png)

Ang arkitektura ng cross-chain na komunikasyon ay tulad ng nasa itaas na diagram. Upang mapaunlakan ang 2 mga heteroid na sistema, ang paghawak ng komunikasyon ay magkakaiba sa bawat direksyon.

## BC patungo sa BSC na Arkitektura

Ang BC ay isang blockchain na nakabatay sa Tendermint at may kagyat na kawakasan. Ang mga Tagapagpatunay na may hindi bababa sa ⅔\*N+1 ng kabuuang kapangyarihan sa pagboto ay kasabay na mag pipirma ng bawat bloke sa kadena. Kaya't praktikal na patunayan ang mga transaksyon sa bloke at kahit ang halaga ng estado sa pamamagitan ng **Ulo ng Bloke** at **Patunay na Merkle** nag pagpapatunay. Nasaliksik ito at ipinatupad bilang “**Protokol na Magaan na Kliyente**”, na masidhing tinalakay sa komunidad ng [Ethereum](https://github.com/ethereum/wiki/wiki/Light-client-protocol), pinag-aralan at ipinatupad para sa [Cosmos inter-chain na komunikasyon](https://github.com/cosmos/ics/blob/a4173c91560567bdb7cc9abee8e61256fc3725e9/spec/ics-007-tendermint-client/README.md).

Ang komunikasyon na BC-patungo-sa-BSC ay papatunayan sa isang “**on-chain na magaan na kliyente**” na ipinatupad sa pamamagitan ng BSC na **Mga Matalinong Kontrata** (ang ilan sa mga ito ay maaaring “**pre-compiled**”). Matapos ang ilang mga transaksyon at pagbabago ng estado na nangyari sa BC, kung ang isang transaksyon ay itinakda na mag-udyok ng cross-chain na komunikasyon, ang mensahe ng “**pakete**” na Cross-chain ay malilikha at ang **BSC na mga Tagahatid** ay magpapasa at magsusumite ng mga ito sa BSC bilang datos sa "build-in na mga sistemang kontrata". Ang mga build-in na mga sistemang kontrata ay papatunayan ang pakete at isasagawa ang mga transaksyon kung pumasa ito sa pagpapatunay. Gagarantiyahan ang pagpapatunay ng disenyo sa ibaba:

1. Ang estado sa pag-bloke ng BC ay isisink sa mga magaan na kliyente na kontrata sa BSC paminsan-minsan, sa pamamagitan ng ulo ng bloke at paunang mga komit, para sa mga impormasyon sa ibaba:
    * bloke at app hash ng BC na napirmahan ng mga tagapagpatunay
    * kasalukuyang hanay ng mga tagapagpatunay, at pinakabagong hanay ng mga tagapagpatunay

2. ang susi-halaga mula sa estado ng blockchain ay papatunayan batay sa Patunay na Merkle at impormasyon mula sa itaas #1.

Matapos kumpirmahing na ang susi-halaga ay tumpak at mapagkakatiwalaan, ang build-in na mga sistemang kontrata ay isasagawa ang mga aksyon na naaayon sa mga cross-chain na pakete. Ang ilang mga halimbawa ng naturang mga pakete na maaaring likhain para sa BC-patungo-sa-BSC ay:

1. Bind: ibigkis ang mga tokens ng BEP2 at BEP2E
2. Paglipat: paglipat ng mga tokens pagkatapos ng pagbigkis, nangangahulugan ito na ang sirkulasyon ay bababa (mai-lock) mula sa BC at lilitaw sa balanse ng target na address sa BSC
3. Pangangasiwa ng Kamalian: para hawakan ang anumang kaganapan sa pag-timeout/pagkabigo para sa komunikasyon ng BSC-patungo-sa-BC
4. Pinakabagong hanay ng mga tagapagpatunay ng BSC

Upang matiyak na walang pagkopya, tamang pagkakasunud-sunod ng mensahe at napapanahong pag-timeout, mayroong isang konseptong "Channel" na ipinakilala sa BC para pangasiwaan ang anumang uri ng komunikasyon.

Para sa mga tagahatid, mangyaring mag-refer din sa ibaba ng seksyong "Tagahatid".

## BSC patungo sa BC na Arkitektura

Gumagamit ang BSC ng Patunay ng Itinayang Awtoridad na protokol ng pagkakasunduan, na mayroong pagkakataon na magsanga at nangangailangan ng kumpirmasyon ng mas madaming mga bloke. Ang isang bloke ay mayroon lang pirma ng isang tagapagpatunay, kaya't hindi madaling umasa sa isang bloke para mapatunayan ang datos mula sa BSC.

Upang ganap na samantalahin ang korum ng tagapagpatunay ng BC, isang ideyang katulad sa maraming [Tulay](https://github.com/poanetwork/poa-bridge) o Orakulong mga blockchain ang gagamitin:

1. Ang mga kahilingan sa cross-chain na komunikasyon mula sa BSC ay isusumite at isinasagawa sa BSC bilang mga transaksyon. Ang pagsasagawa ng transanction ay magpapalabas ng `Events`, at ang mga naturang kaganapan ay maaaring sundin at ibalot sa ilang mga “**Orakulo**” papunta sa BC. Sa halip na Mga Ulo ng Bloke, Hash at Patunay na Merkle, ang ganitong uri ng "Orakulo" na pakete na direktang naglalaman ng impormasyong cross-chain para sa mga pagkilos, tulad ng nagpadala, tatanggap at halaga na ililipat.
2. Upang matiyak ang seguridad ng Orakulo, ang mga tagapagpatunay ng BC ay bubuo ng isa pang korum ng mga “**Orakulong Tagahatid**”. Ang bawat tagapagpatunay ng BC ay dapat magpatakbo ng isang **nakatuon na proseso** bilang Orakulong Tagahatid. Ang mga Orakulong Tagahatid na ito ay magsusumite at magboboto para sa cross-chain na pakete ng komunikasyon, tulad ng Orakulo, papunta sa BC, gamit ang parehong mga susi ng tagapagpatunay. Anumang pakete na nilagdaan ng higit sa ⅔\*N+1 na kapangyarihan ng pagboto ng mga Orakulong Tagahatid ay kasing ligtas ng anumang bloke na nilagdaan ng ⅔\*N+1 ng parehong kapangyarihan ng pagboto ng korum ng mga tagapagpatunay.

Sa paggamit ng parehong korum ng tagapagpatunay, nilalagay nito ang kodigo ng magaan na kliyente sa BC at ang tuluy-tuloy na mga pagbabago ng bloke sa BC. Ang nasabing mga Orakulo ay mayroon ding mga Orakulo ID at uri, para matiyak ang pagkakasunud-sunod at wastong pangangasiwa ng kamalian.

## Pag-timeout at Pangangasiwa ng Kamalian

May mga sitwasyon na hindi nagtatagumpay ang komunikasyon sa cross-chain. Halimbawa, ang hinatid na pakete ay hindi maaaring maipatupad sa BSC dahil sa ilang mga mali sa kodigo ng mga kontrata. **Ang pag-timeout at Pangangasiwa ng Kamalian na mga lohika** ay ginagamit sa mga nasabing senaryo.

Para sa kilalang mga kamalian ng user at ng sistema o anumang inaasahang pagbubukod, dapat na pagalingin ng dalawang network ang kanilang sarili. Halimbawa, kapag nabigo ang paglipat galing sa BC patungo sa BSC, maglalabas ang BSC ng isang kaganapan sa kabiguan at ang mga Orakulong Tagahatid ay magsasagawa ng isang pagsasauli ng bayad sa BC; kapag nabigo ang paglipat galing sa BSC patungo sa BC, maglalabas ang BC ng isang pakete ng pagsasauli ng bayad para ihatid ng Tagahatid para ma-unlock ang pondo.

Gayunpaman, ang hindi inaasahang pagkakamali o pagbubukod ay maaari pa ring mangyari sa anumang hakbang ng cross-chain na komunikasyon. Sa ganitong kaso, matutuklasan ng Tagahatid at mga Orakulong Tagahatid na ang kaukulang cross-chain channel ay natigil sa isang partikular na pagkakasunud-sunod. Pagkatapos ng isang yugto ng Pag-timeout, ang mga Tagahatid at mga Orakulong Tagahatid ay maaaring humiling ng isang transaksyon na “SkipSequence”, ang natigil na pagkakasunud-sunod ay mamarkahan bilang "Hindi mapatakbo". Itataas ang isang kaukulang alerto, at kailangang talakayin ng komunidad kung paano pangangasiwaan ang senaryong ito, hal. ibalik ang bayad sa pamamagitan ng isponsor ng mga tagapagpatunay, o kahit na linisin ang pondo sa susunod na pagbago sa network.

## Cross-Chain na Karanasan ng User

Mas mainam na ang mga user ay umaasang gagamit ng dalawang magkatulad na mga kadena sa parehong paraan tulad ng paggamit nila ng isang solong kadena. Nangangailangan ito ng mas madaming pinagsama-samang mga uri ng transaksyon para maidagdag sa cross-chain na komunikasyon para paganahin ito, na magdaragdag ng labis na pagkakumplikado, mahigpit na pagkakaugnay, at pagpapanatili na pasanin. Dito ipinapatupad lang ng BC at BSC ang mga pangunahing operasyon para paganahin ang daloy ng halaga sa paunang paglulunsad at iwanan ang karamihan ng trabaho sa karanasan ng user sa UI na panig ng kliyente, tulad ng mga pitaka. Hal. ang isang mahusay na pitaka ay maaaring payagan ang mga user na magbenta ng isang token nang direkta mula sa BSC papunta sa DEX order book ng BC, sa isang ligtas na paraan.

## Kaganapan sa Kontrata ng Cross-Chain

Ang Kaganapan sa Kontrata ng Cross-Chain (CCCE) ay idinisenyo para payagan ang isang matalinong kontrata na mag-udyok ng mga cross-chain na transaksyon, direkta sa pamamagitan ng kodigo ng kontrata. Nagiging posible ito batay sa:

1. Ang karaniwang mga sistemang kontrata ay maaaring ibigay para maghatid ng mga operasyon na maaaring tawagin ng pangkalahatang matalinong mga kontrata;
2. Ang karaniwang mga kaganapan ay maaaring mailabas ng karaniwang mga kontrata;
3. Ang mga Orakulong Tagahatid ay maaaring makuha ang karaniwang mga kaganapan, at ma-udyok ang kaukulang mga operasyon ng cross-chain;
4. Ang nakatuon na address na pinangangasiwaan ng kodigo (account) ay maaaring likhain sa BC at mai-access ng mga kontrata sa BSC, dito pinangalanan bilang **Address ng Kontrata sa BC” (CAoB)**.

Maraming karaniwang pagpapatakbo ang ipinatupad:

1. BSC patungo sa BC na paglipat: ipinatupad ito sa parehong paraan tulad ng normal na BSC patungo sa BC na paglipat, nag-uudyok lang sa pamamagitan ng karaniwang kontrata. Ang pondo ay maaaring ilipat sa anumang address sa BC, kabilang ang kaukulang CAoB ng kontrata na pinagmulan ng paglipat.
2. Paglipat sa BC: ipinapatupad ito bilang isang espesyal na cross-chain na paglipat, habang ang totoong paglipat ay mula sa **CAoB** papunta sa anumang iba pang address (kahit na isa pang CAoB).
3. BC patungo sa BSC na paglipat: ipinatutupad ito bilang dalawang-pass na cross-chain na komunikasyon. Ang una ay na-udyok ng kontrata ng BSC at pinalaganap sa BC, at pagkatapos ay sa pangalawang pass, magsisimula ang BC ng isang normal na BC patungo sa BSC cross-chain na paglipat, mula sa **CAoB** hanggang sa address ng kontrata sa BSC. Ang isang espesyal na tala ay dapat bayaran na ang kontrata ng BSC ay nagdaragdag lang ng balanse sa anumang paglipat na papasok sa pangalawang pass, at ang pangangasiwa ng kamalian sa pangalawang pass ay kapareho ng normal na BC patungo sa BSC na paglipat.
4. IOC (Agaran-O-Kanselahin) na Kalakalan Palabas: ang pangunahing layunin ng paglilipat ng mga assets sa BC ay ang makipagkalakalan. Ang kaganapan na ito ay magtuturo para ipagpalit ang isang tiyak na halaga ng isang asset sa CAoB sa isa pang pag-aari hangga't maaari at ilipat palabas ang lahat ng mga resulta, ibig sabihin, ang natira, ang mapagkukunan at mga ipinalit na target na token ng kalakalan, pabalik sa BSC. Hahawakan ng BC ang mga nasabing hinatid na kaganapan sa pamamagitan ng pagpapadala ng isang "Agaran-O-Kanselahin", ibig sabihin, IOC na utos sa mga pares ng pangangalakal, sa sandaling ang susunod na pagtutugma ay natapos, ang resulta ay maihahatid pabalik sa BSC, na maaaring nasa alinman sa isa o dalawang mga pag-aari.
5. Subasta na Kalakalan Palabas: Ang naturang kaganapan ay magtuturo sa BC na magpadala ng isang subasta na utos para ipagpalit ang isang tiyak na halaga ng isang asset sa **CAoB** sa isa pang pag-aari hangga't maaari at ilipat palabas ang lahat ng mga resulta pabalik sa BSC sa pagtatapos ng subasta Paparating ang pagpapaandar sa subasta sa BC.

Mayroong ilang mga detalye para sa Kalakalan Palabas:

1. kapwa maaaring magkaroon ng isang limitasyong presyo (ganap o naaayon) para sa kalakal;
2. ang huling resulta ay isusulat bilang mga cross-chain na pakete para maihatid pabalik sa BSC;
3. ang mga bayarin sa cross-chain na komunikasyon ay maaaring singilin mula sa asset na inilipat pabalik sa BSC;
4. ang kontrata ng BSC ay nagpapanatili ng isang salamin ng balanse at natitirang mga order sa CAoB. Hindi alintana kung anumang kamalian ang mangyari sa panahon ng Kalakalan Palabas, ang huling katayuan ay ikakalat pabalik sa pinagmulan na kontrata at linisin ang panloob na estado.

Sa mga katangian sa itaas, nagdaragdag lang ito ng cross-chain na paglipat at mga kakayahan na maglipat na may mataas na liquidity sa lahat ng mga matalinong kontrata sa BSC. Lalo nitong idaragdag ang mga sitwasyon ng aplikasyon sa Matalinong Kontrata at dApps, at gagawing 1 kadena +1 kadena > 2 kadena.

# Pagtaya at Pamamahala

Ang Patunay ng Itinayang Awtoridad ay nagdudulot ng desentralisasyon at paglahok sa komunidad. Ang pangunahing lohika nito ay maaaring ibuod ayon sa ibaba. Maaari kang makakita ng mga katulad na ideya mula sa iba pang mga network, lalo na ang Cosmos at EOS.

1. Ang mga may hawak ng token, kasama ang mga tagapagpatunay, ay maaaring maglagay ng kanilang mga tokens na “**bonded**” sa taya. Ang mga may hawak ng token ay maaaring **magtalaga** ng kanilang mga tokens sa anumang tagapagpatunay o kandidatong tagapagpatunay, para asahan na maaari itong maging isang aktwal na tagapagpatunay, at sa paglaon maaari silang pumili ng ibang tagapagpatunay o kandidato para **muling magtalaga** ng kanilang mga tokens <sup>1</sup>.
2. Ang lahat ng mga kandidatong tagapagpatunay ay mairaranggo base sa bilang ng mga bonded na token sa kanila, at ang nangungunang sa mga ito ay magiging totoong mga tagapagpatunay.
3. Maaaring ibahagi (bahagi ng) ng mga Tagapagpatunay ang kanilang gantimpala sa pag-bloke sa kanilang mga delegado.
4. Ang mga Tagapagpatunay ay maaaring magdusa mula sa “**Pagbawas**”, isang parusa para sa kanilang mga masamang pagkilos, tulad ng dobleng pagpirma at/o kawalang-tatag. Ang nasabing pagkawala ay ibabahagi pati na rin ng kanilang **mga delegado**.
5. Mayroong isang "**unboding na panahon**" para sa mga tagapagpatunay at delegado para masiguro ng sistema na ang mga tokens ay mananatiling naka-bond kapag nahuli ang mga masamang pagkilos, ang mananagot ay mababawasan sa panahong ito.

## Pagtaya sa BC

Mas mainam na ang naturang lohika ng pagtaya at gantimpala ay dapat na parte na blockchain, at awtomatikong pinapatupad habang nangyayari ang pag-bloke. Ang Cosmos Hub, na nagbabahagi ng parehong Tendermint na pagkakasunduan at mga librerya sa Binance Chain, ay gumagana sa ganitong paraan.

Naghahanda ang BC para paganahin ang lohika ng pagtaya mula pa noong mga araw ng pagdisenyo nito. Sa kabilang panig, tulad ng nais ng BSC na manatiling katugma sa Ethereum hangga't maaari, ito ay isang malaking hamon at pagsisikap na ipatupad ang naturang lohika dito. Totoo ito lalo na kapag ang Ethereum mismo ay maaaring lumipat sa ibang Patunay ng Taya na protokol ng pagkakasunduan sa isang maikling (o mas matagal) na oras. Upang mapanatili ang pagiging tugma at magamit ulit ang magandang pundasyon ng BC, ang lohika ng pagtyaa ng BSC ay ipinatupad sa BC:

1. Ang token sa pagtaya ay BNB, dahil ito ay isang katutubong token sa parehong mga blockchain gayon pa man
2. Ang pagtaya, ibig sabihin, token bond at pagkilos ng delegasyon at mga tala para sa BSC, ay nangyayari sa BC.
3. Ang hanay ng tagapagpatunay ng BSC ay natutukoy sa pamamagitan ng pagtaya at delegado na lohika, sa pamamagitan ng isang modyul ng pagtaya na itinayo sa BC para sa BSC, at pinalaganap araw-araw UTC 00:00 mula BC hanggang BSC sa pamamagitan ng Cross-Chain na komunikasyon.
4. Ang pamamahagi ng gantimpala ay nangyayari sa BC sa humigit-kumulang araw-araw UTC 00:00.

## Paggantimpala

Parehong nangyayari ang pag-update ng tagapagpatunay at pamamahagi ng gantimpala araw-araw ng UTC 00:00. Ito ay para makatipid sa gastos ng madalas na mga pag-update ng staking at pamamahagi ng gantimpala ng bloke. Ang gastos na ito ay maaaring maging malaki, dahil ang gantimpala ng bloke ay nakokolekta sa BSC at ibinabahagi sa BC sa mga tagapagpatunay at delegado ng BSC. (Mangyaring tandaan na ang mga bayarin sa pag-bloke ng BC ay mananatiling makabuluhan sa mga tagapagpatunay lang ng BC.)

Ang isang sadyang pagkaantala ay ipinakilala dito para matiyak na ang pamamahagi ay patas:

1. Ang gantimpala sa pag-bloke ay hindi ipapadala kaagad sa tagapagpatunay, sa halip, ipapamahagi at maiipon ito sa isang kontrata;
2. Sa pagtanggap ng itinatakdang pag-update ng tagapagpatunay sa BSC, mag-uudyok ito ng ilang mga cross-chain na paglipat para ilipat ang gantimpala sa mga address ng pangangalaga sa mga kaukulang tagapagpatunay. Ang mga address ng pangangalaga ay pag-aari ng sistema para hindi magastos ang gantimpala hangga't hindi nangyayari ang ipinangakong pamamahagi sa mga delegado.
3. Upang gawing mas simple ang sinkronisasyon at maglaan ng oras para mapaunlakan ang pagbawas, ang gantimpala para sa N na araw ay ibabahagi lang sa N+2 na araw. Matapos makuha ng mga delegado ang gantimpala, ililipat ang natira sa sariling mga address ng gantimpala ng mga tagapagpatunay.

## Pagbawas

Ang pagbawas ay bahagi ng on-chain na pamamahala, para matiyak na ang mga nakakahamak o negatibong pagkilos ay maparusahan. Ang bawas sa BSC ay maaaring isumite ng sinuman. Ang pagsusumite ng transaksyon ay nangangailangan ng **ebidensya ng bawas** at mga bayarin sa gastos pero nagdadala din ng isang mas malaking gantimpala kapag ito ay matagumpay.

Sa ngayon mayroong dalawang mga kaso na maaaring maisagawa ang pagbawas.

### Dobleng Pagpirma

Ito ay lubos na seryosong kamalian at malamang ay sinadyang kasalanan kapag ang isang tagapagpatunay ay nagpirma ng higit sa isang bloke na may parehong taas at magulang na bloke. Ang implementasyon ng sanggunian na protokol ay dapat na meron ng lohika para maiwasan ito, kaya ang nakakahamak na kodigo lang ang maaaring mag-udyok nito. Kapag nangyari ang Dobleng Pagpirma, dapat alisin kaagad ang tagapagpatunay mula sa **Hanay** ng Tagapagpatunay.

Ang sinuman ay maaaring magsumite ng isang hiling na pagbawas sa BC na may katibayan ng Dobleng Pagpirma ng BSC, na dapat maglaman ng 2 ulo ng bloke na may parehong taas at magulang na bloke, na tinatakan ng nagkasala na tagapagpatunay. Sa pagtanggap ng ebidensya, kung mapatunayan ito ng BC na totoo:

1. Ang tagapagpatunay ay aalisin mula sa hanay nito ng isang instansiya ng hanay ng tagapagpatunay ng BSC na update sa Cross-Chain;
2. Ang taya sa tagapagpatunay ay babawasan ng paunang natukoy na halaga;
3. Bahagi ng nabawasan na BNB ay ilalaan sa address ng nagsumite, na kung saan ay isang gantimpala at mas malaki kaysa sa gastos ng pagsumite ng transaksyon sa paghiling ng pagbawas
4. Ang natitirang nabawasan na BNB ay ilalaan sa ibang mga address na nasa pangangalaga ng mga tagapagpatunay, at ibabahagi sa lahat ng mga delegado sa parehong paraan ng gantimpala sa pag-bloke.

### Hindi Nagagamit

Ang pagka aktibo ng BSC ay nakasalalay na lahat sa Patunay ng Itinayang Awtoridad na hanay ng tagapagpatunay ay makakagawa ng mga bloke ng napapanahon kapag pagkakataon na nila. Ang mga Tagapagpatunay ay maaaring makaligtaan ang kanilang pagkakataon dahil sa anumang kadahilanan, lalo na ang mga problema sa kanilang hardware, software, pagsasaayos o network. Ang kawalang-tatag ng operasyon na ito ay makakasakit sa kakayahang pagganap at magpapakilala ng higit na hindi matukoy na aspeto sa sistema.

Maaaring may isang panloob na matalinong kontrata na responsable sa pagtatala ng mga hindi nasagot na sukatan ng pag-bloke ng bawat tagapagpatunay. Kapag ang mga sukatan ay nasa itaas na ng paunang natukoy na threshold, ang gantimpala sa pag-bloke para sa tagapagpatunay ay hindi maihahatid sa BC para sa pamamahagi pero ibabahagi sa iba pang mas mahusay na mga tagapagpatunay. Sa paraang iyon, ang tagapagpatunay na hindi maganda ang pagpapatakbo ay dapat na unti-unting iboto paalis mula sa itinakdang tagapagpatunay dahil ang kanilang mga delegado ay tatanggap ng mas kaunti o walang gantimpala. Kung ang mga sukatan ay mananatili sa itaas ng isa pang mas mataas na antas ng threshold, ang tagapagpatunay ay mahuhulog mula sa pag-ikot, at ito ay ikakalat pabalik sa BC kapag may isang Pagbawas na magaganap sa taya ng tagapagpatunay.

### Mga Parametro sa Pamamahala

Maraming mga parametro ng sistema para makontrol ang pagkilos ng BSC, hal. halaga ng pagbawas, bayad sa cross-chain na paglipat. Ang lahat ng mga parametro na ito ay matutukoy ng BSC na Hanay ng Tagapagpatunay nang sama-sama sa pamamagitan ng proseso ng pagboto ng panukala batay sa kanilang pagtaya. Ang nasabing proseso ay isasagawa sa BC, at ang mga bagong halaga ng parametro ay kukunin ng kaukulang mga sistemang kontrata sa pamamagitan ng isang cross-chain na komunikasyon.

# Mga Tagahatid

Ang mga tagahatid ang responsable sa pagsumite ng mga Cross-Chain na Komunikasyon na Pakete sa pagitan ng dalawang mga blockchain. Dahil sa magkakaiba-ibang istraktura ng magkahanay na kadena, dalawang magkaibang uri ng Tagahatid ang nalikha.

## Mga Tagahatid ng BSC

Ang mga tagahatid para sa komunikasyon ng BC patungo sa BSC ay tinatawag na mga “**Tagahatid ng BSC**”, o simpleng mga "Tagahatid". Ang Paghatid ay isang nakapag-iisang proseso na maaaring patakbuhin ng sinuman, at saanman, maliban na ang mga Tagahatid ay dapat magparehistro ng kanilang sarili sa BSC at magdeposito ng isang tiyak na naibabalik na halaga ng BNB. Ang mga kahilingan lang sa paghatid mula sa mga nakarehistrong Tagahatid ang tatanggapin ng BSC.

Ang pakete na hinahatid nila ay papatunayan ng on-chain na magaan na kliyente sa BSC. Ang matagumpay na paghatid ay kailangang pumasa sa sapat na pagpapatunay at may gastos na mga bayarin sa gas sa BSC, at sa gayon ay dapat mayroong gantimpalang insentibo para mahikayat ang komunidad na magpatakbo ng mga Tagahatid.

### Mga Insentibo

Mayroong dalawang pangunahing uri ng komunikasyon:

1. Mga Operasyon na inudyok ng mga user, tulad ng `token bind` o `cross chain transfer`. Dapat magbayad ang mga user ng karagdagang bayad bilang gantimpala ng tagahatid. Ibabahagi ang gantimpala sa mga tagahatid na nagsisink sa mga natukoy na mga ulo ng blockchain. Bukod, ang gantimpala ay hindi mababayaran nang direkta sa mga account ng mga tagahatid. Ipapatupad ang isang mekanismo ng pamamahagi ng gantimpala para maiwasan ang monopolisasyon.
2. Sinkronisasyon ng Sistema, tulad ng paghahatid ng `refund package` (sanhi ng mga pagkabigo ng karamihan sa mga orakulong tagahatid), espesyal na sinkronisasyon ng ulo ng blockchain (ang ulo ay naglalaman ng pag-update ng hanay ng tagapagpatunay ng BC), pakete ng pagtaya ng BSC. Ang kontrata ng gantimpala ng sistema ay magbabayad ng gantimpala sa mga account ng mga tagahatid nang direkta.

Kung ang ilang mga Tagahatid ay may mas mabilis na mga network at mas mahusay na hardware, maaari nilang i-monopolyo ang lahat ng paghatid ng pakete at walang maiiwan na gantimpala sa iba. Sa gayon mas kaunting mga kalahok ang sasali para sa paghatid, na hihikayat ng sentralisasyon at pipinsala sa kahusayan at seguridad ng network. Mas mainam, dahil sa desentralisasyon at dinamikong muling halalan ng mga tagapagpatunay ng BSC, ang isang Tagahatid ay maaaring hindi palaging ang una na maghatid ng bawat mensahe. Pero para maiwasan ang karagdagang monopolisasyon, ang ekonomiya ng paggantimpala ay espesyal din na idinisenyo para mabawasan ang nasabing pagkakataon:

1. Ang gantimpala para sa mga Tagahatid ay ibabahagi lang ayon sa pagkapangkat, at ang isang pangkat ang sasaklaw sa isang bilang ng mga matagumpay na naihatid na pakete.
2. Ang gantimpala na maaaring makuha ng isang Tagahatid mula sa isang pamamahagi sa pagkapangkat ay hindi tuwid ang proporsyon sa bilang ng kanilang mga matagumpay na naihatid na pakete. Sa halip, maliban sa unang ilang mga paghatid, kapag mas maraming naihatid ang isang Tagahatid sa panahon ng isang pangkat, mas kaunting gantimpala ang makokolekta nito.

## Mga Orakulong Tagahatid

Ang mga tagahatid para sa komunikasyon ng BSC patungo sa BC ay gumagamit ng modelong "Orakulo", at tinaguriang mga “**Orakulong Tagahatid**”. Ang bawat isa sa mga tagapagpatunay ay dapat, at ang nasa hanay ng tagapagpatunay lang, ang magpatakbo ng mga Orakulong Tagahatid. Pinapanood ng bawat Orakulong Tagahatid ang pagbabago ng estado ng blockchain. Kapag nahuli nito ang Mga Pakete ng Cross-Chain na Komunikasyon, isusumite ito para bumoto para sa mga kahilingan. Pagkatapos ng mga Orakulong Tagahatid mula sa ⅔ ng kapangyarihan sa pagboto ng mga tagapagpatunay ng BC na bumoto para sa mga pagbabago, isasagawa ang mga pagkilos na cross-chain.

Dapat maghintay ang Orakulong Tagahatid para sa sapat na mga bloke para kumpirmahin ang kawakasan sa BSC bago magsumite at bumto para sa mga cross-chain na pakete ng komunikasyon patungoo sa BC.

Ang mga bayarin sa cross-chain ay ibabahagi sa mga tagapagpatunay ng BC kasama ang normal na mga gantimpala sa pag-bloke sa BC.

Ang nasabing orakulong uri ng paghatid ay nakasalalay sa lahat ng mga tagapagpatunay na suportahan. Dahil ang lahat ng mga boto para sa mga pakete ng cross-chain na komunikasyon ay naitala sa blockchain, hindi mahirap magkaroon ng isang panukat na sistema para masuri ang kakayahan sa pagganap ng mga Orakulong Tagahatid. Ang pinakamahinang tagaganap ay maaaring ang kanilang mga gantimpala ay kalmutin pabalik sa pamamagitan ng isa pang Pagbawas na lohika na ipinakilala sa hinaharap.

# Pananaw

Mahirap magtapos para sa Binance Chain, dahil hindi ito tumitigil sa pag-unlad. Ang diskarte sa dalawahang kadena ay para buksan ang pintuan para sa mga user para samantalahin ang mabilis na paglilipat at pakikipagkalakalan sa isang panig, at may kakayahang umangkop at napapalawak na pag-program sa kabilang panig, pero ito ay magiging isang hintuan sa pagbuo ng Binance Chain. Nasa ibaba ang mga paksang maaaring tingnan para mas mapadali ang komunidad para sa mas higit pa na kakayahang magamit at mapalawak:

1. Magdagdag ng iba't ibang modelo ng digital na asset para sa iba't ibang mga kaso ng paggamit sa negosyo
2. Paganahin ang mas marami pang pinagkukunan ng mga datos, lalo na ang mga datos ng merkado ng DEX, na ipaparating mula sa Binance DEX patungo sa BSC
3. Magbigay ng interface at pagiging tugma para ma-integrate sa Ethereum, kasama ang karagdagang pagsulong, at iba pang blockchain
4. Pagbutihin ang karanasan sa panig ng kliyente sa pangangasiwa ng mga pitaka at sa mas madaling paggamit ng blockchain



------

[1]: Ang mga propesyonal sa negosyo sa BNB ay maaaring magbigay ng iba pang mga benepisyo para sa mga delegado ng BNB, tulad ng ginagawa nila ngayon para sa mga pangmatagalang may hawak ng BNB.
