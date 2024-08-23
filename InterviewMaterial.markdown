- [1. 把笔试基础班变厚](#1-把笔试基础班变厚)
- [2. Glossary](#2-glossary)
- [3. 面试题](#3-面试题)
  - [3.1. hello world](#31-hello-world)
  - [3.2. 快排与快速选择](#32-快排与快速选择)
- [4. 双指针(滑动窗口 数组大于零 存在单调性)](#4-双指针滑动窗口-数组大于零-存在单调性)
  - [4.1. 定长滑动窗口](#41-定长滑动窗口)
    - [4.1.1. 偶数子串](#411-偶数子串)
  - [4.2. 不定长滑动窗口](#42-不定长滑动窗口)
    - [4.2.1. 最长上升子数组](#421-最长上升子数组)
      - [4.2.1.1. 骑车路线原题🔗（最长上升子数组）](#4211-骑车路线原题最长上升子数组)
    - [4.2.2. 一般的`最长的`长度](#422-一般的最长的长度)
      - [4.2.2.1. 1493. 删掉一个元素以后全为 1 的最长子数组 - 力扣（LeetCode）](#4221-1493-删掉一个元素以后全为-1-的最长子数组---力扣leetcode)
      - [4.2.2.2. 最长彩带-内推鸭](#4222-最长彩带-内推鸭)
      - [4.2.2.3. 904. 水果成篮 - 力扣（LeetCode）](#4223-904-水果成篮---力扣leetcode)
      - [4.2.2.4. 1658. 将 x 减到 0 的最小操作数 - 力扣（LeetCode）](#4224-1658-将-x-减到-0-的最小操作数---力扣leetcode)
    - [4.2.3. 一般的`最短的`长度](#423-一般的最短的长度)
      - [4.2.3.1. 209. 长度最小的子数组 - 力扣（LeetCode）](#4231-209-长度最小的子数组---力扣leetcode)

依托于wiki，还有dchat的`我群`来准备面试话术和资料 争取能够打印出来

周末系统学习一下Juc

<img alt="picture 5" src="images/pic_1724304399656.png" width="300" /> 

# 1. 把笔试基础班变厚

- [ ] 1期 完成题目迁移
- [ ] 2期 完善代码 格式等 与布局
- [ ] 3期 刷题


# 2. Glossary

子串 == 子数组

> 枚举串首，$n^2$ 量级

子序列

> $2^n$ 量级


# 3. 面试题

## 3.1. hello world

```Java
public class Main{
    public static void main(String[] args){
        System.out.print("hello world");
    }
}
```

## 3.2. 快排与快速选择

```cpp
//快排
#include <iostream>

using namespace std;

const int N = 100010;

int q[N];

void quick_sort(int q[], int l, int r)
{
    if (l >= r) return;

    int i = l - 1, j = r + 1, x = q[l + r >> 1];
    while (i < j)
    {
        do i ++ ; while (q[i] < x);
        do j -- ; while (q[j] > x);
        if (i < j) swap(q[i], q[j]);
    }

    quick_sort(q, l, j);
    quick_sort(q, j + 1, r);
}

int main()
{
    int n;
    scanf("%d", &n);

    for (int i = 0; i < n; i ++ ) scanf("%d", &q[i]);

    quick_sort(q, 0, n - 1);

    for (int i = 0; i < n; i ++ ) printf("%d ", q[i]);

    return 0;
}
```

```cpp
//快速选择
#include <iostream>

using namespace std;

const int N = 100010;

int q[N];

int quick_sort(int q[], int l, int r, int k)
{
    if (l >= r) return q[l];

    int i = l - 1, j = r + 1, x = q[l + r >> 1];
    while (i < j)
    {
        do i ++ ; while (q[i] < x);
        do j -- ; while (q[j] > x);
        if (i < j) swap(q[i], q[j]);
    }

    if (j - l + 1 >= k) return quick_sort(q, l, j, k);
    else return quick_sort(q, j + 1, r, k - (j - l + 1));
}

int main()
{
    int n, k;
    scanf("%d%d", &n, &k);

    for (int i = 0; i < n; i ++ ) scanf("%d", &q[i]);

    cout << quick_sort(q, 0, n - 1, k) << endl;

    return 0;
}
```


# 4. 双指针(滑动窗口 数组大于零 存在单调性)

## 4.1. 定长滑动窗口

### 4.1.1. 偶数子串

```java
import java.util.*;

public class Main {
    // 定义检查函数，检查每个字符出现的次数是否为偶数
    public static boolean check(int[] cnts) {
        for (int val : cnts) {
            if (val % 2 == 1) {
                return false;
            }
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // 读取输入
        int n = scanner.nextInt();
        int k = scanner.nextInt();
        String s = scanner.next();
        // 初始化结果和计数器
        int res = 0;
        int[] cnts = new int[26];
        // 初始化左右指针
        int l = 0, r = 0;
        // 遍历字符串
        for (r = 0; r < n; r++) {
            cnts[s.charAt(r) - 'a']++;
            if (r - l + 1 > k) {  // 如果窗口大小>k了，左指针右移
                cnts[s.charAt(l) - 'a']--;
                l++;
            }
            if (r - l + 1 == k) {  // 如果窗口大小=k了，检查当前窗口内的字符出现次数
                if (check(cnts)) {
                    res++;
                }
            }
        }
        // 输出结果
        System.out.println(res);
    }
}
```

## 4.2. 不定长滑动窗口

### 4.2.1. 最长上升子数组
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        int[] w = new int[n];
        for (int i = 0; i < n; i++) {
            w[i] = scanner.nextInt();
        }
        int res = 0;  // 最大长度
        for (int l = 0; l < n; l++) {
            int r = l;
            // 如果下一个元素大于当前元素，右边界向右移动
            while (r + 1 < n && w[r + 1] > w[r]) {
                r++;
            }
            // 更新最大长度
            res = Math.max(res, r - l + 1);
            l = r;
        }
        System.out.println(res);
    }
}
```

#### 4.2.1.1. 骑车路线[原题🔗](https://www.sspnote.com/oj/3/318)[（最长上升子数组）](#321-最长上升子数组)

### 4.2.2. 一般的`最长的`长度

> $r$指针先移动，移动到某一个区间，不满足条件的时候（比如题目要求区间和不大于某一个正整数，或者区间中元素$x$的个数$\le k$），$l$指针右移，直到满足条件。

#### 4.2.2.1. [1493. 删掉一个元素以后全为 1 的最长子数组 - 力扣（LeetCode）](https://leetcode.cn/problems/longest-subarray-of-1s-after-deleting-one-element/description/)

```java
class Solution {
    public int longestSubarray(int[] nums) {
        int res = 0, n = nums.length;
        int sum = 0;
        for (int l=0,r = 0; r < n; r++) {
            sum += nums[r];
            while (sum < r - l) {
                sum -= nums[l++];
            }
            res = Math.max(res, r - l);
        }

        return res;
    }
}
```

找序列和为长度-1的`最长的`串

#### 4.2.2.2. [最长彩带-内推鸭](https://www.sspnote.com/oj/3/337)

```java
import java.util.HashMap;
import java.util.Scanner;

public class Main {
    private static final int N = 100000 + 10;
    private static int[] a = new int[N];
    private static int n, k;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        n = scanner.nextInt();
        k = scanner.nextInt();

        // 读取数组a的值
        for (int i = 0; i < n; i++) {
            a[i] = scanner.nextInt();
        }

        HashMap<Integer, Integer> cnts = new HashMap<>(); // 统计每一种彩带的个数
        int res = 0;

        // 使用滑动窗口寻找满足条件的最长子数组
        for (int l = 0, r = 0; r < n; r++) {
            cnts.put(a[r], cnts.getOrDefault(a[r], 0) + 1);
            // 当前区间不满足条件
            while (cnts.size() > k) {
                cnts.put(a[l], cnts.get(a[l]) - 1);
                if (cnts.get(a[l]) == 0) {
                    cnts.remove(a[l]); // 删除key以确保哈希表的大小更新
                }
                l++;
            }
            res = Math.max(res, r - l + 1); // 更新最大长度
        }

        System.out.println(res);
    }
}
```

#### 4.2.2.3. <a href="https://leetcode.cn/problems/fruit-into-baskets/description/">904. 水果成篮 - 力扣（LeetCode）</a>

#### 4.2.2.4. <a href="https://leetcode.cn/problems/minimum-operations-to-reduce-x-to-zero/description/">1658. 将 x 减到 0 的最小操作数 - 力扣（LeetCode）</a>

> 求一个`最长的`连续区间（因为要使得删除的元素最小化，则剩下的区间长度一定是`最长的`），使得其满足区间和等于$sum-x$，我们利用上述模版即可

```java
public class Solution {
    public int minOperations(int[] nums, int x) {
        int total = Arrays.stream(nums).sum();
        int target = total - x;  // 将问题转化为区间和为target的最大长度
        if (target < 0) {  // 题干数组元素都为正 故一定无解 
            return -1;
        }
        int n = nums.length;
        int res = -1;  // 不存在答案
        for(int l = 0, r = 0, sum_val = 0;r<n;r++) {  // 定义左指针、右指针、区间和
            sum_val += nums[r];
            while (sum_val > target) {
                sum_val -= nums[l];
                l++;
            }
            if (sum_val == target) {  // 更新最长值
                res = Math.max(res, r - l + 1);
            }
        }
        if (res == -1) {
            return res;
        }
        return n - res;
    }
}
```

### 4.2.3. 一般的`最短的`长度

> $r$指针先移动，移动到某一个区间，满足条件的时候（比如题目要求区间和大于某一个正整数，或者区间中元素$x$的个数$\ge k$），$l$指针右移，直到不满足条件。

#### 4.2.3.1. <a href="https://leetcode.cn/problems/minimum-size-subarray-sum/description/">209. 长度最小的子数组 - 力扣（LeetCode）</a>

```java
public class Solution {
    public int minSubArrayLen(int target, int[] nums) {
        int n = nums.length;
        int res = Integer.MAX_VALUE;  // 初始化结果为最大整数
        int sum = 0;  // 定义双指针l,r,区间和sum
        for (int l = 0, r = 0; r < n; r++) {  // 右指针向右移动
            sum += nums[r];
            while (sum >= target) {  // 当前区间满足条件，更新最小值
                res = Math.min(res, r - l + 1);
                sum -= nums[l];
                l++;  // 左指针向右移动
            }
        }
        return (res == Integer.MAX_VALUE) ? 0 : res;  // 如果结果仍为最大整数，说明没有满足条件的子数组，返回0
    }
}
```