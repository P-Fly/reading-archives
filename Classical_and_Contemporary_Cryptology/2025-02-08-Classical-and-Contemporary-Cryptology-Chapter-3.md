# 经典多码加密法

## 概述

**多码加密法** 是一种 **替换加密法**，其中的每个明文字母可以用密文中的多个字母来替代，而每个密文字母也可以表示多个明文字母。

**多码加密法** 可以消除字符的特性，因此能有效的对付 **频率分析工具**。

## Vigenere 加密法

 1. 生成 **Vigenere Table**，用一个 **26x26** 的方阵，按照字母顺序通过循环移位来填充每一行。

    ```
      a b c d e f ... x y z
    a a b c d e f ... x y z
    b b c d e f g ... y z a
    c c d e f g h ... z a b
    d d e f g h i ... a b c
    e e f g h i j ... b c d
    f f g h i j k ... c d e
    .
    .
    .
    x x y z a b c ... u v w
    y y z a b c d ... v w x
    z z a b c d e ... w x y
    ```

 2. 选择一个关键词做为密钥，并在明文上方不断重复书写。

 3. 将密钥字母做为行索引，明文字母做为列索引，通过 **Vigenere Table** 来确定密文。

    ```
    密钥 hold ho ldh oldholdho
    明文 this is the plaintext
    密文 avtv pg ekl dwdpbeheh
    ```

### Vigenere 加密法分析

 1. 使用 **IC测试(Index of Coincidence)** 测试加密法是否为 **多码加密法**。

    ![vigenere_1][1]
    ![vigenere_2][2]

 2. 使用 **Kasiski** 测试法得到密码长度。

    ![vigenere_2][3]

 3. 将破解 **多码加密** 转换为破解多个不同的 **单码加密** 的问题。

## 自动密钥加密法

与 **Vigenere 加密法** 相似，但是关键词只使用一次，后续使用明文或者密文作为密钥。

    ```
    密钥 a lice ihop ethis worksb ette
    明文 i hope this works better than
    密文 i swri bowh ahysk xskdws xatr
    ```

这种加密法有一个非常不利之处：加密和解密过程中任何地方的一个错误都将影响其后的所有文字。

## Nihilist 加密法

 1. 选取一个单词构成 **Polybius Table**。比如单词为 **example**。

    ```
      1 2 3 4 5
    1 e x a m p
    2 l b c d f
    3 g h i k n
    4 o q r s t
    5 u v w y z
    ```

 2. 选取一个关键词，利用 **Polybius Table** 将其转换成数字。比如单词 **next**。

    ```
    next: 35 11 12 45
    ```

 3. 在明文上方不断重复书写关键词，这样每个明文字母都会与关键词的数字配对。

 4. 利用 **Polybius Table** 将明文字母转换成数字。

 5. 将明文数字与关键词数字相加，如果和大于 100 则减去 100，最终得到的数字就是对应的密文。

    ```
    明文      t  h  i  s  i  s  t  h  e  p  l  a  i  n  t  e  x  t
    明文数字 45 32 33 44 33 44 45 32 11 15 21 13 33 35 45 11 12 45
    关键数字 35 11 12 45 35 11 12 45 35 11 12 45 35 11 12 45 35 11
    密文     80 43 45 89 68 55 57 77 46 26 33 58 68 46 57 56 47 56
    ```

## 圆柱面加密法

 1. 由20个轮组成，每个轮上的字母表顺序不同。

 2. 选定一组轮的顺序作为密钥。

 3. 转动这些轮，使明文出现在同一条直线上，然后可以选取任意的其它直线上的字母作为密文。

    ![bazeries][4]

### Bazeries 圆柱面加密法分析

 1. 该方法假设两个事实：

    - 已知圆柱面的内容。

    - 至少知道一个明文单词。

    该方法是已知明文攻击法，其目标是确定圆柱面的实际顺序。

 2. 通过已知明文单词扫描密文，查找既能产生明文单词，又能得到该密文段的圆柱面排列顺序的位置。

 3. 从已知明文单词与密文的可能对齐开始，为所有可能的圆柱面排列创建一个表格。顶部是已知单词，每一行为每个圆柱面中已知单词行的下一行。

 4. 查找一个对这几个字母都适用的圆柱面排列。

 5. 如果失败，则回到 **第 3 步**，并将表格中的每一行修改为每个圆柱面中已知单词行的第二行，依次类推。

## 回转轮加密法

 1. 回转轮是一个圆盘，它的两面都有电子接点，每个接点代表字母表中的一个字母。内部有连接各接点的电线，这种连接方式定义了单码替换方式。

    ![rotor][5]

 2. 将几个回转轮串联起来，并以不同的速率转动，就可以构建成一个功能强大的多码加密系统。

    ![rotor][6]

    ![enigma][7]

## 总结

 ![chapter 3][8]

 [1]: ./images/vigenere_1.jpg
 [2]: ./images/vigenere_2.jpg
 [3]: ./images/vigenere_3.jpg
 [4]: ./images/bazeries.jpg
 [5]: ./images/rotor1.jpg
 [6]: ./images/rotor2.jpg
 [7]: ./images/enigma.jpg
 [8]: ./images/chapter_3.jpg
