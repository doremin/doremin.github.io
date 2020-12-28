---
layout: post
title:  "The Elements of Computing Systems - 1"
author: "doremin"
tags: [The Elements of Computing Systems, CE]
---

## NAND 게이트로 NOT, AND, OR, XOR 게이트 만들기
### NAND 게이트 진리표

|Input (A, B)|Output|
|--|--|
|0, 0|1|
|0, 1|1|
|1, 0|1|
|1, 1|0|

### NOT 게이트
NAND(0, 0) => 1, NAND(1, 1) => 0 임을 위의 표에서 알 수 있다.
∴ NAND(A, A) => A'

![NANDToNOT](/assets/images/2020-12-28-1.png)

### AND 게이트

$$
\begin{aligned}
    NAND(A,\ B) => (A•B)' \\
    AND(A,\ B) => A•B\\
    ∴ NOT(NAND(A,\ B)) = AND(A,\ B)
\end{aligned}
$$
![NANDToAND](/assets/images/2020-12-28-2.png)

### Or 게이트

$$
\begin{aligned}
    NAND(A,\ B) => (A•B)' \\
    Or(A,\ B) => A+B => (A'\ •\ B')' => NOT(NOT(A)\ •\  NOT(B))\\
    => NOT(NOT(NAND(NOT(A)\ •\ NOT(B)))) => NAND(NOT(A),\ NOT(B))\\
    ∴ NAND(NOT(A),\ NOT(B)) = OR(A,\ B)
\end{aligned}
$$
![NANDToOR](/assets/images/2020-12-28-3.png)

### XOR

$$
\begin{aligned}
    NAND(A,\ B) => (A•B)' \\
    XOR(A,\ B) => A'•B\ +\ A•B' \\
    => NOT(A)•B\ +\ A•Not(B) \\
    => NOT(NAND(NOT(A),\ B)) + NOT(NAND(A,\ NOT(B))) \\
    => NAND(NOT(NOT(NAND(NOT(A),\ B))), NOT(NOT(NAND(A,\ NOT(B))))) \\
    => NAND(NAND(NOT(A),\ B), NAND(A,\ NOT(B))) \\
    ∴ NAND(NAND(NOT(A),\ B), NAND(A,\ NOT(B))) = XOR(A,\ B)
\end{aligned} 
$$
![NANDToXOR](/assets/images/2020-12-28-4.png)
