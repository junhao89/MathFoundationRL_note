# MathFoundationRL_note

## 西湖大学 强化学习笔记
### 第五课

---

### 1. MC basic

#### 问题1: 关于MC basic和截断的policy iteration有什么区别？

**答案1：** 简而言之，截断的PL它知道世界的运行规律，即state的转换概率以及行动action获得的奖励概率，它通过这些P以及pi最终可以迭代遍历出state value，再通过这个精准的state来进行max_action的优化；而 MC 则缺少这些P，而只能用一次次遍历最终得到平均的action value。

---

### 2. MC exploring start

#### 问题1: MC basic的整体实现，pi不变？
**答案1：**： Basic MC 的单次采样过程中，pi是不变的，后面的inprovement才会变

#### 问题2: pi和model free的区别
**答案2：**：pi是策略，在什么state进行什么action的选择问题，而model free是进行action后state的概率分布以及执行action后的reward概率分布

#### 问题3: MC exploring start和MC basic区别？
**答案3：**：basic会使用两个for循环来遍历所有的(s,a),最终算出一个exp，然后再更新pi。而前者会通过遍历一个（s，a）通过在一个遍历序列中提取多个return，可以高效利用数据，并且是一个episode就更新一次pi。


### 3. MC epsilon-greedy
无问题，只是引入了一个epsilon因子，在policy improvement中选择action并不是选择最大的action state，而是使用概率，其他非最大值的动作也可能被选取到（会引出一个问题，当惩罚很重时候，也会有一定概率走向悬崖，引入后面的sora和q learning。
