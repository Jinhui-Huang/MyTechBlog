# Java数组知识点总结

<!-- TOC -->

* [一. 引入数组](#一-引入数组)
    * [1. 为什么需要数组](#1-为什么需要数组)
    * [2. 什么是数组](#2-什么是数组)
        * [扩展: 数组和基本数据类型的区别](#扩展-数组和基本数据类型的区别)
    * [3. 怎么使用数组](#3-怎么使用数组)
        * [(1). 数组](#1-数组)
        * [(2). 变量](#2-变量)
* [二. 总结数组](#二-总结数组)
* [三. 数组内存分析:](#三-数组内存分析)
* [四. 数组例题分析](#四-数组例题分析)
    * [(1). 数组求最值](#1-数组求最值)
    * [(2). 查找数组内容位置](#2-查找数组内容位置)
    * [(3). 数组添加数据](#3-数组添加数据)
* [五. Main方法详解](#五-main方法详解)
* [六. 可变参数](#六-可变参数)
* [七. Arrays工具类](#七-arrays工具类)
* [八. 二维数组](#八-二维数组)
    * [(1). 使用二维数组:](#1-使用二维数组)

<!-- TOC -->

## 一. 引入数组

### 1. 为什么需要数组

- 没有数组之前, 我们需要`创建大量的变量`来存储数据信息;
  有数组之后, 我们只需要`创建一个数组`就可以存储多个数据信息, 节省数据存储空间
- 大量数据使用数组, 操作方便!

### 2. 什么是数组

`数组是引用数据类型, 是一种容器.`

#### 扩展: 数组和基本数据类型的区别

### 3. 怎么使用数组

`数组(4个步骤)`  vs  `基本数据类型(3个步骤)`

#### (1). 数组

- 声明数组: `数组类型[] 数组名` -> `int[] ages;`
- 分配空间: `数组名 = new 数组类型[空间长度]` -> `ages = new int[500];`

  合并写法: `声明数组[] 数组名 = new 数组类型[空间长度]` -> `int[] ages = new int[500];`

- 赋值数组元素:
    1. 静态赋值:
        1. 单个元素赋值: `数组名[下标] = 值;` -> `age[0] = 60;` **数组下标从0开始**
        2. 所有元素赋值: 1 + 2 + 3步骤的赋值!
            - [方式一] `int[] ages = {45, 68, 90, 26, 32}`
            - [方式二] `int[] ages = new int[]{45, 68, 90, 26, 32}`
    2. 动态赋值:
       ```java
       public class Demo {
          public static void arrayMethod() {
          /*控制台接受5个成绩, 全部接收完, 再将5个成绩输出出去*/
          int[] ages = new int[5]; //声明同时分配空间
          Scanner input = new Scanner(System.in);
          for (int i = 0; i < 5; i++) {
              System.out.println("输入第" + (i + 1) + "个");
              ages[i] = input.nextInt();
          }
          System.out.println("=======================");
          for (int i = 0; i < ages.length; i++) {
              System.out.print("第" + (i + 1) + "个学生成绩为: ");
              System.out.println(ages[i]);
           }
        }
       }
       ```
    3. 数组默认值:
        1. `int short byte long `-> `默认值0`
        2. `double float` -> `默认值0.0`
        3. `boolean` -> `默认值false`
        4. `char` -> `\u0000`
- 操作数组
    - sout(`数组名[下标] 数组名[下标] + 数组名[下标] 数组[下标] > 数组[下标]`)
    - 数组的每一个操作都离不开循环

#### (2). 变量

- 声明变量: `变量类型 变量名` -> `int age;`
- 使用变量: `变量名 = 值` -> `age = 10`;

## 二. 总结数组

- 数组的空间长度是固定的, 数组一旦被创建, 数组的长度是不可以改变的
- 数组必须存储同一类型元素, 任何变量类型都可以
- 数组下标索引的取值范围[0, 空间长度 - 1],

  `空间长度=array.length - 1`

  小心: `ArrayIndexOutOfBoundsException:`

## 三. 数组内存分析:

- 内存空间分为5块:
    - `代码区` (虚拟机里的类加载器, 会将物理位置下的字节码文件里的代码段, 加载到内存的代码区里)
    - `常量池` ("字面常量", "符号常量", "静态变量") --- `常量池里的数据不允许出现冗余(不能有重复数据)`
    - `栈` (局部 基本数据类型; 引用数据类型的地址) --- 栈里又分很多个方法区, 一个方法执行完, 对应的方法区立刻销毁.
      到目前位置学到的变量`全是局部变量` (`方法里声明的变量就是局部变量`)
    - `堆`: 引用数据类型. ---不再使用的时候, 交给垃圾回收机制

## 四. 数组例题分析

#### (1). 数组求最值

```java
public class Demo {
    private static void getMax() {
        int[] nums = {23, 9, 45, 93, 6, 72, 55, 2, 78};
        /*暂定一个最大值, 就是数组的第一个元素, 一定不要额外带入其他数进入数组比较*/
        /*int max = nums[0];*/
        for (int i = 0; i < nums.length; i++) {
            for (int j = i; j < nums.length; j++) {
                if (nums[j] < nums[i]) {
                    int temp = nums[i];
                    nums[i] = nums[j];
                    nums[j] = temp;
                }
            }

        }
        System.out.println(Arrays.toString(nums));
        System.out.println("最大数为: " + nums[nums.length - 1]);
    }
}
```

### (2). 查找数组内容位置

```java
public class Demo {
    private static void findIndex() {
        int[] nums = {23, 9, 45, 93, 6, 72, 55, 2, 78};
        System.out.println("输入你要查找的数: ");
        Scanner input = new Scanner(System.in);
        int num = input.nextInt();
        for (int i = 0; i < nums.length; i++) {
            if (num == nums[i]) {
                System.out.println("存在!下标是: " + i);
                return;
            }
        }
        System.out.println("不存在该数");
    }
}
```

### (3). 数组添加数据

```java
public class Demo {
    private static void addNum02() {
        int oldCapacity = 10;
        int newCapacity;
        int size = 0;
        int[] nums = new int[oldCapacity];

        /*控制台接收一个数, 同时再接收插入的下标位置*/
        Scanner input = new Scanner(System.in);
        System.out.println("请输入一个数字添加(0结束): ");
        while (true) {
            int num = input.nextInt();
            if (num == 0) {
                break;
            } else if (nums[oldCapacity - 1] != 0) {
                newCapacity = (int) (oldCapacity * 1.5);
                oldCapacity = newCapacity;
                int[] newNums = new int[oldCapacity];
                for (int i = 0; i < nums.length; i++) {
                    newNums[i] = nums[i];
                }
                nums = newNums;
            }
            nums[size] = num;
            size++;
            System.out.println("请输入一个数字添加(0结束): ");
        }
        StringJoiner sj = new StringJoiner(", ", "[", "]");
        for (int i = 0; i < size; i++) {
            sj.add(String.valueOf(nums[i]));
        }
        System.out.println(sj);
    }
}
```

## 五. Main方法详解

Main方法注意事项:

- `Main方法是特殊的方法`
- `public static void main(String[] args){}` 必须是这个格式
- main方法可不可以有重载方法吗?
    - 可以有, 但是其他的重载方法, 被视为`普通方法`
    - 有重载方法后, 程序就有多个入口了吗? --- 不是, `还是仍然只有一个入口`
- 参数: `字符串类型的数组`
    - 作用: 程序运行时, 可以临时, 动态的传递一个信息变量进入

## 六. 可变参数

- 指的是参数的数量不确定，可以变化
- 1.可变参数：作用提供了一个方法，参数的个数是可变的 ,解决了部分方法的重载参数过多的问题

```
  int...num
  double...num
  boolean...num
```

- 2.可变参数在JDK1.5之后加入的新特性
- 3.方法的内部对可变参数的处理跟数组是一样
- 4.可变参数和其他数据一起作为形参的时候，可变参数一定要放在最后
- 5.我们自己在写代码的时候，建议不要使用可变参数。

## 七. Arrays工具类

- 作用: 帮助我们更方便的操作数组
  Arrays工具类的常用方法
  参考JDK文档

## 八. 二维数组

- 一维数组: 元素是一个普通变量, 通过一个下标就可以锁定一个元素
- 二维数组: 元素是一个数组, 两个下标才能锁定一个具体的元素

#### (1). 使用二维数组:

- 声明二维数组: `int[][] arr;`
- 为二维数组分配空间: `arr = new int[3][4];`, 第二个中括号可以不指定具体数值, 但是第一个中括号`必须指定具体数值`
- 声明空间同时分配空间: `int[][] arr02 = new int[3][]`
- 赋值:
    - `arr[0] = new int[]{1, 2, 3, 4};`
    - `int[] nums = {1, 2, 3, 4};` `arr[1] = nums;`
- 声明分配空间同时赋值:
    - `int[][] arr03 = {{11, 22, 33}, {9, 8, 7, 6}, {10, 20}}`
- 使用二维数组

```java
public class Demo() {
    public static void main(String[] args) {
        int[][] arr03 = {{11, 22, 33}, {9, 8, 7, 6}, {10, 20}};
        for (int i = 0; i < arr03.length; i++) {
            for (int j = 0; j < arr03[i].length; j++) {
                System.out.println(arr03[i][j]);
            }
        }
    }
}
```