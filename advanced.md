# Advanced Concept of Cryptography

## Topics

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

### Zero Knowledge Proofs (ZKPs)

- 中文說明
  - [Day15|密碼學初探(8)：零知識證明](https://ithelp.ithome.com.tw/articles/10215110)
  - [a16z：零知識證明的進步映射去中心化的速度](https://zombit.info/a16z-advances-in-zero-knowledge-proofs/)

### [Verifiable Secret Sharing (VSS)](https://en.wikipedia.org/wiki/Verifiable_secret_sharing)

- Feldman's VSS
  - based on Shamir's secret sharing scheme combined with any homomorphic encryption scheme. 
  - [A tour of Verifiable Secret Sharing schemes and Distributed Key Generation protocols.](https://medium.com/nethermind-eth/a-tour-of-verifiable-secret-sharing-schemes-and-distributed-key-generation-protocols-3c814e0d47e1)
  
### Universally Composable (UC) Security Framework

#### Publication

- [[2000 Universally Composable Security: A New Paradigm for Cryptographic Protocols]](https://eprint.iacr.org/2000/067.pdf)
- [[2019] ILC: A Calculus for Composable, Computational Cryptography](https://eprint.iacr.org/2019/402.pdf)
- [[2019] iUC: Flexible Universal Composability Made Simple](https://eprint.iacr.org/2019/1073.pdf)

#### Tutorials

- [[Course] Universally Composable Security: A Tutorial (by Prof. Ran Canetti in 2016)](https://www.youtube.com/playlist?list=PLqc9MPlwib9nSuyH4oUIwPsyDiZ4bwuEE)
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

### InterPlanetary File System (IPFS)

- [[Paper]IPFS - Content Addressed, Versioned, P2P File System](https://arxiv.org/abs/1407.3561)
- [[Video]李查说IPFS：彻底搞懂 IPFS 白皮书](https://www.youtube.com/watch?v=cIJVg19RSsQ)
