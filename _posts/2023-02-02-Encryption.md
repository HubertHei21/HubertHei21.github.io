---
title: .NET加密
author: Hubert
date: 2023-02-02
category: .NET
layout: post
---

* .NET Core 中可用的对称加密选项有：
  * AES (System.Security.Cryptography.Aes.Create())
  * 3DES (System.Security.Cryptography.TripleDES.Create())
* 而对于非对称加密
  * RSA (System.Security.Cryptography.RSA.Create())

* 对称加密

> DES
> 美国数据加密标准
> AES(推荐)
> 高级加密标准 (Advanced Encryption Standard, AES),又称Rijndael加密法

* 非对称加密

> RSA
>所谓非对称，就是指该算法加密和解密使用不同的密钥，即使用加密密钥进行加密、解密密钥进行解密。
>在RAS算法中，加密密钥（即公开密钥）PK是公开信息，而解密密钥（即秘密密钥）SK是需要保密的。
>加密算法E和解密算法D也都是公开的。
>虽然解密密钥SK是由公开密钥PK决定的，由于无法计算出大数n的欧拉函数phi(N)，所以不能根据PK计算出SK。
>