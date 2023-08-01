# Java面向对象知识点总结
## 一. 面向过程和面向对象的区别
1. `面向过程关注的是解决问题的每一个实施步骤`
2. `面向对象关注的是谁有能力来解决该问题`

面向过程 ---> 面向对象; 其实就是有执行者 ---> 指挥者的一个过渡,
`二者相辅相成, 并不是对立的,` 宏观上通过面向对象缕清复杂关系;微观上通过面向过程来进行操作处理

## 二. 面向对象的三个阶段
### 1. 面向对象分析 Object Oriented Analysis
- 从当前系统/题目中找出所有参与的对象
- 分析这些对象共有的静态特征和动态特征
### 2. 面向对象设计 Object Oriented Design
- 将所有参与的对象提取成一类, 确定类名
- 确定保留哪些静态特征和动态特征, 然后为其命名
### 3. 面向对象编程 Object Oriented Programming

## 三. 面向对象编程, 关注的就是 类和对象
### 1. 什么是类?
- 具有`相同属性`和`共同行为`的`一组对象的集合`, 就叫类
- 补充: `共同行为`的`几组对象的集合` 叫接口
### 2. 什么是对象?
真实存在的, 万事万物都可以是对象
## 四. 创建类和创建对象
- 找到参与者, 提取出类, 设置类名: `Person`
- 找出参与者相同的属性和共同行为, 为属性和行为命名: `name`, `eat`, `study`

```java
package com.itstudy;
/**
 * 根据张三李四两个参与提取出的类Person
 * */
public class Person() {
    /*相同属性*/
    private String name;
    
    public Person() {
        
    }
    public Person(String name) {
        this.name = name;
    }
    /*共同行为*/
    public void eat() {
        System.out.println(name + "在吃饭");
    }

    public void study() {
        System.out.println(name + "在学习");
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}

public class Test() {
    public static void main(String[] args) {
        Person person = new Person("李四");
        person.eat();
        person.study();
    }
}

```
