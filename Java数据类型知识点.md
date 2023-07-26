# Java数据类型知识点

## 1. 变量

### (1). 什么是变量

- `什么是量`: 在计算机领域中, 任何信息都可以称为量
- `变量`: 信息的内容可以发生变化的, 比如说年龄, 发亮, 体重
- `程序中的变量`: int x = 12; `x是整型变量`

### (2). 为什么要使用变量

- 随着行业的发展, java程序会越来越复杂, 程序越来越多的要考虑扩展性, 如果我们还是坚持使用字面常量,
  每次更改信息都要先找到源码--更改源码--重新编译--重新运行, 使用变量可以避免这些问题

### (3). 使用变量

把变量看成一个房间, 使用变量的步骤:

1. `声明变量`: 变量类型 变量名; int x; ---> 内存中会立即开辟一个int类型大小的存储空间, 空间名叫x
2. `赋值变量`: x = 12; ---> 在x的存储空间里, 存入12这个量, `声明变量同时赋值`: int x = 12;
3. `使用变量名`: 直接使用变量名, 就相当于在操作量了
   `System.out.println(x + 2);`
   `System.out.println(x > 2);`

## 2. 常量

- `常量`: 亘古不变的信息就是常量, 比如说 一年有12个月, 一年有4个季度
- 程序中的常量
    - `字面常量`:  System.out.println("hello 10班"); `hello 10班`是字面常量
    - `符号常量`: final int x = 12; `x`是符号常量

## 3. 变量类型

java中变量类型分为:

- `基本数据类型`:
    - `整数类型`:
        - byte (1字节8位)
        - short (2字节16位)
        - int (4字节32位)
        - long (8字节64位)
        - java程序中默认整数都用int来进行存储
    - `浮点类型`:
        - float (单精度浮点4字节32位)
        - double (双精度浮点8字节64位)
    - `字符类型`:
        - char (2字节16位)
        - java程序中默认小数都用double存储
    - `布尔类型`:
        - boolean(1字节8位 true false)
- `引用数据类型`:
    - 字符串String
    - 数组
    - 类
    - 枚举

## 4. 标识符

程序中涉及到的名字都叫标识符

`变量名的命名规则`:

- 由数字, 字母, 美元符$ 组成
- 不能以数字开头
- 不能使用java关键字
- 区分大小写
- 规范: `驼峰规则` --- 组成变量名的多个单词中, 第一个单词的首字母小写, 其他单词的首字母大写

## 5. 赋值:

`String name = "值";`

`char c = 'c';` `char c = 100;`

## 6. 基本数据类型之间的转换:

- boolean 类型不参与类型转换
- Byte, short, char 都是最小类型, 三者之间不进行转换
- 由小到大 (byte short char) int long float double
- `大类型转小类型`: 需要进行强制类型转换 如:
```java

public class Demo {

    public static void main(String[] args) {
        double dou = 34.5;
        int a = (int) dou;
    }
}

  ```
- `小类型转大类型`: 自动进行转换. 如: int a = '张';
- `java程序默认整数是int类型`, 但是当整数值超出int的赋值范围, 需要显示表示long类型 `long l = 12345678900L;`
- `java程序默认小数是double类型`, 但是想让float类型进行存储, 需要显示表示float类型 `float f = (float) 23.56;`
或者 `float f = 23.56F;`

## 7. Scanner 工具类:
程序输入
```java
package com.itstudy;

import java.util.Scanner;

/**
 * 使用Scanner类
 */
public class Test03 {

  /**
   * 借助Scanner实现接受用户输入姓名, 年龄, 成绩
   * 然后将接受到的信息输出
   * @param args
   * */
  public static void main(String[] args) {
    /*
     * 创建Scanner对象, 叫input, 借组于new关键字创建的
     * */
    Scanner input = new Scanner(System.in);
    System.out.println("输入姓名");
    String name = input.next();
    System.out.println("输入年龄");
    int age = input.nextInt();
    System.out.println("输入成绩");
    double grade = input.nextDouble();
    System.out.println("输入性别");
    String sex = input.next();

    System.out.println("姓名:" + name);
    System.out.println("年龄:" + age);
    System.out.println("成绩:" + grade);
    System.out.println("性别:" + sex);
  }
}

```

## 8. 介绍字符编码: 
>java语言是Unicode编码方式. 国际通用字符集, 融合了目前人类使用的所有字符. 为每个字符分配唯一的字符码. 
Unicode编码方式是一个字符占两个字节, 但不是固定的, 比如UTF-8一个字符最小占一字节, 最大占六字节

