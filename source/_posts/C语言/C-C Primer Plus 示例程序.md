---
title: C-C Primer Plus 示例程序
categories:
  - 编程语言
  - C
tags:
  - C
date: 2023-05-27 12:35:41
---

# 第2章 C语言概述

## first.c

```c
// 示例程序
#include <stdio.h>

int main(void) {
    int num;  // 定义变量
    num = 1;  // 给变量赋值

    printf("I am a simple ");  // 调用函数，输出字符串
    printf("computer.\n");  // 输出占位符
    printf("My favorite number is %d because it is first. \n", num);  // 占位符输出 

    return 0;  // 返回值
}
```

输出：

```
I am a simple computer.
My favorite number is 1 because it is first. 
```



## fathm_ft.c

单位转换

```c
#include <stdio.h>

int main(void) {
    int feet, fathoms;
    fathoms = 2;
    feet = 6 * fathoms;

    printf("There ara %d feet in %d fathoms!\n", feet, fathoms);
    printf("Yes, I said %d feet!\n", 6 * fathoms);  // 待打印值可以是表达式

    return 0;
}
```

输出：

```
There ara 12 feet in 2 fathoms!
Yes, I said 12 feet!
```



## tow_func.c

包含多个函数

```c
#include <stdio.h>

void butler(void); // 声明函数原型，告知编译器要使用该函数

int main(void) {
    printf("I will summon the butler function.\n");
    butler();
    printf("Yes. Bring me some tea and writeable DVDs. \n");

    return 0;
}

// 开始定义函数
void butler(void) {
    printf("You rang, sir?\n");
}
```

输出：

```
I will summon the butler function.
You rang, sir?
Yes. Bring me some tea and writeable DVDs. 
```

# 第3章 数据和C

## platium.c

`scanf()` 函数引入，读取程序输入

```c
#include <stdio.h>

int main(void) {
    float weight;
    float value;

    printf("Are you worth your weight in platinum?\n");
    printf("Let's check it out.\n");
    printf("Please enter your weight in pounds: ");

    scanf("%f", &weight);
    value = 1700.0 * weight * 14.5833;
    printf("Your weight in platinum is worth $%.2f.\n", value);
    printf("You are easily worth that! If platinum prices drop,\n");
    printf("eat more to maintain your value.\n");

    return 0;
}
```

## printl.c

占位符不够会输出内存值

```c
#include <stdio.h>

int main(void) {
    int ten = 10;
    int two = 2;

    printf("Doing it right: ");
    printf("%d minus %d is %d\n", ten, 2, ten - two);
    printf("Doing it wrong: ");
    printf("%d minus %d is %d\n", ten);  // 遗漏 2 个参数，输出内存值（随机）

    return 0;
}
```

输出

```
Doing it right: 10 minus 2 is 8
Doing it wrong: 10 minus 0 is 52232400
```

## bases.c

不同进制的显示

```c
#include <stdio.h>

int main(void) {
    int x = 100;

    printf("dec = %d; octal = %o; hex = %x\n", x, x, x);
    printf("dec = %d; octal = %#o; hex = %#x\n", x, x, x);

    return 0;
}
```

输出

```
dec = 100; octal = 144; hex = 64
dec = 100; octal = 0144; hex = 0x64
```

## 3.5 charcode.c

char 类型的打印

```c
#include <stdio.h>

int main(void) {
    char ch;

    printf("Please enter a character.\n");
    scanf("%c", &ch);
    // 占位符决定了变量的显示形式，而不是存储方式
    printf("The code for %c is %d.\n", ch, ch);

    return 0;
}
```

输出

```
Please enter a character.
a
The code for a is 97.
```

## 3.8 typesize.c

sizeof() 函数可以打印类型大小

