# Multiparty Threshold ECDSA

## Publications

### GG-series

- [GG18] Fast Multiparty Threshold ECDSA with Fast Trustless Setup
  - [Paper](https://eprint.iacr.org/2019/114.pdf)
    - Revised
      - ZK range proofs
        - [2021 - Alpha-Rays: Key Extraction Attacks on Threshold ECDSA Implementations](https://eprint.iacr.org/2021/1621.pdf)
  - [Source code from Binance](https://github.com/bnb-chain/tss-lib)]
  - [[Video]ACM CSS 2018](https://www.youtube.com/watch?v=PdfDZIwuZm0)
  
- [GG20] One Round Threshold ECDSA with Identifiable Abort
  - [Paper](https://eprint.iacr.org/2020/540.pdf)
  - [Source code from Coinbase](https://github.com/coinbase/kryptology)]

- [GG21] UC Non-Interactive, Proactive, Threshold ECDSA with Identifiable Aborts
  - [Paper](https://eprint.iacr.org/2021/060.pdf)

  ![Performance Comparison](/img/gg21_fig1.png)

  - [Source code]
    - [[Rust] Webb - CGGMP Threshold ECDSA Distributed Key Generation Protocol](https://github.com/webb-tools/cggmp-threshold-ecdsa)
      - Implementing all ZKPs for 4-round (O(n^2)) identifiable abort
  - [[Video] Short Concept Introduction](https://dl.acm.org/doi/10.1145/3372297.3423367#)
  - [Introduction from Fireblocks](https://www.fireblocks.com/blog/ccs-threshold-ecdsa/)
    - [[Short Video]Introduction on the main concept of GG21](https://www.youtube.com/watch?v=tNptKxswmvg)
  
  [![Technical Overview from Fireblocks(Must Read)](https://img.youtube.com/vi/zXCSPWxWA-s/sddefault.jpg)](https://www.youtube.com/watch?v=zXCSPWxWA-s)
  *Technical Overview (Must Read)*
  
  - Preliminaries
    - Proactive Key Refresh
    - Universally Composable (UC) Security Framework
    - leveraging [Paillier Encryption (from wikipedia)](https://en.wikipedia.org/wiki/Paillier_cryptosystem) as a commitment scheme
    - Pedersen Commitments
    - DDH

### Techical Note

- [(Medium)On UC Non-interactive, Proactive, Threshold ECDSA](https://medium.com/iovlabs-innovation-stories/on-uc-non-interactive-proactive-threshold-ecdsa-fda5916edc50)
 ![Rounds Comparison](/img/ts-comparison.png)
- [(Coinbase)Threshold Digital Signatures](https://www.coinbase.com/blog/threshold-digital-signatures)
  - Deeper dive into threshold signatures
  
### Other Publications

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

---

## Resources

- [[Github] Multi-party ECDSA](https://github.com/ZenGo-X/multi-party-ecdsa)
  - including GG20
  - implemented by Rust
  - [[Github] TSS ECDSA CLI utility](https://github.com/cryptochill/tss-ecdsa-cli)
- [[Github] Multiparty threshold ECDSA scheme](https://github.com/ing-bank/threshold-signatures)
  - based on GG18
  - implmeneted by Rust
  
---

## Supplementaries

- [Basic Concept of Cryptography](basic.md)
- [Advanced Concept of Cryptograph](advanced.md)

### Multi Party Computation (MPC)
- [[Video]Multiparty Computation](https://www.youtube.com/watch?v=_kLET4k2xBQ)
  - the best explanation video
- [[Video]Basic Concept of MPC](https://www.youtube.com/watch?v=vRVudJADQLk) [Refer to [Slide](https://drive.google.com/file/d/1U5M8b4dePgEgiY4PPeP3DL0LB_kaS34S/view)]
- [[2020Cryptography Meetup] A crash course on Secure Multiparty Computation (MPC)](https://www.youtube.com/watch?v=HOqv5xzrlFI)
  - Privacy Guarantees:
    - Computational Security
    - Statistical Security
    - Perfect Security
  - Output Guarantees:
    - Guaranteed Output Delivery (G.O.D.)
    - Fairness
    - Security with Abort
  ![active_guaranteed](/img/active_guaranteed.png)
  - Beaver Triples (a.k.a Multiplication Triples)
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
- [(Sepior)MPC Digital Asset Wallet Considerations - Build vs. Buy](https://www.youtube.com/watch?v=y9nvtJlZvI8)
  - How to evaluate your wallet options?
- [(Unbound Security)Cryptocurrency Protection with MPC & Threshold ECDSA](https://www.youtube.com/watch?v=AAW5C0cXLIU)
- [2013 Multi-Party Computation: From Theory to Practice(Nigel P. Smark at Google in 2013)](https://www.youtube.com/watch?v=LRAN_w1_qmw)
  - Fully Homomophic Encryption (FHE) + Multi-Party Computation (MPC)
    - In FHE one has a huge computational cost, but zero communication.
    - In MPC one has virtually no computational cost, but huge communication.
  - assume Linear Secrete Sharing is free
  - SPDZ protocol vs. NNOS protocol
  - [more details At Microsoft Research in 2016](https://www.youtube.com/watch?v=pNNLAEygPQI)
    - ##TODO##
- [2020 Threshold Secret Sharing - Gilad Asharov](https://www.youtube.com/watch?v=5tDp_-Nf7nU)
  - Error Correction
    - Reed Solomon
    - Berlekamp-Welch Algorithm

---

## Services

- [Sepior - Advanced MPC Digital Asset Wallet & Custody Infrastructure](https://sepior.com/)
- [Fireblocks - an easy to use platform to create new blockchain based products and manage day-to-day digital asset opterations](https://www.fireblocks.com/blog/ccs-threshold-ecdsa/)

---

## Reference

- [MPC Alliance](https://www.mpcalliance.org/)
- [Key Length Comparison](https://www.keylength.com/en/compare/)
  - Provide a mapping table for many standards, e.g. NIST, BSI.
