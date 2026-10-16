#两整数相加
#思路：相当于是定义了一个sum函数，再在函数里先定义一个a用来储存相加的值，因为函数名不能直接当作变量来赋值，最后函数的结果是返回这个a的值，因为它定义是一个int型的函数
#代码实现：
int sum(int num1, int num2) {
    int a;
     a = num1 + num2;
     return a;
}

#温度转换
#思路：用malloc向系统申请了sizeof(double)*2这块大小的内存，(double*)强制将返回的指针转换为double*类型，double*res声明一个double类型的指针res来接受这个内存地址；*returnSize = 2; 是通过解引用指针，将数组的长度（2）写入到系统提供的内存地址中。
#代码实现：
double* convertTemperature(double celsius, int* returnSize) {
    double *res = (double *)malloc(sizeof(double) * 2);
    res[0] = celsius + 273.15;
    res[1] = celsius * 1.80 + 32.00;
    *returnSize = 2;
    return res;
}

Summary:第一次用这种编程算法网站，一点不熟悉编程界面，万事开头难，加油。下来还是得看C语言的内容，leetcode一点刷不动，今日重点：数组、指针、malloc函数
