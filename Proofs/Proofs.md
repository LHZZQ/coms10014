# Proofs

Created: 2024年11月23日 11:19
Class: COMS10014

# Odd and Even

一个整数$a$是：

- 偶数，如果我们可以写成 $a = 2k$ 的形式，其中k是某个整数。
- 奇数，如果我们可以写成 $a = 2k + 1$ 的形式，其中k是某个整数。

# Rules of Arithmetic

- 以下规则适用于自然数、整数和实数，除非另有说明：
    - 交换律：$a+b = b+a$ 和 $a×b = b×a$ 对任何数字$a，b$都成立。
    - 结合律：$(a+b)+c = a+(b+c)$ 对任何数字$a，b，c$都成立，乘法运算同理。
    - 分配律：$a×(b+c) = a×b + a×c$ 对任何数字$a，b，c$都成立。
    - 中性元素 0 & 1：$a+0 = a$ 和 $a×1 = a$  对任何数字a都成立。
    - 逆元素：在整数和实数上，但不包括自然数，$a+(−a) = 0$；仅在实数上，如果$a ≠ 0$，则$a×1/a = 1$。
    - 乘法和零：$a×0 = 0$ 对任何数字a都成立。更有趣的是，如果$a×b = 0$，则至少$a，b$中的一个已经是零；另一种表达方式是，如果$a ≠ 0$且$b ≠ 0$，则$a×b$也不为零。
        
        这是你需要推断出$(x−2)(x−3) = 0$的解是$2$和$3$的规则。
        
        注意，这条规则对于会“回绕”的数字不成立，比如计算机上的64位无符号整数，在这种情况下，例如$2^{63}×2$再次变为0
        

<aside>
💡

$$
 (a +b)^2 = a^2 +2ab+b^2
$$

</aside>

# Direct Proof

## **例1**

要求: 如果$a$是偶数$b$是奇数, 那么$ab$是偶数.
证明:

1. 已知$a$是偶数。根据定义，存在一个整数$k$，使得 $a=2k$。
2. 已知b是奇数。根据定义，存在一个整数$m$，使得 $b=2m+1$（注意，k已被使用，因此我们需要一个新变量）。
3. 计算：$ab=(2k)(2m+1)=4km+2k=2(2km+k)$。
4. 设 $c=2km+k$，那么我们有 $ab=2c$，其中$c$是一个整数。
5. 重新打包：得出结论$ab$是偶数。

## **例2：证明偶数的平方是偶数**

**命题**：如果$n$是偶数，那么 $n^2$ 也是偶数。

**证明**：因为$n$是偶数，存在某个$k$使得 $n=2k$。那么 $n^2=(2k)^2=4k^2=2(2k^2$)，因此 $n^2$ 是偶数

# Indirect Proof

## 原理

命题$P \to Q$（如果P，则Q）与其逆否命题$\neg Q \to \neg P$（如果不是Q，则不是P）是等价的

## **步骤：**

1. **选择逆否命题**：从假设逆否命题中的 $¬Q$ 开始，进行计算和逻辑推理。
2. **推导出 $\neg P$**：如果从 ¬Q 的假设中能推导出 $¬P$，那么原命题 $P→Q$ 得到证明。

## **示例1：证明如果 $n^2$ 是奇数，则n是奇数**

- **命题**：如果 $n^2$ 是奇数，则n是奇数。
- **逆否命题**：如果n不是奇数（即n是偶数），则 $n^2$ 不是奇数（即 $n^2$ 是偶数）。
- **证明**：
    - 假设n是偶数，即存在某个整数k使得 $n=2k$。
    - 计算 $n^2$：$n^2=(2k)^2=4k^2=2(2k^2)$，这表明 $n^2$ 是偶数。
    - 因此，如果n是偶数，则 $n^2$ 必然是偶数。这证明了逆否命题，从而证明了原命题。$n^2$

## **示例2：证明如果ab是偶数，则a或b是偶数**

- **命题**：如果ab是偶数，则a或b是偶数。
- **逆否命题**：如果a和b都不是偶数（即a和b都是奇数），则ab不是偶数（即ab是奇数）。
- **证明**：
    - 假设a和b都是奇数。设$a = 2k + 1，b = 2m + 1$，其中k和m是整数。
    - 计算 ab：$ab=(2k+1)(2m+1)=4km+2k+2m+1=2(2km+k+m)+1$这表明ab是奇数。
    - 因此，如果a和b都是奇数，则ab是奇数。这证明了逆否命题，从而证明了原命题。

# Proof by Contradiction

## **步骤：**

1. **假设命题为假**：从假设命题的否定出发。
2. **推理和计算**：进行逻辑推理和/或数学计算。
3. **寻找矛盾**：寻找在这个假设下出现的逻辑或计算上的矛盾。
4. **得出结论**：由于出现矛盾，说明假设命题为假是不可能的，因此原命题为真。

## **示例1：证明$\sqrt2$是无理数**

