## 题目分析：

给出n个区间[L,R]，要求删除最少的区间，使得任意两个区间都没有重叠部分。 

### 解题思路：

贪心思想。 
按照每个节点的end从小到大排序，从第一个开始，将当前区间的end和后面一个节点的start比较，如果end <= start那么说明两个区间没有重合，将后面一个区间作为当前点，继续向后比较。如果当前区间的end和后面一个区间的start比较，end > start说明有重合，那么就需要删除后一个区间，使得答案增加1，并继续向后面比较。 
算法复杂度为O(nlogn)。 


#### 算法正确性：

按照这样的规则排序，如果两个区间A和B有重叠，且A排在B之前，那么有两种情况： 
1. 区间B包含区间A，既然存在重复，说明至少也要删除一个区间，之所以删B不删A，是因为B包含A，显然删掉B有较大可能减少更多的重叠部分。
2. 区间A和B仅重叠一部分，这种情况下，由于B的右端点大于等于A的右端点，说明B对于之后的区间重叠的可能性更大，所以应该删除B。 
综上所述，改贪心策略正确。
