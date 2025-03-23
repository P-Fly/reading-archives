# 经典多图加密法

## 概述

凡是一次加密一个字母的加密法都称为 **单图加密法 monographic cipher**。

**多图加密法 polygraphic cipher** 是作用于字符组。明文的 m 个字符组合被密文的 m 个字符组替代。

**多图加密法** 比 **单图加密法** 更安全，因为后者只有 26 个字母，而双图加密法有 676 (26 \* 26)种双图。三图加密法有 17576 (26 \* 26 \* 26)种三图。

## Playfair 加密法

 1. 选取一个单词构成 **Playfair Table**。比如单词为 **telegram**。

    ```
    t e l g r
    a m b c d
    f h i k n
    o p q s u
    v w x y z
    ```

 2. 对明文进行一些处理：

    - 将明文中的 j 改为 i。

    - 在明文中的双字母中插入一个等效字母，比如 x 或 q。

    - 如果明文为奇数，则在末尾添加一个等效字母，使明文字母数为偶数。

 3. 在 **Playfair Table** 中查找明文对，并根据下列规则之一选取密文：

    - 如果两个明文字符出现在同一行，选用右边的字符作为密文。

    - 如果两个明文字符出现在同一列，选用下方的字符作为密文。

    - 如果两个明文字符出现在不同的行和列，就形成了一个包含这两点的正方形，选用这个正方形上另外两个点的字母作为密文。

    ```
    明文         next time jay try something different
    转换后的明文 next qtime iay try something difqferent
    密文         hrvl olhbl hcv etg ypaleikkr bniohttlfr
    ```

## Hill 加密法

一种基于联立方程的加密算法，将 m 个字母的明文块加密成含有 m 个字母的密文快。密钥可以如下：

 ![Hill][1]

## 总结

 ![Chapter 4][2]

 [1]: ./images/hill.jpg
 [2]: ./images/chapter_4.jpg
