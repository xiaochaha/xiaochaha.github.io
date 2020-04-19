---
title: 银行家算法避免死锁
date: 2019-12-07 20:13:58
tags: '银行家算法'
categories: 'OS'
---

## 1.银行家算法中的数据结构

1. Available可利用资源向量。
2. Max最大需求矩阵。
3. Allocation分配矩阵。
4. Need需求矩阵。

## 2.银行家算法

设**Requesti**是进程Pi的请求向量，**Request<sub>i</sub>[ j ]=k**，表示进程Pi需要K个Rj类型的资源。

当P<sub>i</sub>发出请求时候，系统按下步骤检查：

1. 如果**Request<sub>i</sub>[ j ]≤Need[ j ]**，到步骤二；否则出错，因为他所需要的资源已超过它所宣布的最大值。
2. 如果**Request<sub>i</sub>[ j ]≤Available[ j ]**到步骤三；否则尚无足够资源，P<sub>i</sub>需等待。
3. 系统试探分配资源给P<sub>i</sub> :
   **Available<sub>i</sub>[j]-=Request<sub>i</sub>[j];**
   **Allocation<sub>i</sub>[j]+=Request<sub>i</sub>[j];**
   **Need<sub>i</sub>[j]-=Request<sub>i</sub>[j];**
4. 执行安全性算法，若安全分配资源给Pi，否则作废恢复原来资源分配状态，让P<sub>i</sub>等待。

## 3.安全性算法

1. 设置两个工作向量**Work=Available**;**Finish**
2. 从进程集合中找到一个满足下述条件的进程，
   **Finish==false;**
   **Need<=Work;**
   如找到，执行（3)；否则，执行（4)
3. 设进程获得资源，可顺利执行，直至完成，从而释放资源。
   **Work=Work+Allocation;**
   **Finish=true;**
   **GOTO 2**
4. 如所有的进程Finish= true，则表示安全；否则系统不安全。

## 4.银行家算法举例

假定系统中有5个进程{P<sub>0</sub>，P<sub>1</sub>，P<sub>2</sub>，P<sub>3</sub>，P<sub>4</sub>}和三类资源{A，B，C}，各种资源数量为10、5、7，在T<sub>0</sub>时刻的资源分配情况如下表

|               | Max   | Allocation | Need      | Available |
| ------------- | ----- | ---------- | --------- | --------- |
|               | A_B_C | A_B_C      | A_B_C     | A_B_C     |
| P<sub>0</sub> | 7_5_3 | 0_1_0      | 7_4_3     | 3_3_2     |
| P<sub>1</sub> | 3_2_2 | 2_0_0      | **1_2_2** |           |
| P<sub>2</sub> | 9_0_2 | 3_0_2      | 6_0_0     |           |
| P<sub>3</sub> | 2_2_2 | 2_1_1      | **0_1_1** |           |
| P<sub>4</sub> | 4_3_3 | 0_0_2      | 4_3_2     |           |

### 1.T0时刻的安全性：利用安全性算法

Work=Available（3_3_2）

因为need≤Work

所以P<sub>1</sub>（**1_2_2**）P<sub>3</sub>（**0_1_1**）符合

得安全序列{P<sub>1</sub>，P<sub>3</sub>，P<sub>4</sub>，P<sub>2</sub>，P<sub>0</sub>}如下表（ps.安全系列不止一种可能，也可以P<sub>3</sub>开头）

|               | Work      | Need  | Allocation | Work+Allocation | Finish |
| ------------- | --------- | ----- | ---------- | --------------- | ------ |
|               | A_B_C     | A_B_C | A_B_C      | A_B_C           |        |
| P<sub>1</sub> | **3_3_2** | 1_2_2 | 2_0_0      | 5_3_2           | true   |
| P<sub>3</sub> | 5_3_2     | 0_1_1 | 2_1_1      | 7_4_3           | true   |
| P<sub>4</sub> | 7_4_3     | 4_3_1 | 0_0_2      | 7_4_5           | true   |
| P<sub>2</sub> | 7_4_5     | 6_0_0 | 3_0_2      | 10_4_7          | true   |
| P<sub>0</sub> | 10_4_7    | 7_4_3 | 0_1_0      | 10_5_7          | true   |

### 2.P<sub>1</sub>请求资源：P<sub>1</sub>发出请求向量Request<sub>1</sub>(1，0，2)，进行银行家算法

