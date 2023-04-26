---
title: 工厂模式 Factory
author: Hubert
date: 2023-02-15
category: .NET
layout: post
---

### 1.简单工厂

* Test

~~~C#
    /// <summary>
    /// 顾客充当客户端，负责调用简单工厂来生产对象
    /// 即客户点菜，厨师（相当于简单工厂）负责烧菜(生产的对象)
    /// </summary>
    class Customer
    {
        static void Main(string[] args)
        {
            // 客户想点一个西红柿炒蛋        
            Food food1 = FoodSimpleFactory.CreateFood("西红柿炒蛋");
            food1.Print();
            // 客户想点一个土豆肉丝
            Food food2 = FoodSimpleFactory.CreateFood("土豆肉丝");
            food2.Print();
            Console.Read();
        }
    }

    /// <summary>
    /// 菜抽象类
    /// </summary>
    public abstract class Food
    {
        // 输出点了什么菜
        public abstract void Print();
    }

    /// <summary>
    /// 西红柿炒鸡蛋这道菜
    /// </summary>
    public class TomatoScrambledEggs : Food
    {
        public override void Print()
        {
            Console.WriteLine("一份西红柿炒蛋！");
        }
    }

    /// <summary>
    /// 土豆肉丝这道菜
    /// </summary>
    public class ShreddedPorkWithPotatoes : Food
    {
        public override void Print()
        {
            Console.WriteLine("一份土豆肉丝");
        }
    }

    /// <summary>
    /// 简单工厂类, 负责 炒菜
    /// </summary>
    public class FoodSimpleFactory
    {
        public static Food CreateFood(string type)
        {
            Food food = null;
            if (type.Equals("土豆肉丝"))
            {
                food= new ShreddedPorkWithPotatoes();
            }
            else if (type.Equals("西红柿炒蛋"))
            {
                food= new TomatoScrambledEggs();
            }

            return food;
        }
    }
~~~

> * 优点：解决了客户端直接依赖于具体对象的问题、代码复用
> * 缺点：工厂类集中了所有产品创建逻辑，一旦不能正常工作，整个系统都会受到影响（通俗地意思就是：一旦餐馆没饭或者关门了，很多不愿意做饭的人就没饭吃了）
> * 缺点：系统扩展困难，一旦添加新产品就不得不修改工厂逻辑，这样就会造成工厂逻辑过于复杂。

---

### 2.工厂方法模式

一 对象抽象类 \
一 工厂抽象类 \
一 对象类 : 对象抽象类 \
一 对象工厂类 : 工厂抽象类

~~~ C#

 /// <summary>
/// 1.报告单抽象类
/// </summary>
public abstract class AbstractReport
{
    /// <summary>
    /// 打印报告单
    /// </summary>
    public abstract void Print();
}

/// <summary>
/// 2.抽象工厂类
/// </summary>
public abstract class AbstractReportFactory
{
    /// <summary>
    /// 工厂方法
    /// </summary>
    /// <returns></returns>
    public abstract AbstractReport CreateReportFactory(); 
}

---

/// <summary>
/// 3.输血申请单
/// </summary>
public class BloodRequestReport:AbstractReport
{
    /// <summary>
    /// 打印报告单-输血申请报告单
    /// </summary>
    public override void Print()
    {
        Console.WriteLine("输血申请报告单");

    }
}

/// <summary>
/// 4.输血申请单工厂
/// </summary>
public class BloodRequestReportFactory: AbstractReportFactory
{
    /// <summary>
    /// 工厂方法
    /// </summary>
    /// <returns></returns>
    public override AbstractReport CreateReportFactory()
    {
        return new BloodRequestReport();
    }
}

~~~
