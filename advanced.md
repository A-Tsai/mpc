# Advanced Concept of Cryptography

## Topics

### Elliptic Curve Cryptography (ECC)

- [[Video] Elliptic Curve Cryptography橢圓曲線密碼簡介(鄧安文教授)](https://www.youtube.com/watch?v=3FUyGjH_FZ0&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=3)
- [[Video] Elliptic Curve Cryptography Overview](https://www.youtube.com/watch?v=dCvB-mhkT0w)
- [[Video] Elliptic Curves - Computerphile](https://www.youtube.com/watch?v=NF1pwjL9-DE)
- [Elliptic Curve Cryptography: finite fields and discrete logarithms](https://andrea.corbellini.name/2015/05/23/elliptic-curve-cryptography-finite-fields-and-discrete-logarithms/)

### Homomorphic Encryption (同態加密)

在加密空間做計算，回傳後再解密可以得到相同的答案

- [同態加密 (Part 1：簡介)](https://blog.amis.com/%E5%90%8C%E6%85%8B%E5%8A%A0%E5%AF%86-part-1-%E7%B0%A1%E4%BB%8B-c46281304fd7)
  - Semantic Security (加密 100 次相同的輸入，會產生 100 種不同的密文)
  - Chosen-Plaintext attacks
- [同態加密 (Part 2：Paillier cryptosystem)](https://blog.amis.com/%E5%90%8C%E6%85%8B%E5%8A%A0%E5%AF%86-part-2-paillier-cryptosystem-bd96af29da0e)
  - Paillier Encryption：Select Random 0 < r < N with gcd(r,N)=1
- [[Video] Introduction to Homomorphic Encryption (by Pascal Paillier)](https://www.youtube.com/watch?v=umqz7kKWxyw)
  - Fully Homomorphic Encryption (FHE)
- [[Video] Intro to HE from Microsoft Research](https://www.youtube.com/watch?v=SEBdYXxijSo&list=RDLVSEBdYXxijSo&start_radio=1&rv=SEBdYXxijSo&t=72)
  - CKKS - Approximated HE
- [[Video] More topics on HE from FHE.org meetup](https://www.youtube.com/playlist?list=PLnbmMskCVh1chnSM8Jjy6Nk3IH6fpn7MM)

### Zero Knowledge Proofs (ZKPs)

- [ZKDocs](https://www.zkdocs.com/)
  - [Notation(慣用數學符號的定義)](https://www.zkdocs.com/docs/zkdocs/notation/)
  - ZK Protocols
    - Schnorr's Identification protocol
    - Girault's Identification protocol
- [CO6GC: Introduction to Zero-Knowledge Proofs](https://www.esat.kuleuven.be/cosic/blog/co6gc-introduction-to-zero-knowledge-proofs-1/)
  - Completeness
  - Soundness
  - Special-Soundness (or Knowledge-Soundness)
- 中文說明
  - [Day15|密碼學初探(8)：零知識證明](https://ithelp.ithome.com.tw/articles/10215110)
  - [a16z：零知識證明的進步映射去中心化的速度](https://zombit.info/a16z-advances-in-zero-knowledge-proofs/)
- [[Course] The 9th BIU Winter School on Cryptography - Zero Knowledge](https://www.youtube.com/playlist?list=PL8Vt-7cSFnw29cLUVqAIuMlg1QJ-szV0K)
  - [[Video] Intro to Zero Knowledge](https://www.youtube.com/watch?v=6uGimDYZPMw)
    - Completeness, Soundness, Efficiency
  - [[Video] Sigma Protocols (part1) - Benny Pinkas](https://www.youtube.com/watch?v=XT1Pad0DM24&list=PL8Vt-7cSFnw29cLUVqAIuMlg1QJ-szV0K&index=11)
- [(Wiki)Proof of knowledge](https://en.wikipedia.org/wiki/Proof_of_knowledge)
  - Schnorr's protocol
  - Sigma ($\Sigma$-) protocol
    - three-move structure(commitment, challenge, and response)
- Range Proof
  - Bulletproofs 基本說明 [I](https://www.8btc.com/article/530155), [II](https://www.8btc.com/media/532874), [III](https://zhuanlan.zhihu.com/p/97676457)
    - https://github.com/dalek-cryptography/bulletproofs
    - [(paper) 2017 Bulletproofs: Short Proofs for Confidential Transactions and More](https://web.stanford.edu/~buenz/pubs/bulletproofs.pdf)

### [Verifiable Secret Sharing (VSS)](https://en.wikipedia.org/wiki/Verifiable_secret_sharing)

- [Shamir Secret Sharing assumes all parties are honest, so it will be broken easily by any malicious party. That's why we need VSS.](https://zhuanlan.zhihu.com/p/149071853)
  - ZKP (interactive) : ???
  - PKI + HE (uninteractive) : Feldman's VSS
- [(Video) Concept of Commitment Schemes](https://www.youtube.com/watch?v=4w_b8Msxy14)
  - Commitment Phase (c) + Reveal Phase (m, d)
  - Perfect binding and perfect hiding can't be existed together.
  - e.g. Pederson Commitment
    - Computationally binding + perfectly hiding
  
- Feldman's VSS
  - based on Shamir's secret sharing scheme combined with any homomorphic encryption scheme.
  - [(Video)Threshold Secret Sharing part 2- Verifiable Secret Sharing - Gilad Asharov](https://youtu.be/Qm4EgaNDLK4?t=1781)
  - [可以扺抗 (n-1)/2 malicious parties](https://zhuanlan.zhihu.com/p/149071853)
  - [A tour of Verifiable Secret Sharing schemes and Distributed Key Generation protocols.](https://medium.com/nethermind-eth/a-tour-of-verifiable-secret-sharing-schemes-and-distributed-key-generation-protocols-3c814e0d47e1)
  - [(GitHub: Rust Code) VSS from bitrocks](https://github.com/bitrocks/verifiable-secret-sharing)
- [Pedersen Verfifiable Secret Sharing](https://medium.com/asecuritysite-when-bob-met-alice/pedersen-verifiable-secret-shares-pvss-commitments-and-spotting-a-bad-dealer-a54364d24d6f)
  
### Universally Composable (UC) Security Framework

#### Publication

- [[2000 Universally Composable Security: A New Paradigm for Cryptographic Protocols]](https://eprint.iacr.org/2000/067.pdf)
- [[2019] ILC: A Calculus for Composable, Computational Cryptography](https://eprint.iacr.org/2019/402.pdf)
- [[2019] iUC: Flexible Universal Composability Made Simple](https://eprint.iacr.org/2019/1073.pdf)

#### Tutorials

- [[Course] Universally Composable Security: A Tutorial (by Prof. Ran Canetti in 2016)](https://www.youtube.com/playlist?list=PLqc9MPlwib9nSuyH4oUIwPsyDiZ4bwuEE)
- [[Video] PriSC'20 - Universal Composability is Secure Compilation](https://www.youtube.com/watch?v=rpZTL9fxwfw)
- [[Video] A Framework for Universally Composable Diffie-Hellman Key Exchange](https://www.youtube.com/watch?v=hxNYnaJQsyM)
  - Provide the basic concept of UC
  
### Multi-Signature (MultiSeq)

- [什麼是多重簽名錢包？](https://academy.binance.com/zt/articles/what-is-a-multisig-wallet)
- [MultiSig vs. ThresholdSig](https://sepior.com/blog/2019/4/4/are-threshold-signatures-really-more-secure-thannbspmultisignbsp)
  - Since Bitcoin uses fixed length blocks, MultiSig transactions limit the number of transactions per block, so miners charge higher fees and perhaps more importantly may deprioritize processing MultiSig transactions during peak traffic periods.
- [(Video)Introduction to Threshold Signatures in 9 Minutes](https://www.youtube.com/watch?v=4DFfZovCBB0)
![multisig_thresholdsig](/img/multisig_thresholdsig.png)

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

### Theshold Schnorr Signature

- [Schnorr signature](https://www.youtube.com/watch?v=r9hJiDrtukI)
  - Fiat-Shamir Transform： the hash function

### InterPlanetary File System (IPFS)

- [[Paper]IPFS - Content Addressed, Versioned, P2P File System](https://arxiv.org/abs/1407.3561)
- [[Video]李查说IPFS：彻底搞懂 IPFS 白皮书](https://www.youtube.com/watch?v=cIJVg19RSsQ)

## Comparison

### Signature Scheme

- [區塊鏈替代簽名方案優劣勢對比，Schnorr簽名最適合比特幣](https://www.8btc.com/article/359451)
  - SSS
  - Threshold ECDSA
  - Threshold EdDSA
  - Schnorr Signature Scheme
  - BLS Signature Scheme
    - 可以節省存儲空間和傳輸帶寬，因為多個簽名和密鑰可以合併成一個。
    - 可以提高系統的安全性，因為聚合簽名和聚合密鑰的驗證不依賴於單個簽名者或密鑰持有者。
    - 可以實現多重交易和閾值簽名，方便使用者管理自己的資產。

![Comparison on Signature Scheme](/img/signature_scheme_comparison.png)
