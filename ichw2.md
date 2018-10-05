# ichw
## 1.用你的语言描述图灵为什么要证明停机问题, 其证明方法和数学原理是什么.     
   
  图灵在计算机理论的基础上解决了第三次数学危机。其证明方法是反证法，从假设推出矛盾。数学原理则是罗素悖论，而“自我指涉”可导致罗素悖论。简单来说，一个命题的真或假依赖于其本身的真假，即可为自我指涉。
## 2.你在向中学生做科普，请向他们解释二进制补码的原理
原码与补码之和正好为2^N(N为码长)
## 3.
|Sign   |Exp   |Frac   |Value   |
|-------|------|-------|--------|
|*      |0000000|00000000|±0.0|
|0|0111111|00000000|1.0|
|1|0111111|00000000|-1.0|
|* |0000000|00000001|  ±  (2^{-8}*2^{-62}) |
|* |0000000|11111111|  ± (1-2^{-8}) * 2^{-62} |
|* |1111111|00000000| ± ∞ |
|* |1111111|non zero| NaN |
|* |0000001|00000000| ±2^{-62}|
|* |1111110|11111111| ±(2-2^{-8})*2^{63}  |