```c
#include <stdio.h>

int main(void) {
    printf("Type char has a size of %zd bytes.\n", sizeof(char));
    printf("Type short has a size of %zd bytes.\n", sizeof(short));
    printf("Type int has a size of %zd bytes.\n", sizeof(int));
    printf("Type long has a size of %zd bytes.\n", sizeof(long));
    printf("Type long long has a size of %zd bytes.\n", sizeof(long long));
    printf("Type _Bool long has a size of %zd bytes.\n", sizeof(_Bool));
    printf("Type float long has a size of %zd bytes.\n", sizeof(float));
    printf("Type double long has a size of %zd bytes.\n", sizeof(double));
    printf("Type long double long has a size of %zd bytes.\n", sizeof(long double));

    return 0;
}
```

输出

```
Type char has a size of 1 bytes.
Type short has a size of 2 bytes.
Type int has a size of 4 bytes.
Type long has a size of 8 bytes.
Type long long has a size of 8 bytes.
Type _Bool long has a size of 1 bytes.
Type float long has a size of 4 bytes.
Type double long has a size of 8 bytes.
Type long double long has a size of 16 bytes.
```

# 第4章 字符串和格式化输入/输出

## 4.1 talkback.c

字符串输入和输出

```c
#include <stdio.h>
#include <string.h>  // 提供 strlen() 函数原型
#define DENSITY 62.4f  // 定义常量

int main(void) {
    float weight, volume;
    int size, letters;
    char name[40];  // 定义数组

    printf("Hi! What's your first name?\n");
    scanf("%s", name);
    printf("%s, what's your weight in pounds?\n", name);
    scanf("%f", &weight);
    size = sizeof name;
    letters = strlen(name);
    volume = weight/DENSITY;
    printf("Well, %s, your volume is %2.2f cubic feet.\n",
           name, volume);
    printf("Also, your first name has %d letters, \n", letters);
    printf("and we have %d bytes to store it.\n", size);

    return 0;
}
```

输出

```
Hi! What's your first name?
Christine
Christine, what's your weight in pounds?
154
Well, Christine, your volume is 2.47 cubic feet.
Also, your first name has 9 letters, 
and we have 40 bytes to store it.
```

## 4.3 praise2.c

验证字符串占用

```c
#include <stdio.h>
#include <string.h>  // 提供 strlen() 函数原型
#define PRAISE "You are an extraordinary being."  // 自动计算大小

int main(void) {
    char name[40];

    printf("What's your name? ");
    scanf("%s", name);
    printf("Hello, %s. %s\n", name, PRAISE);
    printf("Your name of %zd letters occupies %zd memory cells.\n", 
           strlen(name), sizeof(name));
    printf("The phrase of praise has %zd letters ", strlen(PRAISE));
    printf("and occupies %zd memory cells.\n", sizeof(PRAISE));

    return 0;
}
```

输出

```
What's your name? Serendipity Chance
Hello, Serendipity. You are an extraordinary being.
Your name of 11 letters occupies 40 memory cells.
The phrase of praise has 31 letters and occupies 32 memory cells.
```

## 4.7 width.c

输出修饰符

```c
#include <stdio.h>
#define PAGES 959

int main(void) {
    printf("*%d*\n", PAGES);
    printf("*%2d*\n", PAGES);
    printf("*%10d*\n", PAGES);
    printf("*%010d*\n", PAGES);
    printf("*%-10d*\n", PAGES);
    printf("*%+10d*\n", PAGES);

    return 0;
}
```

输出

```
*959*
*959*
*       959*
*0000000959*
*959       *
*      +959*
```

## 4.8 floats.c

输出修饰符

```c
#include <stdio.h>
#define PAGES 959

int main(void) {
    printf("*%d*\n", PAGES);
    printf("*%2d*\n", PAGES);
    printf("*%10d*\n", PAGES);
    printf("*%010d*\n", PAGES);
    printf("*%-10d*\n", PAGES);
    printf("*%+10d*\n", PAGES);

    return 0;
}
```

输出

```
*959*
*959*
*       959*
*0000000959*
*959       *
*      +959*
```

