# MathFoundationRL_note

## 西湖大学 强化学习笔记
### 第五课

---

### 1. MC basic

#### 问题1: 关于MC basic和截断的policy iteration有什么区别？

**答案1：** 简而言之，截断的PL它知道世界的运行规律，即state的转换概率以及行动action获得的奖励概率，它通过这些P以及pi最终可以迭代遍历出state，再通过这个精准的state来进行max_action的优化；而 MC 则缺少这些P，而只能用一次次遍历最终得到平均的state value。

---

### 2. MC exploring start和MC basic区别？

#### 问题1: MC basic的整体实现，pi不变？

#### 问题2: pi和model free的区别

#### 问题3: MC es的整体迭代过程的代码实现