- **命题**：$\sqrt2$是无理数。
- **证明步骤**：
    - 假设$\sqrt2$是有理数，即存在整数A和$B（B≠0）$，使得 $\sqrt2 = \frac AB$。进一步假设这个分数已经是最简形式，即A和B没有共同因子。
    - 对等式两边平方得 $2 = \frac {A²}{B²}$，从而 $2B² = A²$。这意味着$A²$是偶数，从而A也必须是偶数（因为奇数的平方是奇数）。
    - 因为A是偶数，可以设$A = 2k$。代入原等式得 $2B² = (2k)² = 4k²$，简化得 $B² = 2k²$，这意味着$B²$也是偶数，因此B也必须是偶数。
    - 现在，A和B都是偶数，这与我们的假设（$\frac AB$是最简形式）矛盾，因为最简形式的分数不可能有共同因子。
    - 由于这个矛盾，我们的假设（$\sqrt2$是有理数）是错误的，因此$\sqrt2$必须是无理数。

## **示例2：证明如果ab是奇数，则a和b都是奇数**

- **命题**：如果ab是奇数，则a和b都是奇数。
- **证明步骤**：
    - 假设ab是奇数，但a和b不都是奇数，即至少有一个是偶数。
    - 如果a是偶数（或b是偶数），那么ab必定是偶数（因为偶数乘以任何整数都是偶数），这与我们的假设（ab是奇数）矛盾。
    - 因此，如果ab是奇数，则a和b必须都是奇数。

# Case Distinction

## **步骤：**

1. **识别所有可能的情况**：确定问题可以分解的所有情况。
2. **单独处理每种情况**：对每个情况进行分析和证明。
3. **合并结论**：从每种情况的结论中综合得出总结论。

## **示例1：证明n(n+1)总是偶数**

- **命题**：对于任何整数$n，n(n+1)$总是偶数。
- **证明步骤**：
    - 考虑两种情况：n是偶数和n是奇数。
        - **情况1：n是偶数**：
            - 设$n = 2k$，其中k是整数。
            - 计算$n(n+1) = 2k(2k+1) = 2(2k^2 + k)$，这是偶数。
        - **情况2：n是奇数**：
            - 设$n = 2k+1$，其中k是整数。
            - 计算$n(n+1) = (2k+1)(2k+2) = 2(2k^2 + 3k + 1)$，这也是偶数。
    - 因此，无论n是偶数还是奇数，n(n+1)都是偶数。

## **示例2:证明如果a+b是偶数，则a和b要么都是偶数，要么都是奇数**

- **命题**：如果$a+b$是偶数，则$a$和$b$要么都是偶数，要么都是奇数。
- **证明步骤**：
    - 假设$a+b = 2k$，其中$k$是整数。
    - 考虑两种情况：
        - **情况1：$a$是偶数**：
            - 设$a = 2m$，其中m是整数。
            - 计算$b = (a+b) - a = 2k - 2m = 2(k-m)$，因此b也是偶数。
        - **情况2：a是奇数**：
            - 设$a = 2m+1$，其中m是整数。
            - 计算$b = (a+b) - a = 2k - (2m+1) = 2(k-m)-1$，因此$b$也是奇数。
    - 因此，如果$a+b$是偶数，则$a$和$b$要么都是偶数，要么都是奇数。

# Euclid’s Theorem

## **欧几里得定理的定义和意义：**

欧几里得定理，也称为除法原理，说明对于任何整数$a$和任何正整数$b$，存在唯一的整数对$q$（商）和$r$（余数），使得：$a=bq+r$并且$0 \leq r < b$

## 示例1：证明整数都是奇数或偶数

- **命题**：所有整数要么是奇数，要么是偶数。
- **证明**：
    - 基于欧几里得定理，$a=bq-r$  取$b = 2$进行除法，那么对于任何整数$a$，都存在整数$q$和$r$使得
        
         $a=2q+r$，且r的取值范围为{0, 1}。
        
    - 当$r = 0$时，$a$是偶数；当$r = 1$时，$a$是奇数。
    - 因为每个整数$a$都可以用这样的形式表示，并且$r$的值只能是$0$或$1$，所以每个整数要么是偶数要么是奇数。

## 示例2：对于任意整数 $a$ 和任意正整数 $b>0$，最多只存在一对整数 $(q,r)$，使得 $a=qb+r$，并且 $r≥0$ 且 $r<b$。

**证明过程解释：**

- **假设**：假设存在两对这样的整数 $(q,r)$ 和 $(q′,r′)$，它们可能相同也可能不同。
- **逻辑推导**：从这个假设出发，我们知道以下事实：
    - $a,b,q,r,q′,r′$ 都是整数。
    - $b>0$
    - $a=qb+r 和 a=q′b+r′$
    - $0 \leq r < b 和 0≤r′<b。$
- **求差**：将两个方程相减得到 $a−a=qb+r−(q′b+r′)$，简化后为 $0=b(q−q′)+(r−r′)$。
- **重新排列**：从这里我们可以重排为 $b(q−q′)=r′−r$。
- **案例分析**：
    - **如果 $r′−r=0$**：则 $b(q−q′)=0$。因为 $b\not=0$，所以 $q−q′=0$，从而 $q=q′$ 和 $r=r′$。
    - **如果 $r′−r≠0$**：这会导致 $b(q−q′)$ 是正数或负数。但因为 $0≤r,r′<b，r′−r$ 必须小于 $b$ 并且大于 $−b$，这导致了与 $b(q−q′)$ 无法满足条件的矛盾。
- **结论**：通过这种情况的分析，我们可以看到，如果 $r′−r$ 为正或为负，都将导致逻辑上的矛盾。因此，$q=q′$ 和 $r=r′$ 是唯一可能的情况，这证明了整数对 $(q,r)$ 的唯一性。