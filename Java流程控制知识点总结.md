# Java流程控制知识点总结

<!-- TOC -->

* [一. 流程控制语句:](#一-流程控制语句)
* [二. 选择结构](#二-选择结构)
    * [1. if选择结构](#1-if选择结构)
        * [(1). 单分支选择结构](#1-单分支选择结构)
        * [(2). 双分支选择结构](#2-双分支选择结构)
        * [(3). 多分支选择结构](#3-多分支选择结构)
        * [(4). 嵌套选择结构](#4-嵌套选择结构)
    * [2. switch 选择结构](#2-switch-选择结构)

<!-- TOC -->

## 一. 流程控制语句:

- `顺序结构` (从上到下, 从左到右, `逐行执行`)
- `选择结构` (根据表达式的判断结果, 有选择性的选择某一部分代码执行)
- `循环结构` (根据表达式的判断结果, 判断某一部分代码, 是否进行多次重复执行)

## 二. 选择结构

### 1. if选择结构

#### (1). 单分支选择结构

```
if (表达式) {
    //结构体
}
```

- 表达式为true, 执行结构体里的内容, false不执行
- 表达式可以有赋值语句, 但仅限boolean类型的变量
- 省略大括号后, 默认第一行完整结构的代码是属于结构体里的, 其他代码都是结构体以外,
  不推荐省略选择结构里的大括号

```java
public class Demo {
    public static void main(String[] args) {
        if (boo = false)
            System.out.println("表达式成立");
        System.out.println("boo = false");
        System.out.println("程序结束");
    }
}
```

#### (2). 双分支选择结构

```
if (表达式) {
    //结构体1
} else {
        //结构体2
    }
```

- 条件表达式为真, 执行结构体1; 条件表达四为假, 执行结构体2
- 无论表达式结构体如何, 一定会执行其中一个结构体

#### (3). 多分支选择结构

```
if (表达式) {
    //结构体1
} else if (表达式) {
        //结构体2
    } else {
            //结构体3
        }
```

- 多分支选择结构, 即便有多个条件成立, 也一定是从上到下第一个为真的表达式, 执行对应的结构体.
  结构体执行完, 当前多分支选择结构也立刻结束, 继续执行结构后面的代码
- 以else结尾的多分支选择结构, 一定会执行其中一个结构体
- 一个多分支选择结构 和 多个单分支选择结构的区别
    - 一个以else结尾的多分支结构程序执行时, 一定会执行其中的一个结构体
    - 不以else结尾的多分支结构程序执行时, 有可能执行一个结构体, 有可能一个结构体都不执行
    - 多个单分支选择结构, 有可能一个结构体都不执行, 有可能所有结构体都执行

#### (4). 嵌套选择结构

```
if (表达式) {
    if (表达式) {
            //结构体1
        }
    //结构体2
} else {
        if (表达式) {
            //结构体3
        }
        //结构体4
    }
```

```java
public class Demo {
    public static void main(String[] args) {
        /*举行运动会100米赛跑, 跑入12秒内的都进入决赛, 然后分为男女子组*/
        Scanner input = new Scanner(System.in);
        System.out.println("请输入成绩: XXX秒");
        int score = input.nextInt();
        if (score <= 12) {
            System.out.println("请输入你的性别: ");
            String sex = input.next();
            if (sex.equals("男")) {
                System.out.println("决赛进入男子组");
            } else {
                System.out.println("决赛进入女子组");
            }
        } else {
            System.out.println("感谢参与!");
        }
    }
}
```

### 2. switch 选择结构

(1). if选择结构 与 switch选择结构的区别?

- if更擅长处理区间问题; switch更擅长处理等值问题.

```java
public class Demo {
    public static void main(String[] args) {
        /*random [0.0, 1.0)*/
        double random = Math.random() * 10;
        int i = (int) random;
        System.out.println(i);

        switch (i) {
            case 1:
            case 2:
            case 3: {
                System.out.println("条件1成立");
                break;
            }
            case 4:
            case 5:
            case 6: {
                System.out.println("条件2成立");
                break;
            }
            case 7:
            case 8:
            case 9: {
                System.out.println("条件3成立");
                break;
            }
            default: {
                System.out.println("无条件成立");
            }
        }
    }
}
```

`例题: 判断每月有多少天`

```java
public class Test02 {
    public static void main(String[] args) {

        System.out.println("输入月份: ");
        int month = new Scanner(System.in).nextInt();
        System.out.println("输入年份: ");
        int year = new Scanner(System.in).nextInt();
        switch (month) {
            case 1:
            case 3:
            case 5:
            case 7:
            case 8:
            case 10:
            case 12: {
                System.out.println(month + "月有31天");
                break;
            }
            case 4:
            case 6:
            case 9:
            case 11: {
                System.out.println(month + "月有30天");
                break;
            }
            case 2: {
                if (year % 4 == 0 && year % 100 != 0 || year % 400 == 0) {
                    System.out.println(month + "月有29天");
                } else {
                    System.out.println(month + "月有28天");
                }
                break;
            }
            default: {
                System.out.println("输入非法");
            }
        }
    }
}
```