1. Request<sub>1</sub>(1，0，2)≤Need<sub>1</sub>（1，2，2）
2. Request<sub>1</sub>(1，0，2)≤Available<sub>1</sub>（3，3，2）
3. 系统假定可为P<sub>1</sub>分配资源，修改Available，Allocation<sub>1</sub>，Need<sub>1</sub>向量如下表（和第一张表比）

|               | Max   | Allocation            | Need                  | Available             |
| ------------- | ----- | --------------------- | --------------------- | --------------------- |
|               | A_B_C | A_B_C                 | A_B_C                 | A_B_C                 |
| P<sub>0</sub> | 7_5_3 | 0_1_0                 | 7_4_3                 | **(3_3_2)→（2_3_0）** |
| P<sub>1</sub> | 3_2_2 | **(2_0_0)→（3_0_2）** | **(1_2_2)→（0_2_0）** |                       |
| P<sub>2</sub> | 9_0_2 | 3_0_2                 | 6_0_0                 |                       |
| P<sub>3</sub> | 2_2_2 | 2_1_1                 | 0_1_1                 |                       |
| P<sub>4</sub> | 4_3_3 | 0_0_2                 | 4_3_2                 |                       |

1. 再进行安全算法检查系统是否安全。

|               | Work      | Need  | Allocation | Work+Allocation | Finish |
| ------------- | --------- | ----- | ---------- | --------------- | ------ |
|               | A_B_C     | A_B_C | A_B_C      | A_B_C           |        |
| P<sub>1</sub> | **2_3_0** | 0_2_0 | 3_0_2      | 5_3_2           | true   |
| P<sub>3</sub> | 5_3_2     | 0_1_1 | 2_1_1      | 7_4_3           | true   |
| P<sub>4</sub> | 7_4_3     | 4_3_1 | 0_0_2      | 7_4_5           | true   |
| P<sub>0</sub> | 7_4_5     | 7_4_3 | 0_1_0      | 7_5_5           | true   |
| P<sub>2</sub> | 7_5_5     | 6_0_0 | 3_0_2      | 10_5_7          | true   |

得到安全序列{P<sub>1</sub>，P<sub>3</sub>，P<sub>4</sub>，P<sub>0</sub>，P<sub>2</sub>}，系统安全，立即分配资源给P<sub>1</sub>

### 3.P<sub>4</sub>请求资源：P<sub>4</sub>发出请求向量Request<sub>4</sub>(3，3，0)，进行银行家算法检查

1. Request<sub>4</sub>(3，3，0)≤Need<sub>4</sub>（4，3，1）
2. Request<sub>4</sub>(3，3，0)≥Available<sub>4</sub>（2，3，0），P<sub>4</sub>等待

### 4.P<sub>0</sub>请求资源：<sub>P0</sub>发出请求向量Request<sub>0</sub>(0，2，0)，进行银行家算法检查

1. Request<sub>0</sub>(0，2，0)≤Need<sub>0</sub>（7，4，3）
2. Request<sub>0</sub>(0，2，0)≤Available<sub>0</sub>（2，3，0）
3. 系统假定可为P0分配资源，修改Available，Allocation<sub>1</sub>，Need<sub>1</sub>向量如下表（和第一张表比）

|               | Allocation            | Need                  | Available             |
| ------------- | --------------------- | --------------------- | --------------------- |
|               | A_B_C                 | A_B_C                 | A_B_C                 |
| P<sub>0</sub> | **(0_1_0)→（0_3_0）** | **(7_4_3)→（7_2_3）** | **(2_3_0)→（2_1_0）** |
| P<sub>1</sub> | 3_0_2                 | 0_2_0                 |                       |
| P<sub>2</sub> | 3_0_2                 | 6_0_0                 |                       |
| P<sub>3</sub> | 2_1_1                 | 0_1_1                 |                       |
| P<sub>4</sub> | 0_0_2                 | 4_3_2                 |                       |

1. 进行安全算法检查系统是否安全。Available（2_1_0）小于所有进程的需要Need，故系统进入不安全状态，不分配资源

#### **如果将P0发出请求向量Request<sub>0</sub>(0，2，0)变为Request<sub>0</sub>(0，1，0)可以么？**

答案是可以的，这里不做推导了。