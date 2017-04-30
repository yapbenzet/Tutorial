## 题目分析：

A可以对B进行若干次攻击，每次攻击会让B进入一段时间的中毒状态，中毒的重复时间不叠加。给出A一串攻击时刻的序列（保证递增），问最后B一共会中毒多长时间。

### 解题思路：

模拟题，模拟攻击的过程。 
假设上一次中毒的终止时间是T，下一次攻击发生在t，每次攻击持续x秒中毒状态，总中毒时间是ans。 
首先让ans加上中毒时间x，但是这x可能会存在重复，比如这次的攻击时间t < 上一次终止时间T，那么T-t这一段时间在上次攻击的时候就已经被算过一次了，需要从ans中减掉。

#### 算法正确性：

算法模拟攻击过程，排除了所有的重复时间，正确性显然。时间复杂度为O(n)。

