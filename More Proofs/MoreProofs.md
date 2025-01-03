# More Proofs

Created: 2024年11月23日 12:16
Class: COMS10014

# Proof Strategies

$⊨$ means that the right-hand side is a tautology 表示逻辑上必然成立

# Laws of Logical Reasoning, Part 1

## Modus Ponens

如果你知道 $A$ ，且知道 $A → B$ ，那么你可以得出$B$

$$
A, A → B ⊢ B           
$$

## Modus Tollens

如果你知道 $¬B$（B是假的）且知道 $A → B$ ，那么你可以得出 $¬A$

$$
¬B, A → B ⊢ ¬A
$$

- 示例
    
    对 证明任何整数n，$(n(n + 1))^2$ 总是偶数
    
    ### **第一种证明方法（使用肯定前件法则）**
    
    - **证明**：我们已经证明了$n(n + 1)$总是偶数，并且如果 $x$ 是偶数，那么 $x^2$ 也是偶数。通过使用肯定前件法则（Modus Ponens），由于 $n(n + 1)$ 是偶数，因此 $(n(n + 1))^2$ 也是偶数
    
    ### **第二种证明方法（使用否定后件法则）**
    
    - **证明**：我们已经证明了 $n(n + 1)$ 总是偶数，并且如果 $x^2$ 是奇数，那么 $x$ 也是奇数。通过使用否定后件法则（Modus Tollens），因为 $n(n + 1)$ 不是奇数，所以 $(n(n + 1))^2$ 也不是奇数，即它是偶数。

# Laws of Logical Reasoning, Part 2

## Disjunctive Syllogism 排中律

如果我们知道 $A ∨ B$ ，并且知道 $¬A$ ，那么我们可以得出 $B$ 

## Hypothetical Syllogism 假言三段论

if A implies B, and B implies C, then A implies C

 In symbols, $A → B,B →C ⊢A→C$

# Laws of Logical Reasoning,Part3

## **合取引入（∧ introduction）**

- **定义**：如果我们知道A且知道B，则我们可以得出$A∧B$。这表示A和B同时为真。
- **符号表示**： $A, B ⊢ A∧B$ 。
- **应用示例**：如果我们知道“这个数字是偶数”（A）且“这个数字大于10”（B），则我们可以得出“这个数字是一个大于10的偶数”（ $A∧B$ ）。

## **合取消除（∧ elimination）**

- **定义**：如果我们知道 $A∧B$ ，则我们可以单独得出A，也可以单独得出B。
- **符号表示**： $A∧B ⊢ A 和 A∧B ⊢ B$ 。
- **应用示例**：如果我们知道“这个数字是大于10的偶数”（ $A∧B$ ），我们可以分别得出“这个数字是偶数”（A）和“这个数字大于10”（ $B$ ）。

## **析取引入（∨ introduction）**

- **定义**：如果我们知道$A$，那么对于任何$B$，我们都可以得出$A∨B$，或者如果我们更喜欢，可以得出$B∨A$。
- **符号表示**： $A ⊢ A∨B 和 A ⊢ B∨A$ 。
- **应用示例**：如果我们知道“今天是周末”（A），我们可以得出“今天是周末或者天气晴朗”（A∨B），即使我们不知道天气情况如何。

## **析取消除（∨ elimination）**

- **定义**：如果我们知道 $A∨B$ ，并且我们分别知道$A$可以得出$C$，$B$也可以得出$C$，那么我们可以得出$C$。
- **符号表示**： $(A∨B, A ⊢ C, B ⊢ C) ⊢ C$ 。
- **应用示例**：如果我们知道“这个数字是奇数或偶数”（ $A∨B$ ），并且我们知道无论是奇数还是偶数都属于整数范畴（C），则可以得出“这个数字是整数”（C）。

## **否定引入（¬ introduction）**

如果在某个范围内， 我们能够从A推导出矛盾（F），那么我们可以得出 $¬A$ 。 $(A⊢F)⊢¬A$ 

- (或许你想要个例子吗，我光看这个没看懂)
    
    证明“如果一个数是偶数，那么它不可能是奇数”。
    
    证：
    
    1. 假设A是偶数，则 $A=2k$ （
    $k$是某个整数）
        1. 同时再假设A是奇数（创造出一个矛盾），则 $A=2m+1$ （ $m$ 也是某个整数）
    2. 推导矛盾：假设 $A$ 同时是偶数和奇数（矛盾）
        1. 如果 $A=2k$ （偶数），并且 $A=2m+1$ （奇数），那么我们可以将这两个表达式相等表示为：
        
        👉 $2k = 2m+1$  
        
        👉 $2k - 2m = 1$  
        
        👉 $2(k-m)= 1$ 
        
        👉  $2(k-m)$是偶数，不可能等于  $1$ 
        
    3. 得出矛盾：反正矛盾了
    4. 所以 $A$ 是偶数和 $A$ 是奇数矛盾了，所以当 $A$ 是偶数的时候， $A $不是奇数，即  $\neg A$  成立！

## **否定消除（¬ elimination）**

如果我们在某个范围内同时得出A和¬A，则我们有矛盾，理论上可以得出任何结论（ $B$ ）。 $A ,¬A⊢B$ 

- （又有个例子）
    
    不管我活着（A）还是死掉了（ $\neg A$ ），地球都在转(B) .
    
    “不论吾生死，天地依旧运转” 耶~~~
