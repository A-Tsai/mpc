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
  - Preliminaries
    - Proactive Key Refresh
    - Universally Composable (UC) Security Framework
      - [[2000 Universally Composable Security: A New Paradigm for Cryptographic Protocols]](https://eprint.iacr.org/2000/067.pdf)
    - Paillier Encryption
    - Pedersen Commitments

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
  
## Tutorial

### Basic Concept

- [[2021 iThome 鐵人賽]學密碼學也猜不到你的手機密碼](https://ithelp.ithome.com.tw/users/20140112/ironman/3930)

### Elliptic Curve Cryptography (ECC)

- [[Video] Elliptic Curve Cryptography橢圓曲線密碼簡介](https://www.youtube.com/watch?v=3FUyGjH_FZ0&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=3)
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

## Questions

### Q1: Why ECDSA is better than RSA?

![ECC vs. RSA](/img/ecc_rsa.png)
Ref: [NIST](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)

![addition](/img/ecc_addition.png)
![addition1](/img/ecc_addition1.png)

### Q2: How is Bitcoin Public key converted to address?

![address](/img/bitcoin_address.png)
![address1](/img/bitcoin_address1.png)

*refer to [video](https://www.youtube.com/watch?v=FshMisRD2Uo&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=86)

## Reference
