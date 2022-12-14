# Multiparty Threshold ECDSA

## Publications

### GG-series

- GG18 [[paper](https://eprint.iacr.org/2019/114.pdf), [code from Binance](https://github.com/bnb-chain/tss-lib)]
  - [[Video] Short Concept Introduction](https://dl.acm.org/doi/10.1145/3372297.3423367#)
- GG20 [[paper](https://eprint.iacr.org/2020/540.pdf), [code from Coinbase](https://github.com/coinbase/kryptology)]
- GG21 [[paper](https://eprint.iacr.org/2021/060.pdf), code]
  ![Performance Comparison](/img/gg21_fig1.png)

  - [[Video] Short Concept Introduction](https://dl.acm.org/doi/10.1145/3372297.3423367#)
  - [Introduction from Fireblocks](https://www.fireblocks.com/blog/ccs-threshold-ecdsa/)
  
  [![Technical Overview (Must Read)](https://img.youtube.com/vi/zXCSPWxWA-s/sddefault.jpg)](https://www.youtube.com/watch?v=zXCSPWxWA-s)
  *Technical Overview (Must Read)*
  
  - Preliminaries
    - Proactive Key Refresh
    - Universally Composable (UC) Security Framework
    - leveraging [Paillier Encryption (from wikipedia)](https://en.wikipedia.org/wiki/Paillier_cryptosystem) as a commitment scheme
    - Pedersen Commitments
    - DDH

### Other Important Papers

- [2022 Better than Advertised Security for Non-interactive Threshold Signatures](https://crypto.iacr.org/2022/papers/538806_1_En_18_Chapter_OnlinePDF.pdf)
  - [Source Code(Python)](https://github.com/mmaller/multi_and_threshold_signature_reductions)
- [2022 Low-Bandwidth Threshold ECDSA via Pseudorandom Correlation Generators](https://eprint.iacr.org/2021/1587.pdf)
- [2022 Fast Threshold ECDSA with Honest Majority](https://eprint.iacr.org/2020/501.pdf)
- [2022 On the security of ECDSA with additive key derivation and presignatures](https://eprint.iacr.org/2021/1330.pdf)
- [2020 Threshold ECDSA for Decentralized Asset Custody](https://eprint.iacr.org/2020/498.pdf)
  - [Source Code(Go)](https://github.com/aleph-zero-foundation/threshold-ecdsa)
- [2018 Fast Secure Multiparty ECDSA with Practical Distributed Key Generation and Applications to Cryptocurrency Custody](https://eprint.iacr.org/2018/987.pdf)
- [2020 Securing DNSSEC Keys via Threshold ECDSA From Generic MPC](https://eprint.iacr.org/2019/889.pdf)
  - another pre-signing protocol
  - [[Video] MPTS 2020 Talk 3a2: Securing DNSSEC Keys via Threshold ECDSA From Generic MPC](https://csrc.nist.gov/presentations/2020/mpts2020-3a2)
  - [[Slide]](https://csrc.nist.gov/CSRC/media//Events/mpts2020/slides/mpts2020-3a2-talk-kris.pdf)

## Resources

- [[Github] Multi-party ECDSA](https://github.com/ZenGo-X/multi-party-ecdsa)
  - including GG20
  - implemented by Rust
  - [[Github] TSS ECDSA CLI utility](https://github.com/cryptochill/tss-ecdsa-cli)
- [[Github] Multiparty threshold ECDSA scheme](https://github.com/ing-bank/threshold-signatures)
  - based on GG18
  - implmeneted by Rust
  
---

## Tutorial

### Basic Concept of Cryptography

- 4 Characteristics of Cryptography
  - 機密性（Confidentiality）：確保資料只會給對方看到
  - 完整性（Integrity）：確保資料的完整性
  - 身份驗證（Authentication）：傳送和接收都需要驗證
  - 不可否認性（Non-Reputation）：提供雙方互動的證明
- Kerckhoffs’ principle
  - 古典密碼學和現代密碼學最大的區別就是在有柯克霍夫原則後才開始有了變化，柯克霍夫原則（Kerckhoffs’ principle），大致上就是在強調即使密碼系統的任何細節被人知道了，只要密鑰（key）未洩漏，它也是安全的。換句話說，加密技術就算演算法被知道了，資料也不會有危險。
- [[2021 iThome 鐵人賽]學密碼學也猜不到你的手機密碼](https://ithelp.ithome.com.tw/users/20140112/ironman/3930)
  - RC4, DES, AES and RSA
  - [ECC (Elliptic Curve Cryptography;橢圓曲線密碼學)](https://ithelp.ithome.com.tw/articles/10268495)
    - [Day 24. 非對稱式加密演算法 - 橢圓曲線密碼學 Elliptic Curve Cryptography , ECC (觀念篇)](https://ithelp.ithome.com.tw/articles/10251031)
  - [DHKE、ECDH、ElGamal](https://ithelp.ithome.com.tw/articles/10271893)
  - [ECDSA](https://ithelp.ithome.com.tw/articles/10275773)
  - [地址 Address](https://ithelp.ithome.com.tw/articles/10279688)
- [[YouTube] NCSSM's Cryptography](https://www.youtube.com/playlist?list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro)
  - Ciphers
    - Transposition Ciphers: Reverse, Rail Fence, Route
    - Substitution Ciphers: Atbash, Caesar, multiplicative, Tabula Recta, Trithemius,  Vigenere, Autokey, **Affine, Hill, Playfair**
  - [Index of Coincidence](https://www.youtube.com/watch?v=kty-dCB4AAk&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=22)
  - [Kasiski Test](https://www.youtube.com/watch?v=asRbswE2hFY&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=23)
  - [Linear Feedback Shift Register (LFSR)](https://www.youtube.com/watch?v=Y0DlCM4iKeA&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=29)
  - [Diffie-Hellman Key Exchange Problem](https://youtu.be/NHCsgISM6BY?t=318)
  - [The Extended Euclidean Algorithm (EEA)](https://www.youtube.com/watch?v=WKSlsFTH8hs&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=33)
  - [Euler's Totient Function $\Phi(n)$ ](https://www.youtube.com/watch?v=CTbdowq0ZB8&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=34)
    - if `p` is prime, then: $\Phi(p) = p -1$.
    - if `p` and `q` are both primes, and `n = pq`, then: $\Phi(n)=\Phi(pq)=\Phi(p)*\Phi(q)=(p-1)(q-1)$
-[[Video]RSA 歷史原由與設計說明](https://www.youtube.com/watch?v=wXB-V_Keiu8)
-[[MOOC]区块链中的密码学](https://www.youtube.com/watch?v=uGenWpoFDG0&list=PLv8hyYaXsdish--YdAtaFXnDDsYMBQJXz)
-[[Explore the Cryptography World]](https://www.youtube.com/playlist?list=PL-qvsLbZq06LvdO6L7byZfcigeQAEo2k6)
-[Day 21. 加密演算法要注意的那些毛 (一) - 加密模式](https://ithelp.ithome.com.tw/articles/10249953)
  - ECB, CBC[區塊鏈(blockchain)的鼻祖], CFB, OFB, CTR
  - [AES, Advanced Encryption Standard，其實是一套標準：FIPS 197，而我們所說的AES演算法 就是Rijndael演算法](https://ithelp.ithome.com.tw/articles/10249488) 
  - [RSA 流程推導與實例說明](RSA 簡介)
  
### Elliptic Curve Cryptography (ECC)

- [[Video] Elliptic Curve Cryptography橢圓曲線密碼簡介(鄧安文教授)](https://www.youtube.com/watch?v=3FUyGjH_FZ0&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=3)
- [[Video] Elliptic Curve Cryptography Overview](https://www.youtube.com/watch?v=dCvB-mhkT0w)
- [[Video] Elliptic Curves - Computerphile](https://www.youtube.com/watch?v=NF1pwjL9-DE)

### Homomorphic Eencryption (同態加密)

在加密空間做計算，回傳後再解密可以得到相同的答案

- [同態加密 (Part 1：簡介)](https://blog.amis.com/%E5%90%8C%E6%85%8B%E5%8A%A0%E5%AF%86-part-1-%E7%B0%A1%E4%BB%8B-c46281304fd7)
  - Semantic Security (加密 100 次相同的輸入，會產生 100 種不同的密文)
  - Chosen-Plaintext attacks
- [同態加密 (Part 2：Paillier cryptosystem)](https://blog.amis.com/%E5%90%8C%E6%85%8B%E5%8A%A0%E5%AF%86-part-2-paillier-cryptosystem-bd96af29da0e)
  - Paillier Encryption：Select Random 0 < r < N with gcd(r,N)=1
- [[Video] Introduction to Homomorphic Encryption (by Pascal Paillier)](https://www.youtube.com/watch?v=umqz7kKWxyw)
  - Fully Homomorphic Encryption (FHE)

### Multi Party Computation (MPC)

- [[Video]Basic Concept of MPC](https://www.youtube.com/watch?v=vRVudJADQLk) [Refer to [Slide](https://drive.google.com/file/d/1U5M8b4dePgEgiY4PPeP3DL0LB_kaS34S/view)]
- [[2020Cryptography Meetup] A crash course on Secure Multiparty Computation (MPC)](https://www.youtube.com/watch?v=HOqv5xzrlFI)
  ![active_guaranteed](/img/active_guaranteed.png)
  - Beaver Triples
  - [Shamir Secret Sharing](https://en.wikipedia.org/wiki/Shamir%27s_Secret_Sharing)
    - [[Video] Secret Sharing Explained Virsually](https://www.youtube.com/watch?v=iFY5SyY3IMQ)
    - [A Good Example with code](https://www.geeksforgeeks.org/shamirs-secret-sharing-algorithm-cryptography/)
    - [中文範例 with code](https://medium.com/taipei-ethereum-meetup/%E7%A7%81%E9%91%B0%E5%88%86%E5%89%B2-shamirs-secret-sharing-7a70c8abf664)
    - [An Interactive Emulator](https://iancoleman.io/shamir/)
- [[Video] Introduction to Multiparty Computation (by Yehuda Lindell)](https://www.youtube.com/watch?v=aDL_KScy6hA)
  - Secure Multiparty Computation (e.g. Salary Average)
  - Yao's Garbled Circuits
  - Secret Share Refresh - Proactive Security
  - Private Set Intersection (e.g. Google Ads.)
  ![mpc properties](/img/mpc_properties.png)
- [MPC Alliance](https://www.mpcalliance.org/)
  - [Wiki](https://wiki.mpcalliance.org/)
  - [Learn (Books, Articles, Videos)](https://www.mpcalliance.org/learn)

### Zero Knowledge Proof

<<TODO: add more resource on this topic>>

### Universally Composable (UC) Security Framework

#### Publication

- [[2000 Universally Composable Security: A New Paradigm for Cryptographic Protocols]](https://eprint.iacr.org/2000/067.pdf)
- [[2019] ILC: A Calculus for Composable, Computational Cryptography](https://eprint.iacr.org/2019/402.pdf)
- [[2019] iUC: Flexible Universal Composability Made Simple](https://eprint.iacr.org/2019/1073.pdf)

#### Tutorials

- [[Course] Universally Composable Security: A Tutorial (by Prof. Ran Canetti in 2016)](https://www.youtube.com/playlist?list=PLqc9MPlwib9nSuyH4oUIwPsyDiZ4bwuEE)
  - 
- [[Video] PriSC'20 - Universal Composability is Secure Compilation](https://www.youtube.com/watch?v=rpZTL9fxwfw)
- [[Video] A Framework for Universally Composable Diffie-Hellman Key Exchange](https://www.youtube.com/watch?v=hxNYnaJQsyM)

### Threshold Signatures Scheme (TSS)

- [[Video] MultiParty Computation Introduction to Threshold Signatures in 9 Minutes](https://www.youtube.com/watch?v=4DFfZovCBB0)
- [[Video Threshold Signatures - Discrete Log Based Schemes (Part 1) - Rosario Gennaro]](https://www.youtube.com/watch?v=Tz3-ZBXxraI)
  - Threshold BLS Signature
    - Shamir's classic scheme
    - BLS signature
    - Interpolation in the exponent
  - Threshold Schnorr signature
    - Schnorr's signatures
  - Feldman's VSS (Verifiable Secret Sharing)
  - Distributed Key Generation (DKG)
    - Pedersen's DKG
    - Joint-Pedersen's DKG

## Definition

### EdDSA (愛德華茲曲線數字簽名算法）

- SA，DSA，ECDSA，EdDSA和Ed25519都用於數字簽名，但只有RSA也可以用於加密。[(ref)](https://www.cnblogs.com/librarookie/p/15389876.html)
  - RSA（Rivest–Shamir–Adleman）是最早的公鑰密碼系統之一，被廣泛用於安全數據傳輸。它的安全性取決於整數分解，因此永遠不需要安全的RNG（隨機數生成器）。與DSA相比，RSA的簽名驗證速度更快，但生成速度較慢。
  - DSA（數字簽名算法）是用於數字簽名的聯邦信息處理標準。它的安全性取決於離散的對數問題。與RSA相比，DSA的簽名生成速度更快，但驗證速度較慢。如果使用錯誤的數字生成器，可能會破壞安全性。
  - ECDSA（橢圓曲線數字簽名算法）是DSA（數字簽名算法）的橢圓曲線實現。橢圓曲線密碼術能夠以較小的密鑰提供與RSA相對相同的安全級別。它還具有DSA對不良RNG敏感的缺點。
  - EdDSA（愛德華茲曲線數字簽名算法）是一種使用基於扭曲愛德華茲曲線的Schnorr簽名變體的數字簽名方案。簽名創建在EdDSA中是確定性的，其安全性是基於某些離散對數問題的難處理性，因此它比DSA和ECDSA更安全，後者要求每個簽名都具有高質量的隨機性。
- Ed25519是EdDSA簽名方案，但使用SHA-512 / 256和Curve25519；它是一條安全的橢圓形曲線，比DSA，ECDSA和EdDSA 提供更好的安全性，並且具有更好的性能。
  - spec256r1、spec256k1、ed25519都是簽名算法，而且是具體數字算法的實現。[(ref)](https://blog.csdn.net/feeltouch/article/details/126070640)
  - spec256k1、spec256r1都屬於橢圓曲線數字簽名算法ECDSA(Elliptic Curve Digital Signature Algorithm)簽名的具體實現，只是橢圓曲線函數不同。是由NIST(National Institute of Standards and Technology)這個組織確定的。
  - ed25519屬於EdDSA (Edwards-curve Digital Signature Algorithm) 簽名算法的具體實現，是由ANFS組織推進的ed25519密鑰體系相關進展。

### Paillier Encryption

- [Paillier_cryptosystem](https://en.wikipedia.org/wiki/Paillier_cryptosystem)
  - Choose two large prime numbers `p` and `q` randomly, `gcd(pq,(p-1)(q-1))=1`
  - Compute `n = pq` and $\lambda$`=lcm(p-1,q-1)`
- Encryption
  - Let `m` be a message to be encrypted where `0<= m<n`
  - Select random `r` where `0<r<n`
  - Compute ciphertext as: c = g^m.r^n mod n^2
- Homomorphic properties[[ref]](https://en.wikipedia.org/wiki/Paillier_cryptosystem#Homomorphic_properties)
  - A notable feature of the Paillier cryptosystem is its homomorphic properties along with its non-deterministic encryption (see Electronic voting in Applications for usage). As the encryption function is additively homomorphic, the following identities can be described :
    - Homomorphic addition of plaintexts
    - Homomorphic multiplication of plaintexts

### Decisional Diffie–Hellman (DDH)
- [Lesson 30 The Key Exchange Problem](https://youtu.be/NHCsgISM6BY?t=318)
- [Diffie-Hellman 金鑰交換 讀書筆記](https://medium.com/@asdfg55887/diffie-hellman-key-exchange-protocol-3e04df91b1c)
- [[Course]The Decisional Diffie-Hellman (DDH) problem](https://www.youtube.com/watch?v=RPO53voYY5k&list=PL-qvsLbZq06LvdO6L7byZfcigeQAEo2k6&index=181)
  - [[Video]Diffie Hellman Key Exchange Algorithm | Diffie Hellman key exchange algorithm example and solution](https://www.youtube.com/watch?v=J_EhWSB1wgc)
    - Provide a good example to demo the key exchange process
  - [[Video]Hardness of DDH implies DH key-exchange is Secure](https://www.youtube.com/watch?v=nhp846HDEh8&list=PL-qvsLbZq06LvdO6L7byZfcigeQAEo2k6&index=199)
- [[Paper]The Decision Diffie-Hellman Problem](https://crypto.stanford.edu/~dabo/pubs/papers/DDH.pdf)
- [Cyclic Group(循環群)](https://zh.wikipedia.org/wiki/%E5%BE%AA%E7%92%B0%E7%BE%A4)

### Bitcoin Improvement Proposal (BIP)

- [BIPs](https://github.com/bitcoin/bips)
- [Ethereum Improvement Proposal (EIP)](https://github.com/ethereum/EIPs)
- [[2021 iThome 鐵人賽]DAY 28- BIP32- HD wallet](https://ithelp.ithome.com.tw/articles/10279944)
  - Hierarchical Deterministic Wallets
  - [HD Wallet 技術細節](https://medium.com/@bun919tw/hd-wallet-970096a6d72f)
    - HMAC-SHA256
  - [python-bip32](https://github.com/darosior/python-bip32)

### ERC-20 / ERC721
- [ERC-20 代幣簡介](https://academy.binance.com/zt/articles/an-introduction-to-erc-20-tokens)
  - 在以太坊中，ERC 指的是以太坊評論請求。這些皆為概述以太坊程式化標準的技術文件。請勿與以太坊改進提案 (EIP) 混淆，這就像是比特幣的 BIP，可針對協定本身提出改善方案。另外，ERC 旨在建立可讓應用程式與合約輕鬆互動的慣例。
  - 穩定幣（與法幣掛鉤的代幣）通常會採用 ERC-20 代幣標準。其中一項範例就是稍早引用的 BUSD 合約交易，且大多數主流穩定幣也有提供此格式。
  - 若要遵循 ERC-20，則您的合約必須包含六項強制函數：totalSupply、balanceOf、transfer、transferFrom、approve 及 allowance。此外，您還可以指定 name、symbol 及 decimal 等可選函數。
- [以太坊系列標準介紹(ERC20/ERC721)](https://medium.com/@starbit.writer/%E4%BB%A5%E5%A4%AA%E5%9D%8A%E7%B3%BB%E5%88%97%E6%A8%99%E6%BA%96%E4%BB%8B%E7%B4%B9-erc20-erc721-4a5a83009d00)
  - ERC（Ethereum Request for Comment）並非一項技術或是程式，而是以太坊通用徵求意見協議（RFC）。
  - ERC為開發者提供了建設技術指導。而開發者可以通過提交EIP（Ethereum Improvement Proposal），向以太坊社區提交新的ERC標準提案。
  - 提交內容包括協議規範和合約標準。一旦該EIP獲得以太坊委員會的批准並最終定型，它就會成為一個新的ERC。
  
### Unspent Transaction Output (UTXO)

- [從比特幣上的一筆交易來看 UTXO 架構 【Day 4】](https://ithelp.ithome.com.tw/articles/10217556)
  - [e.g. An example from Blockstream Explorer](https://blockstream.info/block/0000000000000000000779afcfa50c15cad7916880c2c698a61dfaf4ba0ae33f)
  - [The Ethereum Blockchain Explorer](https://etherscan.io/)
- [什麼是UTXO?](https://medium.com/%E4%B8%80%E5%80%8B%E5%AE%B9%E6%98%93%E5%81%A5%E5%BF%98%E7%9A%84%E5%A4%A7%E5%AD%B8%E7%94%9F/%E4%BB%80%E9%BA%BC%E6%98%AFutxo-40b62e73c84d)
  - UTXO (Bitcoin 採用）與 帳戶餘額模型(Account；Ethereum 採用) 優劣比較：
    - UTXO 可簽發多筆交易，並廣播到區塊鏈網路
    - 帳戶餘額模型易理解且容易編寫程式；而UTXO要考慮到輸入與輸出之間的關係，在程式上比較難編寫
    - 帳戶餘額模型的每一筆交易都只需要一個簽名，而輸入與輸出都是地址，能節省儲存空間。
    - UTXO只要驗證當前的交易是符合輸出與輸入規則，不用去追朔先前交易；而帳戶餘額模型只要金額有問題必須追朔先前交易的金流動向。
    - Account模型需要有更多的機制去保護資金；而UTXO對於雙花攻擊(Double Spending)與重放攻擊(Replay Attack)有先天的保護

### [Public Key Cryptography Standards (PKCS)](https://en.wikipedia.org/wiki/PKCS)

- These are a group of public-key cryptography standards devised and published by RSA Security LLC, starting in the early 1990s. 
- The company published the standards to promote the use of the cryptography techniques to which they had patents, such as the RSA algorithm, the Schnorr signature algorithm and several others.
  - PKCS#1 : RSA Cryptography Standard
  - PKCS#3 : [Diffie-Hellman Key Agreement Standard(D-H)](https://zh.wikipedia.org/wiki/%E8%BF%AA%E8%8F%B2-%E8%B5%AB%E7%88%BE%E6%9B%BC%E5%AF%86%E9%91%B0%E4%BA%A4%E6%8F%9B)
    - Diffie–Hellman–Merkle key exchange

### [Elliptic Curve Diffie–Hellman key exchange (ECDH）](https://zh.wikipedia.org/wiki/%E6%A9%A2%E5%9C%93%E6%9B%B2%E7%B7%9A%E8%BF%AA%E8%8F%B2-%E8%B5%AB%E7%88%BE%E6%9B%BC%E9%87%91%E9%91%B0%E4%BA%A4%E6%8F%9B)
- 橢圓曲線迪菲-赫爾曼密鑰交換，是一種匿名的密鑰合意協議（Key-agreement protocol），這是迪菲－赫爾曼密鑰交換的變種，採用橢圓曲線密碼學來加強性能與安全性。
- 在這個協定下，雙方利用由橢圓曲線密碼學建立的公鑰與私鑰對，在一個不安全的通道中，建立起安全的共有加密資料。
- 臨時ECDH（ECDH Ephemeral，ECDHE）能夠提供前向安全性。

### [Forward Secrecy(FS) or Perfect Forward Secrecy (PFS)](https://zh.wikipedia.org/wiki/%E5%89%8D%E5%90%91%E4%BF%9D%E5%AF%86)
- 前向保密（Forward Secrecy）有時也被稱為完全前向保密（Perfect Forward Secrecy，是密碼學中通訊協定的一種安全特性，指的是長期使用的主金鑰泄漏不會導致過去的對談金鑰泄漏。
- 前向保密能夠保護過去進行的通訊不受密碼或金鑰在未來暴露的威脅。
- 如果系統具有前向保密性，就可以保證在私鑰泄露時歷史通訊的安全，即使系統遭到主動攻擊也是如此。

## Questions

### Q1: Why ECDSA is better than RSA?

![ECC vs. RSA](/img/ecc_rsa.png)
Ref: [NIST](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)

![addition](/img/ecc_addition.png)
![addition1](/img/ecc_addition1.png)
Ref: [[Video] Elliptic Curve Cryptography橢圓曲線密碼簡介(鄧安文教授)](https://www.youtube.com/watch?v=3FUyGjH_FZ0&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=3)

### Q2: How is Bitcoin Public key converted to address?

![address](/img/bitcoin_address.png)
![address1](/img/bitcoin_address1.png)

*refer to [video](https://www.youtube.com/watch?v=FshMisRD2Uo&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=86)

---

## Services

- [The Bitcoin Blockstream Explorer](https://blockstream.info)
- [The Ethereum Blockchain Explorer](https://etherscan.io/)
- [Bitcoint Improvement Proposal (BIP)](https://github.com/bitcoin/bips)
- [Ethereum Improvement Proposal (EIP)](https://github.com/ethereum/EIPs)

---

## Reference

- [MPC Alliance](https://www.mpcalliance.org/)
- [CoinMarketCap](https://coinmarketcap.com/)
- [智富區塊 Smart Rich](https://smartrichs.com/)
- [區塊客](https://blockcast.it/)
- [幣學](https://glossary.bshare.io/)
- [BitNodes](https://bitnodes.io/)
  - [Live-Map](https://bitnodes.io/nodes/live-map/)
- 