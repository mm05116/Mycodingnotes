#统计好三元组
#思路：三元数组每个位置的数字都有位置大写的要求，所以写三个嵌套循环对输入的数组进行遍历，再对其进行储存，在最内层的循环中进行条件判断，如果满足就让三元组数量加一。
#代码实现：
int countGoodTriplets(int* arr, int arrSize, int a, int b, int c) {
    int ans = 0;
    for(int i = 0; i < arrSize; ++i) {
        for(int j = i +1; j < arrSize; ++j) {
            for(int k = j + 1; k < arrSize; ++k) {
                if (abs(arr[i] - arr[j]) <= a && abs(arr[j] - arr[k]) <= b && abs(arr[i] - arr[k]) <= c) {
                    ++ans;
                }
            }
        }
    }
    return ans;
}

#转换为小写字母
#思路：写一个循环遍历整个数组，在循环内对数值的ascii码值进行判断，因为A到a的ascii码值数值大小差了32，所以对每个遍历到的数加32，便可将大写转换为小写。
#代码实现：
char* toLowerCase(char* s) {
    int len = strlen(s);
    int i;
    for(i = 0; i < len; i++) {
       if (s[i] >= 65 && s[i] <= 90) {
        s[i] |= 32;
       }
    }
    return s;
}

Summary:今天接触了abs函数：用来取运算绝对值；strlen函数：用来取数组长度，我记得好像在数据结构里学过；对于第二个代码中，字符本质上就是整数，char类型在底层储存的就是该字符对应的ascii码值。
