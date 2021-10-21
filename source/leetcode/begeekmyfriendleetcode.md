# begeekmyfriendleetcode

参考GitHub: 
[begeekmyfriendleetcode](https://github.com/begeekmyfriend/leetcode)

## 0001.two_sum
```sh
给定一个整数数组nums和一个
```
[两数之和](https://leetcode-cn.com/problems/two-sum/)
<details>
<summary>code</summary>

```c
#include<stdio.h>
#include<stdlib.h>

struct object {
    int val;
    int index;
};

static int compare(const void *a, const void *b)
{
    return ((struct object *) a)->val - ((struct object *) b)-val);
}

int* TwoSum(int *nums, int numsSize, int target, int *returnSize)
{
    int i, j;
    struct object *objs = malloc(numsSize * sizeof(*objs));
    for (i = 0;i < numsSize; i++) {
        objs[i].val = nums[i];
        objs[i].index = i;
    }

    qsort(objs, numsSize, sizeof(*obj), compare);

    int *results = malloc(2 * sizeof(int));

    i = 0;
    j = numsSize - 1;
    while (i < j) {
        int sum = objs[i].val + objs[j].val;
        if (sum < target) {
            i++;
        } else if (sum > target) {
            j--;
        } else {
            results[0] = objs[i].index;
            results[1] = objs[j].index;
            *returnSize = 2;
            return result;
        }
    }
    return NULL;
}

int main(void)
{

    int nums[] = {3, 2, 3};
    int size = sizeof(nums) / sizeof(*nums);
    int target = 6;
    int count = 0;
    int *indexes = TwoNum(nums, size, target, &count);
    if (indexes != NULL) {
        printf("%d %d\n", indexes[0], indexes[1]);
    } else {
        printf("Not found\n");
    }

    return 0;
}

```
</details>

## 0002.add_two_num

[2.两数相加](https://leetcode-cn.com/problems/add-two-numbers/)
<details>
<summary>code</summary>

```c
struct ListNode {
    int val;
    struct ListNode *next;
}

struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2)
{
    int carry = 0;
    struct ListNode dummy;
    struct ListNode *p = l1, *prev = &dummy;

    dummy.next = p;
    while (l1 != NULL || l2 != NULL) {
        int sum = 0;

        if (l1 != NULL) {
            sum += l1->val;
            l1 = l1->next;
        }

        if (l2 != NULL) {
            if (p == NULL) {
                prev->next = l2;
                p = l2;
            }
            sum += l2->val;
            l2 = l2->next;
        }

        sum += carry;
        carry = sum / 10;
        p->val = sum % 10;
        prev = p;
        p = p->next;
    }

    if (carry) {
        p = malloc(sizeof(*p));
        p->val = carry;
        p->next = NULL;
        prev->next = p;
    }

    return dummy.next;
}

```
</details>

## 0003.无重复字符的最长子串

[无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)

<details>
<summary>code</summary>

```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int lengthOfLongestSubstring(char *s)
{
    int offset[128];
    int max_len = 0;
    int len = 0;
    int index = 0;

    memset(offset, 0xff, sizeof(offset));
    while (*s != '\0') {
        if (offset[*s] == -1) {
            len++;
        } else {
            if (index - offset[*s] > len) {
                len++;
            } else {
                len = index - offset[*s];
            }
        }
        if (len > max_len) {
            max_len = len;
        }
        offset[*s++] = index++;
    }

    return max_len;
}

```
</details>