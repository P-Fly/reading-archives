# 经典单码加密法

## 概述

**单码加密法** 是一种替换加密法，其中每个明文只能被唯一的一个密文字母所替换。

## 关键词加密法

 1. 选择一个关键词，并去除重复的字母。

 2. 将该关键词写在字母表的下方，并用字母表的其它字母按标准顺序填写余下的空间。

### 关键词加密法分析

 1. 语言的每个字母都有自身的特性，比如出现的频率，与其它字母的联系，在单词中的位置等。

 2. 将标准英语字母分成 4 个频率组，猜测可能的映射。不同分组的两个相邻字母的出现频率差约为 2% 左右。

    ```
    高    E T A O N J R S H
    中    D L U C M
    低    P F Y W G B V
    极少  J K Q X Z
    ```

 3. 通过双联字母/三联字母，猜测可能的映射。比如 th，er。

## 仿射加密法 (affine cipher)

 1. 字母表的字母被赋予一个数字。

 2. 仿射加密法的密钥为 0 ~ 25 之间的数字对 (a, b)。其中a与26的最大公约数必须为1，即GCD(a, 26) = 1。

 3. 明文(p) 与 密文 (c) 对应的关系为：c = (ap + b)(mod 26)

## 多文字加密法

 1. 使用5个字母组成一个关键词，用这个关键词组成一个 5\*5 的矩阵。比如关键词为 codes：

    ```
      c o d e s
    c a b c d e
    o f g h i k
    d l m n o p
    e q r s t u
    s v w x y z
    ```
 2. 每个明文由标识该字母的行和列的字母对替代。

因为是用一对字母来替代每个明文字母，因此密文只包含5个字母。通过穷举法列举所有可能的排列，就可以得到密钥。

## 总结

 ![chapter 2][1]

 [1]: ./images/chapter_2.jpg
