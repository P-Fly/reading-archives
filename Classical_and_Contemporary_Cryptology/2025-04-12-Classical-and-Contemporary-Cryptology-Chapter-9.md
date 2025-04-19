# 密钥管理，数字签名，散列函数与证书

## 概述

现代密码除了 **机密性**，还需要保证 **完整性**，**真实性**。

## 密钥交换

**Diffie-Hellman** 密钥交换系统：

 1. Bob 和 Alice 共享两个数：P：一个大素数，g：一个小于P的随机数。

 2. Alice 选择一个保密的随机数 a，并将值 g\^a mod p 发送给 Bob。

 3. Bob 选择一个保密的随机数 b，并将值 g\^b mod p 发送给 Alice。

 4. Alice 使用自己的保密随机数与 Bob 发给自己的值计算：k = (g\^b mod p)\^a mode p

 5. Bob 使用自己的保密随机数与 Alice 发给自己的值计算：k = (g\^a mod p)\^b mode p

 6. k 就是共同密钥。

该算法本身不能抵御 **中间人攻击**。

## 可靠性

 ![RSA][1]

## 数字签名

 ![Signature][2]

## 公钥基础设施和证书

### 建立证书

 ![Create Certificates][3]

### 使用证书

 ![Use Certificates][4]

## 应用

 - 智能卡

 - 安全套接层

## 总结

 ![Chapter 9][5]

 [1]: ./images/rsa.jpg
 [2]: ./images/signature.jpg
 [3]: ./images/create_certificates.jpg
 [4]: ./images/use_certificates.jpg
 [5]: ./images/chapter_9.jpg
