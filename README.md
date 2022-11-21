# Multiparty Threshold ECDSA

## Publications

- GG18 [[paper](https://eprint.iacr.org/2019/114.pdf), [code from Binance](https://github.com/bnb-chain/tss-lib)]
- GG20 [[paper](https://eprint.iacr.org/2020/540.pdf), [code from Coinbase](https://github.com/coinbase/kryptology)]
- GG21 [[paper](https://eprint.iacr.org/2021/060.pdf), code]

## Tutorial

### Basic Concept

- [[2021 iThome 鐵人賽]學密碼學也猜不到你的手機密碼](https://ithelp.ithome.com.tw/users/20140112/ironman/3930)

### Elliptic Curve Cryptography (ECC)

- [[Video] Elliptic Curve Cryptography橢圓曲線密碼簡介](https://www.youtube.com/watch?v=3FUyGjH_FZ0&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=3)
- [[Video] Elliptic Curve Cryptography Overview](https://www.youtube.com/watch?v=dCvB-mhkT0w)
- [[Video] Elliptic Curves - Computerphile](https://www.youtube.com/watch?v=NF1pwjL9-DE)

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
![addition](/img/ecc_addition.png)
![addition1](/img/ecc_addition1.png)

### Q2: How is Bitcoin Public key converted to address?

![address](/img/bitcoin_address.png)
![address1](/img/bitcoin_address1.png)

*refer to [video](https://www.youtube.com/watch?v=FshMisRD2Uo&list=PLYRlUBnWnd5JdDFEGi4VO8gZyAQfX9P4I&index=86)

## Forum

## Reference
