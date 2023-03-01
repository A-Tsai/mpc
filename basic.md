# Basic Concept of Cryptography

## Definition

### **Characteristics of Cryptography**

- 機密性（Confidentiality）：確保資料只會給對方看到
- 完整性（Integrity）：確保資料的完整性
- 身份驗證（Authentication）：傳送和接收都需要驗證
- 不可否認性（Non-Reputation）：提供雙方互動的證明

### **柯克霍夫原則 (Kerckhoffs’ principle)**

- 古典密碼學和現代密碼學最大的區別就是在有柯克霍夫原則後才開始有了變化，柯克霍夫原則（Kerckhoffs’ principle），大致上就是在強調即使密碼系統的任何細節被人知道了，只要密鑰（key）未洩漏，它也是安全的。換句話說，加密技術就算演算法被知道了，資料也不會有危險。

### DSA (Digital Signature Algorithm)

- [RSA/DSA/ESIGN的基本觀念介紹](http://security.nknu.edu.tw/textbook/chap5.pdf)
![dsa_keygen](/img/dsa_keygen.png)
- [簡單公式](https://dreamisadream97.pixnet.net/blog/post/282813180-dsa-%28digital-signature-algorithm%29)
![dsa](/img/dsa.png)
  - [重要定理：Fermat's Little Theorem](https://www.youtube.com/watch?v=3Cb0ys-jppU&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=42)
- Tutorials
  - [[Video]Digital Signature Algorithm (DSA) - Cryptography - Practical TLS](https://www.youtube.com/watch?v=iS1nK4G6EtA)
  - [[Video]RSA and DSA Encryption Algorithms Explained（Simplilearn](https://www.youtube.com/watch?v=bO4lEQfPn60)

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

### Homomorphic Encryption

-[[Video]What is Homomorphic Encryption Explained | Paillier Cryptosystem | PHE | SHE | FHE](https://www.youtube.com/watch?v=7IUS-ixypos)
  -Partially Homomorphic Encryption (PHE)
    - only ADDITION or only MULTIPLICATION, but an infinite number of time
  -Somewtat Homomorphic Encryption (SHE)
    - both ADDITION & MULTIPLICATION, but for a limited number of times
  -Fully Homomorphic Encryption (FHE)
    - both ADDITION & MULTIPLICATION & an infinite number of times
  
### Paillier Encryption (is a kind of PHE)

- [Paillier_cryptosystem](https://en.wikipedia.org/wiki/Paillier_cryptosystem)
  - Choose two large prime numbers `p` and `q` randomly, `gcd(pq,(p-1)(q-1))=1`
  - Compute `n = pq` and $\lambda$`=lcm(p-1,q-1)`
- Encryption
  - Let `m` be a message to be encrypted where `0<=m<n`
  - Select random `r` where `0<r<n`
  - Compute ciphertext as: c = g^m.r^n mod n^2
- Homomorphic properties[[ref]](https://en.wikipedia.org/wiki/Paillier_cryptosystem#Homomorphic_properties)
  - A notable feature of the Paillier cryptosystem is its homomorphic properties along with its non-deterministic encryption (see Electronic voting in Applications for usage). As the encryption function is additively homomorphic, the following identities can be described :
    - Homomorphic addition of plaintexts
    - Homomorphic multiplication of plaintexts
- [[Video]Implementation of Homomorphic Encryption: Paillier](https://www.youtube.com/watch?v=xHjhQZdP2aU)
  - Tutorial and implementation by Python
- [[Video]Paillier's cryptosystem - Addtive homomorphic encryption](https://www.youtube.com/watch?v=bhebAMgRZMs)
  - Tutorial and details

### Decisional Diffie–Hellman (DDH)

- [Diffie-Hellman 金鑰交換 讀書筆記](https://medium.com/@asdfg55887/diffie-hellman-key-exchange-protocol-3e04df91b1c)
  - [Lesson 30 The Key Exchange Problem](https://youtu.be/NHCsgISM6BY?t=318)
  - [[Video]Diffie Hellman Key Exchange Algorithm | Diffie Hellman key exchange algorithm example and solution](https://www.youtube.com/watch?v=J_EhWSB1wgc)
    - Provide a good example to demo the key exchange process
  - [[Video]DHKE : Demo with mixing colors - part 1/2](https://www.youtube.com/watch?v=4svwEYsO77U&list=PLSNNzog5eydtwsdT__t5WtRgvpfMzpTc7)
    - Provide good examples(color and math) to describe DHKE
  - [Man in the middle attack in Diffie Hellman Key Exchange](https://www.youtube.com/watch?v=ev2Cbu23m-Q)
- [[Course]The Decisional Diffie-Hellman (DDH) problem](https://www.youtube.com/watch?v=RPO53voYY5k&list=PL-qvsLbZq06LvdO6L7byZfcigeQAEo2k6&index=181)
  - [[Video]Hardness of DDH implies DH key-exchange is Secure](https://www.youtube.com/watch?v=nhp846HDEh8&list=PL-qvsLbZq06LvdO6L7byZfcigeQAEo2k6&index=199)
- [[Paper]The Decision Diffie-Hellman Problem](https://crypto.stanford.edu/~dabo/pubs/papers/DDH.pdf)
- [Cyclic Group(循環群)](https://zh.wikipedia.org/wiki/%E5%BE%AA%E7%92%B0%E7%BE%A4)

### [Shamir’s Secret Sharing (SSS)](https://medium.com/taipei-ethereum-meetup/%E7%A7%81%E9%91%B0%E5%88%86%E5%89%B2-shamirs-secret-sharing-7a70c8abf664)

- [Wiki](https://en.wikipedia.org/wiki/Shamir%27s_Secret_Sharing)
- [Golang implmentation](https://github.com/corvus-ch/shamir)
- [Ruby Example](https://kimh.github.io/blog/en/security/protect-your-secret-key-with-shamirs-secret-sharing/)
- [ZeroPass](https://zeropass.io/)
  - [ZeroPass Whitepaper](https://zeropass.gitbook.io/whitepaper/)

### Schnorr Digital Signature

-[wiki](https://cryptography.fandom.com/wiki/Schnorr_signature)
-[[Video]Schnorr Digital Signature](https://www.youtube.com/watch?v=mV9hXEFUB6A)

### Strong RSA Assumption

- [[Video Tutorial]RSA Signatures](https://www.youtube.com/watch?v=rz78hRliZDA)
  
### Semantic Security

對於相同的明文稱作 x，則今天用同態加密方法 En去加密他，也就是得到 En(x)。對同樣的 x 和相同的 En計算 En(x) 100 次，你會發現這一百次出來的結果都不一樣。但是呢，你將這一百個值做解密，會發現給出的答案都是 10。( for 同態加密(homomorphic encryption))

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

## Tutorial

- [[2021 iThome 鐵人賽]學密碼學也猜不到你的手機密碼](https://ithelp.ithome.com.tw/users/20140112/ironman/3930)
  - RC4, DES, AES and RSA
  - [ECC (Elliptic Curve Cryptography;橢圓曲線密碼學)](https://ithelp.ithome.com.tw/articles/10268495)
    - [Day 24. 非對稱式加密演算法 - 橢圓曲線密碼學 Elliptic Curve Cryptography , ECC (觀念篇)](https://ithelp.ithome.com.tw/articles/10251031)
  - [DHKE、ECDH、ElGamal](https://ithelp.ithome.com.tw/articles/10271893)
    - [[Sunny Classroom]Intro to the ElGamal Cryptosystem](https://www.youtube.com/watch?v=oQqr8d5s3Uk)
  - [ECDSA](https://ithelp.ithome.com.tw/articles/10275773)
  - [地址 Address](https://ithelp.ithome.com.tw/articles/10279688)

- [[Video] NCSSM's Cryptography Course](https://www.youtube.com/playlist?list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro)
  - Ciphers
    - Transposition Ciphers: Reverse, Rail Fence, Route
    - Substitution Ciphers: Atbash, Caesar, multiplicative, Tabula Recta, Trithemius,  Vigenere, Autokey, <del>Affine, Hill, Playfair</del>
  - [Index of Coincidence](https://www.youtube.com/watch?v=kty-dCB4AAk&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=22)
  - [Kasiski Test](https://www.youtube.com/watch?v=asRbswE2hFY&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=23)
  - [Linear Feedback Shift Register (LFSR)](https://www.youtube.com/watch?v=Y0DlCM4iKeA&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=29)
  - [Diffie-Hellman Key Exchange Problem](https://youtu.be/NHCsgISM6BY?t=318)
  - [The Extended Euclidean Algorithm (EEA)](https://www.youtube.com/watch?v=WKSlsFTH8hs&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=33)
  - [Euler's Totient Function $\Phi(n)$](https://www.youtube.com/watch?v=CTbdowq0ZB8&list=PLE6ty64ouo1MYLUgQxDJ6Ruic_ghtUsro&index=34)
    - if `p` is prime, then: $\Phi(p) = p -1$.
    - if `p` and `q` are both primes, and `n = pq`, then: $\Phi(n)=\Phi(pq)=\Phi(p)*\Phi(q)=(p-1)(q-1)$

- [(Course)Cryptography & Network Security by Neso Academy](https://www.youtube.com/playlist?list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII)
  - [CIA trial for Computer Security](https://www.youtube.com/watch?v=gx0vlRpdFnc&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=2)
    - Confidientiality, Integrity, Availability
    - Authenticity, Accountability
  - [OSI Security Architecture](https://www.youtube.com/watch?v=UG26SS9pjwE&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=3)
    - Security Attack:
      - passive attack
      - active attack
        - Masquerade (假裝是 Bob 送訊息給 Alice)
        - Replay
        - Modification of message
        - Denial of Service (DoS)
    - Security Mechanism
    - Security Service
      - nonrepudiation
  - Cryptography
    - Encryption schemes
      - Unconditionally secure
      - Computationally secure
    - Classical Encryption Techniques
      - Substitution
        - Caesar, Monoalphabetic, Playfair, Hill, Polyalphabetic(Vigenere, Vernam), One-Time Pad (Perfect Secrecy)
      - Transposition
        - Rail Fence, Row Column Transposition
    - [Steganography](https://www.youtube.com/watch?v=Te8Cao2Smsk&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=26)
    - [Euler's Totient Function](https://www.youtube.com/watch?v=osge0_lZTaY&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=39)
      - [解法說明](https://www.youtube.com/watch?v=osge0_lZTaY&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=39)
![addition](/img/euler.png)  
    - [Fermat's Little Theorem](https://www.youtube.com/watch?v=3Cb0ys-jppU&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=40)
    - [Euler's Theorem](https://www.youtube.com/watch?v=DyOv20d4c70&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=41)
    - [Primitive root](https://www.youtube.com/watch?v=DKy98FWHwdg&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=42)
    - [Multiplicative Inverse](https://www.youtube.com/watch?v=YwaQ4m1eHQo&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=43)
    - [Extended Euclidean Algorithm](https://www.youtube.com/watch?v=lq285DDdmtw&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=44)
    - [Fermat's Factoring Algorithm](https://www.youtube.com/watch?v=tKTNVmnW_4w&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=51)
    - [Fermat's Primality Test](https://www.youtube.com/watch?v=sDrXeCs3ghQ&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=52)
      - Miller-Rabin Primality Test
    - [Abelian Group](https://www.youtube.com/watch?v=8TjYHK804mU&list=PLBlnK6fEyqRgJU3EsOYDTW7m6SUmW6kII&index=54)
    - **TODO: subcribe the channel for chapter 3/4**

- [[Explore the Cryptography World]](https://www.youtube.com/playlist?list=PL-qvsLbZq06LvdO6L7byZfcigeQAEo2k6)

- [[Sunny Classroom]Advanced Cryptography](https://www.youtube.com/playlist?list=PLSNNzog5eydtwsdT__t5WtRgvpfMzpTc7)
  - DHKE, PKI, RSA, [ELGamal](https://www.youtube.com/watch?v=oQqr8d5s3Uk&list=PLSNNzog5eydtwsdT__t5WtRgvpfMzpTc7&index=12)
  
- [[Video]RSA 歷史原由與設計說明](https://www.youtube.com/watch?v=wXB-V_Keiu8)

- [[華人開放式課程 MOOC]区块链中的密码学](https://www.youtube.com/watch?v=uGenWpoFDG0&list=PLv8hyYaXsdish--YdAtaFXnDDsYMBQJXz)

- [Day 21. 加密演算法要注意的那些毛 (一) - 加密模式](https://ithelp.ithome.com.tw/articles/10249953)
  - ECB, CBC[區塊鏈(blockchain)的鼻祖], CFB, OFB, CTR
  - [AES, Advanced Encryption Standard，其實是一套標準：FIPS 197，而我們所說的AES演算法 就是Rijndael演算法](https://ithelp.ithome.com.tw/articles/10249488)
  - [RSA 流程推導與實例說明](RSA 簡介)

---

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

- refer to [video](https://www.youtube.com/watch?v=FshMisRD2Uo&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=86)
- Bitcoin 採用 [Secp256k1](https://en.bitcoin.it/wiki/Secp256k1)

---

## Resource

- Cryptography suite
  - [A Security Suite](https://asecuritysite.com/)
  