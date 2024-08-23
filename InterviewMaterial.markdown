- [1. Glossary](#1-glossary)
- [2. 面试杂题](#2-面试杂题)
  - [2.1. hello world](#21-hello-world)
- [3. 双指针](#3-双指针)
  - [3.1. 定长滑动窗口](#31-定长滑动窗口)
    - [3.1.1. 偶数子串](#311-偶数子串)
  - [3.2. 不定长滑动窗口](#32-不定长滑动窗口)
    - [3.2.1. 最长上升子数组](#321-最长上升子数组)
      - [3.2.1.1. 骑车路线原题🔗（最长上升子数组）](#3211-骑车路线原题最长上升子数组)
    - [3.2.2. 1493. 删掉一个元素以后全为 1 的最长子数组 - 力扣（LeetCode）](#322-1493-删掉一个元素以后全为-1-的最长子数组---力扣leetcode)

依托于wiki，还有dchat的`我群`来准备面试话术和资料 争取能够打印出来

周末系统学习一下Juc

<img alt="picture 5" src="images/pic_1724304399656.png" width="300" />  

# 1. Glossary

子串 == 子数组

> 枚举串首，$n^2$ 量级

子序列

> $2^n$ 量级


# 2. 面试杂题

## 2.1. hello world

```Java
public class Main{
    public static void main(String[] args){
        System.out.print("hello world");
    }
}
```

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


# 3. 双指针

## 3.1. 定长滑动窗口

### 3.1.1. 偶数子串

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

## 3.2. 不定长滑动窗口

### 3.2.1. 最长上升子数组
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

#### 3.2.1.1. 骑车路线[原题🔗](https://www.sspnote.com/oj/3/318)[（最长上升子数组）](#321-最长上升子数组)

### 3.2.2. [1493. 删掉一个元素以后全为 1 的最长子数组 - 力扣（LeetCode）](https://leetcode.cn/problems/longest-subarray-of-1s-after-deleting-one-element/description/)

找序列和为长度-1的最长串