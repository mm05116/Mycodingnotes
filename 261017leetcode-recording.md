#最小偶倍数
#思路：奇数和2的最小公倍数是它自身*2，偶数和2的最小公倍数是它自身。所以就先判断所给的数是奇数还是偶数，用2取余，为0为偶数，返回它自身，不是0为奇数，返回它自身乘2.
#代码实现：
int smallestEvenMultiple(int n) {
    return n % 2 == 0 ? n : 2 * n;
}

#数组异或操作
#思路：需要定义一个int型变量用于储存返回的异或值，再用一个for循环遍历整个数组，并且在循环中对数组中的元素进行异或操作。
#代码实现：
int xorOperation(int n, int start) {
    int ans = 0;
    for (int i = 0; i < n; ++i){
        ans ^= (start + i * 2);
    }
    return ans;
}

#好数对的数目
#思路：先定义一个int型变量ans用于储存最终好数对的总数，cnt数组用于记录每个数字出现的次数，用一个for循环遍历数组，将数组中的数字记录在x里，若前面并没有出现和x一样的数字，则ans+0，但cnt变为1；若前面出现了一次和x一样的数字，则ans+1，且cnt变为前面出现的次数+1；若前面出现了两次和x一样的数字，则ans+2（它可以和前面两个都分别组成好数对）cnt+1
#代码实现：
int numIdenticalPairs(int* nums, int numsSize) {
    int ans = 0;
    int cnt[101] = {};
    for(int i = 0; i < numsSize; i++) {
        int x = nums[i];
        ans += cnt[x];
        cnt[x]++;
    }
    return ans;
    
Summary：三元运算符：条件？真值：假值，先判断条件，为真输出真值，为假输出假值；取余操作；异或运算符：^=；好数对的思路特别重要，一个用于储存出现次数，另一个用于储存好数对的数目，要找准他们之间的关系才能写出这个代码。
