依托于wiki，还有dchat的`我群`来准备面试话术和资料 争取能够打印出来

周末系统学习一下Juc

<img alt="picture 5" src="images/pic_1724304399656.png" width="300" />  


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

# 1. 双指针

## 1.1. 不定长滑动窗口

### 1.1.1. 最长上升子数组
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
### 1.1.2. 子数组最大值