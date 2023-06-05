---
title: C-C Primer Plus 练习程序
categories:
  - 编程语言
  - C
tags:
  - C
date: 2023-05-30 22:45:25
---

# 第2章 C语言概述

## 第 1 题

练习 printf() 函数和转义字符

```c
#include <stdio.h>

int main(void) {
    printf("Gustav Mahler\n");
    printf("Gustav\nMahler\n");
    printf("Gustav ");
    printf("Mahler\n");

    return 0;
}
```

输出

```
Gustav Mahler
Gustav
Mahler
Gustav Mahler
```

## 第 2 题

练习 printf() 函数

```c
#include <stdio.h>

int main(void) {
    printf("My name is Gustav Mahler\n");
    printf("My address is stress no.1\n");

    return 0;
}
```

输出

```
My name is Gustav Mahler
My address is stress no.1
```

## 第 3 题

练习变量、printf() 函数、占位输出符

```c
#include <stdio.h>

int main(void) {
    int age;  // 定义变量
    age = 18;  // 给变量赋值

    printf("My age is %d, and I have lived %d days.\n", age, age * 365);

    return 0;
}
```

输出

```
My age is 18, and I have lived 6570 days.
```

## 第 4 题

练习多个函数

```c
#include <stdio.h>

// 声明函数。void 分别表示无参数、无返回值
void jolly(void);
void deny(void);

// main 函数写在开头，符合习惯
int main(void) {
    jolly();  // 调用函数
    deny();

    return 0;
}

// 定义函数
void jolly(void) {
    printf("For he's a jolly good fellow!\n");
    printf("For he's a jolly good fellow!\n");
    printf("For he's a jolly good fellow!\n");
}
// 定义函数
void deny(void) {
    printf("Which nobody can deny!\n");
}
```

输出

```
For he's a jolly good fellow!
For he's a jolly good fellow!
For he's a jolly good fellow!
Which nobody can deny!
```

## 第 5 题

练习多个函数

```c
#include <stdio.h>

// 声明函数。void 分别表示无参数、无返回值
void br(void);
void ic(void);

// main 函数写在开头，符合习惯
int main(void) {
    br();  // 调用函数
    printf(", ");
    ic();
    printf("\n");
    ic();
    printf(",\n");
    br();

    return 0;
}

// 定义函数
void br(void) {
    printf("Brazil, Russia");
}
// 定义函数
void ic(void) {
    printf("India, China");
}
```

输出

```
Brazil, Russia, India, China
India, China,
Brazil, Russia
```

## 第 6 题

练习变量和计算，占位符输出

```c
#include <stdio.h>

int main(void) {
    int toes;
    toes = 10;

    printf("toes * 2 = %d\n", toes * 2);
    printf("toes ^ 2 = %d\n", toes * toes);

    return 0;
}
```

输出

```
toes * 2 = 20
toes ^ 2 = 100
```

## 第 7 题

练习函数定义和调用

```c
#include <stdio.h>

void smile(void);

int main(void) {
    smile();
    smile();
    smile();
    printf("\n");
    smile();
    smile();
    printf("\n");
    smile();

    return 0;
}

void smile(void) {
    printf("Smile!");
}
```

输出

```
Smile!Smile!Smile!
Smile!Smile!
Smile!
```

## 第 8 题

练习函数嵌套调用

```c
#include <stdio.h>

void one_three(void);
void two(void);

int main(void) {
    printf("starting now:\n");
    one_three();
    printf("done!");

    return 0;
}

// 函数定义位置并不影响调用
void one_three(void) {
    printf("one\n");
    two();
    printf("three\n");
}
void two(void) {
    printf("two\n");
}
```

输出

```
starting now:
one
two
three
done!
```

# 第3章 数据和C

## 第 2 题

```c
#include <stdio.h>

int main(void) {
    char ch;

    printf("Please type a ascii code: ");
    scanf("%c", &ch);
    printf("char of code is %d", ch);

    return 0;
}
```

输出

```
Please type a ascii code: A
char of code is 65
```

## 第 4 题

浮点数的输入和输出

```c
#include <stdio.h>

int main(void) {
    float f;

    printf("Please type a num of float: ");
    scanf("%f", &f);
    printf("float is %f\n", f);
    printf("float e is %e\n", f);

    return 0;
}
```

输出

```
Please type a num of float: 121212.4324234
float is 121212.429688
float e is 1.212124e+05
```

## 第 5 题

浮点数运算

```c
#include <stdio.h>

int main(void) {
    float f;

    printf("Please type a num of float: ");
    scanf("%f", &f);
    printf("float is %f\n", f);
    printf("float e is %e\n", f);

    return 0;
}
```

输出

```
Please type a num of float: 121212.4324234
float is 121212.429688
float e is 1.212124e+05
```

## 第 6 题

浮点数运算

```c
#include <stdio.h>

int main(void) {
    int num;

    printf("请输入水的夸脱数：");
    scanf("%d", &num);
    printf("水分子数量为：%e\n", num * 950 / 3e-23);

    return 0;
}
```

输出

```
请输入水的夸脱数：1
水分子数量为：3.166667e+25
```

## 第 7 题

浮点数运算

```c
#include <stdio.h>

int main(void) {
    int num;

    printf("请输入水的夸脱数：");
    scanf("%d", &num);
    printf("水分子数量为：%e\n", num * 950 / 3e-23);

    return 0;
}
```

输出

```
请输入水的夸脱数：1
水分子数量为：3.166667e+25
```

