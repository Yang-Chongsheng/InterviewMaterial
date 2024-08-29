- [1. 把笔试基础班变厚](#1-把笔试基础班变厚)
- [2. Glossary](#2-glossary)
  - [2.1. 快读](#21-快读)
- [3. 面试题](#3-面试题)
  - [3.1. hello world](#31-hello-world)
  - [3.2. 快排与快速选择](#32-快排与快速选择)
  - [3.3. 写一个函数将 ipv4 地址字符串 (仅包含数字，点，空格) 转化成 32 位整数。另外，数字和点之间的空格是合法的，其他情况均为非法地址，要求输出合法地址的 32 位整型结果](#33-写一个函数将-ipv4-地址字符串-仅包含数字点空格-转化成-32-位整数另外数字和点之间的空格是合法的其他情况均为非法地址要求输出合法地址的-32-位整型结果)
  - [3.4. 斐波那契数列 考察点：递归、非递归写法；时间复杂度计算](#34-斐波那契数列-考察点递归非递归写法时间复杂度计算)
  - [3.5. 基于 UDP 实现可靠的传输协议](#35-基于-udp-实现可靠的传输协议)
  - [3.6. 读文件](#36-读文件)
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
      - [4.2.3.2. 三值字符串-内推鸭](#4232-三值字符串-内推鸭)
      - [4.2.3.3. K0序列-内推鸭](#4233-k0序列-内推鸭)
    - [4.2.4. 求方案数](#424-求方案数)
      - [4.2.4.1. 713. 乘积小于 K 的子数组 - 力扣（LeetCode）](#4241-713-乘积小于-k-的子数组---力扣leetcode)
      - [4.2.4.2. 2302. 统计得分小于 K 的子数组数目 - 力扣（LeetCode）](#4242-2302-统计得分小于-k-的子数组数目---力扣leetcode)
      - [4.2.4.3. 删除子数组-内推鸭](#4243-删除子数组-内推鸭)
- [5.](#5)

依托于wiki，还有dchat的`我群`来准备面试话术和资料 争取能够打印出来

周末系统学习一下Juc

<img alt="picture 5" src="images/pic_1724304399656.png" width="300" /> 

# 1. 把笔试基础班变厚

- [ ] 1期 完成题目迁移
- [ ] 2期 完善代码 格式等 与布局
- [ ] 3期 刷题
> 推荐书籍
由 谈明亮创建, 最后修改于一月 17, 2020<br>
架构<br>
数据密集型应用系统设计 9.6 https://book.douban.com/subject/30329536/
系统架构 9.1 https://book.douban.com/subject/26938710/
架构整洁之道 8.7 https://book.douban.com/subject/30333919/
演进式架构 7.2 https://book.douban.com/subject/34793521/
<br>微服务<br>
微服务设计 8.2 https://book.douban.com/subject/26772677/
微服务架构设计模式 9.1 https://book.douban.com/subject/33425123/
生产微服务 8.0 https://book.douban.com/subject/27127050/
<br>混沌工程<br>
混沌工程：Netflix系统稳定性之道 6.6 https://book.douban.com/subject/34466272/
<br>容器编排<br>
Kubernetes in Action中文版 9.3 https://book.douban.com/subject/30418855/
深入浅出 Docker 8.2 https://book.douban.com/subject/30486354/
Service Mesh 目前没有特别好的书推荐
<br>DevOps<br>
DevOps实践指南 8.5 https://book.douban.com/subject/30186150/
SRE：Google运维解密 9.0 https://book.douban.com/subject/26875239/
<br>编码<br>
编写可读代码的艺术 8.7 https://book.douban.com/subject/10797189/
重构第二版 9.5 https://book.douban.com/subject/30468597/
代码整洁之道 8.6 https://book.douban.com/subject/4199741/
<br>PHP 内核<br>
PHP7内核剖析 8.1 https://book.douban.com/subject/27197032/
<br>Go<br>
Go程序设计语言 8.8 https://book.douban.com/subject/27044219/
Go Web 编程 8.2 https://book.douban.com/subject/27204133/
Go语言高级编程 8.8 https://book.douban.com/subject/34442131/
<br>安全<br>
图解密码技术 9.1 https://book.douban.com/subject/26265544/
<br>HTTP<br>
HTTP权威指南 8.6 https://book.douban.com/subject/10746113/
HTTP/2基础教程 7.2 https://book.douban.com/subject/27665112/
<br>底层<br>
C 程序设计语言 9.4分 https://book.douban.com/subject/1139336/
UNIX环境高级编程 9.6分 https://book.douban.com/subject/25900403/
UNIX网络编程 卷1：套接字联网API 9.2分 https://book.douban.com/subject/26434583/
C 语言程序设计 9.3分 https://book.douban.com/subject/4279678/
C语言接口与实现 9.0 https://book.douban.com/subject/6801697/
Linux/UNIX系统编程手册 9.2分 https://book.douban.com/subject/25809330/
数据结构与算法分析 8.9 https://book.douban.com/subject/1139426/
深入理解计算机系统 9.9 https://book.douban.com/subject/26912767/

# 2. Glossary

子串 == 子数组

> 枚举串首，$n^2$ 量级

子序列

> $2^n$ 量级

## 2.1. 快读

```java
import java.io.*;
import java.util.StringTokenizer;
// 注意类名必须为Main
class Main {
    public static void main(String[] args) {
        FastReader sc = new FastReader();
        PrintWriter out = new PrintWriter(new OutputStreamWriter(System.out));
        int a = sc.nextInt();
        int b = sc.nextInt();
        out.println(a + b);
        // 最后记得flush，不然会没有输出
        out.flush();
    }
}
// 下面是快读模板。需要使用时直接贴在下面就好了
class FastReader {
    //不用写构造函数，默认自带无参构造函数
    BufferedReader br=new BufferedReader(new InputStreamReader(System.in));
    StringTokenizer st;
    
    String next(){
        while (st==null||!st.hasMoreElements()){
            try {
                st=new StringTokenizer(br.readLine());
            }catch (IOException e){
                e.printStackTrace();
            }
        }
        return st.nextToken();
    }
    
    int nextInt() {
        return Integer.parseInt(next());
    }
    
    long nextLong() {
        return Long.parseLong(next());
    }
    
    double nextDouble() {
        return Double.parseDouble(next());
    }
    
    //下面两个用才加
    String nextLine() {
        String line = null;
        try {
            line = br.readLine();
        } catch (IOException e) {
            e.printStackTrace();
        }
        return line;
    }
    
    boolean hasNext() {
        while (st == null || !st.hasMoreElements()) {
            String line = nextLine();
            if (line == null) {
                return false;
            }
            st = new StringTokenizer(line);
        }
        return true;
    }
}
```

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

## 3.3. 写一个函数将 ipv4 地址字符串 (仅包含数字，点，空格) 转化成 32 位整数。另外，数字和点之间的空格是合法的，其他情况均为非法地址，要求输出合法地址的 32 位整型结果

## 3.4. 斐波那契数列 考察点：递归、非递归写法；时间复杂度计算

## 3.5. 基于 UDP 实现可靠的传输协议
提示：参考 TCP

## 3.6. 读文件
有一段从磁盘读取文件程序。详细描述从代码编写完毕，到文件读到内存中的过程。尽量给出你知道的所有细节
提示：编译、进程管理、lib 库、系统 API、文件系统、IO 操作(磁盘结构等) 等

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

#### 4.2.3.2. <a href="https://www.sspnote.com/oj/3/319">三值字符串-内推鸭</a>

```java
import java.util.*;
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int T = scanner.nextInt();
        while (T-- > 0) {
            solve(scanner);
        }
    }

    public static void solve(Scanner scanner) {
        String s = scanner.next();
        int n = s.length();
        int[] cnts = new int[3];  // 分别统计1,2,3字符的个数
        int res = n + 1;  // 初始化最小值
        for (int l = 0, r = 0; r < n; r++) {
            cnts[s.charAt(r) - '1']++;
            while (cnts[0] > 0 && cnts[1] > 0 && cnts[2] > 0) {  // 区间同时包含字符1,2,3
                res = Math.min(res, r - l + 1);
                cnts[s.charAt(l) - '1']--;
                l++;
            }
        }
        if (res == n + 1) {
            System.out.println("0");
        } else {
            System.out.println(res);
        }
    }
}
```

#### 4.2.3.3. <a href="https://www.sspnote.com/oj/3/305">K0序列-内推鸭</a>

```java
import java.util.Scanner;

public class Main {
    static final int N = (int)1e5+10;
    static int[] a = new int[N], w = new int[N];
    static int n, k;

    // 计算x转为2进制后末尾0的个数
    static int calc(int x) {
        int res = 0;
        while (x % 2 == 0) {
            res++;
            x /= 2;
        }
        return res;
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        n = in.nextInt();
        k = in.nextInt();
        for (int i = 0; i < n; i++) {
            a[i] = in.nextInt();
            w[i] = calc(a[i]);
        }
        int res = n + 1;  // 求最小长度
        for (int l = 0, r = 0, total = 0; r < n; r++) {
            total += w[r];
            while (total >= k) {
                res = Math.min(res, r - l + 1);
                total -= w[l];
                l++;
            }
        }
        if (res == n + 1) System.out.println("-1");
        else System.out.println(res);
    }
}
```
### 4.2.4. 求方案数


####  4.2.4.1. <a href="https://leetcode.cn/problems/subarray-product-less-than-k/description/">713. 乘积小于 K 的子数组 - 力扣（LeetCode）</a>

```java
// 根据右端点不同 控制生成子数组的不同
public class Solution {
    public int numSubarrayProductLessThanK(int[] nums, int k) {
        int n = nums.length, res = 0;
        //if (k <= 1) return 0;
        int total = 1;
        for (int l = 0, r = 0; r < n; r++) {
            total *= nums[r];
            while (l<=r && total >= k) {   // 当前区间不满足条件，l左移
                total /= nums[l];
                l++;
            }
            res += r - l + 1;  // [l,r]区间有r-l+1个子区间都满足题意
        }
        return res;
    }
}
```

#### 4.2.4.2. <a href="https://leetcode.cn/problems/count-subarrays-with-score-less-than-k/">2302. 统计得分小于 K 的子数组数目 - 力扣（LeetCode）</a>

```java
public class Solution {
    public long countSubarrays(int[] nums, long k) {
        long res = 0, sum = 0;
        int n = nums.length;
        for (int l = 0, r = 0; r < n; r++) {
            sum += nums[r];
            while (l<=r && sum * (r - l + 1) >= k) {  // 当前区间不满足条件,l指针右移
                sum -= nums[l];
                l++;
            }
            res += r - l + 1;
        }
        return res;
    }
}
```

#### 4.2.4.3. <a href="https://www.sspnote.com/oj/3/4">删除子数组-内推鸭</a>

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        int k = scanner.nextInt();

        // 统计a[i]的因子2的数量
        int[] a2 = new int[n];
        // 统计a[i]的因子5的数量
        int[] a5 = new int[n];

        int[] a = new int[n];
        for (int i = 0; i < n; i++) {
            a[i] = scanner.nextInt();
            // 计算每个数的因子2和因子5的数量
            while (a[i] % 2 == 0) {
                a[i] /= 2;
                a2[i]++;
            }
            while (a[i] % 5 == 0) {
                a[i] /= 5;
                a5[i]++;
            }
        }

        int cnt2 = Arrays.stream(a2).sum();  // 因子2的总数量
        int cnt5 = Arrays.stream(a5).sum();  // 因子5的总数量

        
        long ans = 0;

        // 使用滑动窗口计算满足条件的子数组数量
        for (int left = 0,right = 0; right < n; right++) {
            cnt2 -= a2[right];
            cnt5 -= a5[right];
            // 当前区间不满足条件（因子2和因子5的数量都小于k）
            while (left <= right && Math.min(cnt2, cnt5) < k) {
                cnt2 += a2[left];  // 移动左指针，增加因子2的数量
                cnt5 += a5[left];  // 移动左指针，增加因子5的数量
                left++;
            }
            ans += right - left + 1;
        }

        System.out.println(ans);
    }
}
```

# 5. 