# shiyan4
模拟学生作业处理

## 实验目的

掌握字符串String及其方法的使用
掌握文件的读取/写入方法
掌握异常处理结构

## 实验要求

1.设计学生类（可利用之前的）；
2.采用交互式方式实例化某学生；
3.设计程序完成上述的业务逻辑处理，并且把“古诗处理后的输出”结果存储到学生基本信息所在的文本文件A中。

## 实验过程

首先创建主类，并在其下创建三个类，分别为student学生类，homework作业内容类和handle处理类。

在student类中，我基本上沿用了上一次实验中的一部分内容，包括在其中创建变量和用this进行内容的调用。

在homework类中，实现的是在每7个汉字中加标点和换行，这部分通过用for方法进行循环实现。

在handle类中，实现的是文本内容读取和处理。用File file以及FileReader读取并将内容存入一个字符串中（此部分用了预处理，将内容写在try方法下，用catch和e.printStackTrace捕获异常）。用getCharMaps方法实现搜索特定字符并计录出现数量，在其中定义变量w，用作计数。用for方法实现对字符串中内容的遍历，并用if方法判定读取内容与输入内容是否相同，如相同则w=w+1，实现计数功能。

最后完善主类内容，完成对其他类的调用，与数据的输出。

## 核心代码

```
public class shiyan4 {
    public static void main(String args[]) {
        Scanner input = new Scanner(System.in);
        int w;
        StringBuffer str2 = null;
        Handle hkls = new Handle();
        StringBuffer str1 = hkls.Read();
        Homework one = new Homework();
        str2 = one.HW(str1);
        Handle.Write(str2);

        System.out.println("请输入要查询的字符：");
        String z = input.next();
        w = hkls.getCharMaps(z,str1);

        System.out.println("学生信息：");
        Student hkl = new Student();
        hkl.setName("胡凯莉");
        hkl.setAge(20);
        hkl.setNumber(2019310000);
        hkl.setSex("男");
        System.out.println("学生姓名:" + hkl.getName());
        System.out.println("学生年龄:" + hkl.getAge());
        System.out.println("学生编号:" + hkl.getNumber());
        System.out.println("学生性别:" + hkl.getSex());

        System.out.println("处理完成");
        System.out.println(z + "出现了"+ z + "次");
    }
}
```

## 运行结果
汉皇重色思倾国，御宇多年求不得。
杨家有女初长成，养在深闺人未识。
天生丽质难自弃，一朝选在君王侧。
回眸一笑百媚生，六宫粉黛无颜色。
春寒赐浴华清池，温泉水滑洗凝脂。
侍儿扶起娇无力，始是新承恩泽时。
云鬓花颜金步摇，芙蓉帐暖度春宵。
春宵苦短日高起，从此君王不早朝。
承欢侍宴无闲暇，春从春游夜专夜。
后宫佳丽三千人，三千宠爱在一身。
金屋妆成娇侍夜，玉楼宴罢醉和春。
姊妹弟兄皆列士，可怜光采生门户。
遂令天下父母心，不重生男重生女。
骊宫高处入青云，仙乐风飘处处闻。
缓歌慢舞凝丝竹，尽日君王看不足。
渔阳鼙鼓动地来，惊破霓裳羽衣曲。
九重城阙烟尘生，千乘万骑西南行。
<未完，待续>，
请输入要查询的字符：
男
学生信息：
学生姓名:胡凯莉
学生年龄:20
学生编号:2019310000
学生性别:男
处理完成
男出现的次数为：1次
## 实验感想

通过这次实验我进一步掌握了掌握字符串String及其方法的使用、文件的读取和写入方法，掌握了异常处理结构，并用预处理处理了实验中的问题，最后通过不断修改完成了实验内容。提交后我会再根据不足和以后对代码的理解再加深之后再对程序进行修改和完善。
