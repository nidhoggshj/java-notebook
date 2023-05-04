# 韩顺平java基础篇 第5章——第13章

## 第 5 章 程序控制结构

### 5.1 程序流程控制介绍

![img](https://img-blog.csdnimg.cn/img_convert/28634e0d0f7830c50204efba91b0bdc7.png)

### 5.2 顺序控制

![img](https://img-blog.csdnimg.cn/img_convert/d27475e7f026ceab129a4f60a7a12597.png)

### 5.3 分支控制 if-else

#### 5.3.1 分支控制 if-else 介绍

![img](https://img-blog.csdnimg.cn/img_convert/b2c49041fca61ae5cfb28fecf1cde2e0.png)

#### 5.3.2单分支

![img](https://img-blog.csdnimg.cn/img_convert/88880289dae8cd494a098caaa1144424.png)

### 5.4 分支

#### 5.4.1 双分支

![img](https://img-blog.csdnimg.cn/img_convert/a5c06ba147155d42bd5f0ab6cb953f4a.png)

#### 5.4.4 多分支

多分支的流程图

![img](https://img-blog.csdnimg.cn/img_convert/8967365f726e43b7b93933289656641a.png)

案例演示 2

### 5.6 switch 分支结构

#### 5.6.1 基本语法

![img](https://img-blog.csdnimg.cn/img_convert/3502658c4a83449ac875fd0bfb9a3832.png)

#### 5.6.2 switch 分支结构流程图

![img](https://img-blog.csdnimg.cn/img_convert/0824de0a6491144f34388430feb856ce.png)

#### 5.6.4 switch 注意事项和细节讨论

![img](https://img-blog.csdnimg.cn/img_convert/f591e830600af28e8a43c5db01db5bbc.png)

#### 5.6.5 switch 课堂练习

1. 对学生成绩大于 60 分的，输出"合格"。低于 60 分的，输出"不合格"。(注：输入的成绩不能大于 100), 提示 成绩/60

```java
//思路分析 
//1. 这道题，可以使用 分支来完成， 但是要求使用 switch 
//2. 这里我们需要进行一个转换, 编程思路 : 
// 如果成绩在 [60,100] , (int)(成绩/60) = 1 
// 如果成绩在 [0,60) , (int)(成绩/60) = 0 

//代码实现 
double score = 1.1; 
//使用 if-else 保证输入的成绩有有效的 0-100 
if( score >= 0 && score <= 100) { 
    switch ((int)(score / 60)) { 
        case 0 : 
            System.out.println("不合格"); 
            break; 
        case 1 : 
            System.out.println("合格"); 
            break; 
    } 
} else { 
    System.out.println("输入的成绩在 0-100"); 
}
```

1. 根据用于指定月份，打印该月份所属的季节。3,4,5 春季 6,7,8 夏季 9,10,11 秋季 12, 1, 2 冬季 [ 课堂练习, 提示 使用穿透 ]

```java
//思路分析 
//1. 创建 Scanner 对象， 接收用户输入 
//2. 使用 int month 接收 
//3. 使用 switch 来匹配 ,使用穿透来完成，比较简洁 

Scanner myScanner = new Scanner(System.in); 
System.out.println("输入月份"); 
int month = myScanner.nextInt(); 
switch(month) { 
    case 3: 
    case 4: 
    case 5: 
        System.out.println("这是春季"); 
        break; 
    case 6: 
    case 7:
    case 8: 
        System.out.println("这是夏季"); 
        break; 
    case 9: 
    case 10: 
    case 11: 
        System.out.println("这是秋季"); 
        break; 
    case 1: 
    case 2: 
    case 12: 
        System.out.println("这是冬季"); 
        break; 
    default : 
        System.out.println("你输入的月份不对(1-12)"); 
}
```

#### 5.6.6 switch 和 if 的比较

![img](https://img-blog.csdnimg.cn/img_convert/3401500ce9ca4ba50a31861c2b7fe596.png)

### 5.7 for 循环控制

#### 5.7.3 for 循环流程图

![img](https://img-blog.csdnimg.cn/img_convert/fdfb4fa75e5c79b8ae105895ab5d4e78.png)

#### 5.7.5 for 循环练习题

1. 打印 1~100 之间所有是 9 的倍数的整数，统计个数 及 总和.[化繁为简,先死后活]

```java
public class ForExercise { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        //打印 1~100 之间所有是 9 的倍数的整数，统计个数 及 总和.[化繁为简,先死后活] 
        //老韩的两个编程思想(技巧) 
        //1. 化繁为简 : 即将复杂的需求，拆解成简单的需求，逐步完成 编程 = 思想 --练习-> 代码 
        //2. 先死后活 : 先考虑固定的值，然后转成可以灵活变化的值 
        
        //思路分析 
        //打印 1~100 之间所有是 9 的倍数的整数，统计个数及总和 
        //化繁为简
        //(1) 完成 输出 1-100 的值 
        //(2) 在输出的过程中，进行过滤，只输出 9 的倍数 i % 9 ==0 
        //(3) 统计个数 定义一个变量 int count = 0; 当 条件满足时 count++; 
        //(4) 总和 , 定义一个变量 int sum = 0; 当条件满足时累积 sum += i; 
        //先死后活 
        //(1) 为了适应更好的需求，把范围的开始的值和结束的值，做出变量 
        //(2) 还可以更进一步 9 倍数也做成变量 int t = 9; 
    
        int count = 0; //统计 9 的倍数个数 变量 
        int sum = 0; //总和 
        int start = 10; 
        int end = 200; 
        int t = 5; //倍数 
        for(int i = start; i <= end; i++) { 
            if( i % t == 0) { 
                System.out.println("i=" + i); 
                count++; 
                sum += i;//累积 
            } 
        }

        System.out.println("count=" + count); 
        System.out.println("sum=" + sum); 
    } 
}
```

### 5.8 while 循环控制

#### 5.8.2 while 循环执行流程分析

1. 画出流程图

   ![img](https://img-blog.csdnimg.cn/img_convert/ce593638a014cd31a7bb31392be6342e.png)

   

### 5.9 do…while 循环控制

#### 5.9.3 do…while 循环执行流程图

![img](https://img-blog.csdnimg.cn/img_convert/0dd0348f60686402c814eb85c3d51f71.png)

### 5.10 列子

#### 5.10.4 经典的打印金字塔

![img](https://img-blog.csdnimg.cn/img_convert/5741922c8863d7815a5d65a6b542ce89.png)

```java
public class Stars { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        /* 
              * 
            *  * 
           *    * 
          ******** 
    
        思路分析 
        化繁为简 
        1. 先打印一个矩形 
        ***** 
        *****
        ***** 
        ***** 
        *****
        
        2. 打印半个金字塔
        *       //第 1 层 有 1 个* 
        **      //第 2 层 有 2 个* 
        ***     //第 3 层 有 3 个* 
        ****    //第 4 层 有 4 个* 
        *****   //第 5 层 有 5 个*
        
        3. 打印整个金字塔
            *       //第 1 层 有 1 个* 2 * 1 -1 有 4=(总层数-1)个空格 
           ***      //第 2 层 有 3 个* 2 * 2 -1 有 3=(总层数-2)个空格 
          *****     //第 3 层 有 5 个* 2 * 3 -1 有 2=(总层数-3)个空格 
         *******    //第 4 层 有 7 个* 2 * 4 -1 有 1=(总层数-4)个空格 
        *********   //第 5 层 有 9 个* 2 * 5 -1 有 0=(总层数-5)个空格
        
        4. 打印空心的金字塔 [最难的]
            *       //第 1 层 有 1 个* 当前行的第一个位置是*,最后一个位置也是* 
           * *      //第 2 层 有 2 个* 当前行的第一个位置是*,最后一个位置也是* 
          *   *     //第 3 层 有 2 个* 当前行的第一个位置是*,最后一个位置也是* 
         *     *    //第 4 层 有 2 个* 当前行的第一个位置是*,最后一个位置也是* 
        *********   //第 5 层 有 9 个* 全部输出*
        
        先死后活
        5 层数做成变量 int totalLevel = 5;
        */
        int totalLevel = 20; //层数 
        for(int i = 1; i <= totalLevel; i++) { //i 表示层数 
            //在输出*之前，还有输出 对应空格 = 总层数-当前层 
            for(int k = 1; k <= totalLevel - i; k++ ) { 
                System.out.print(" "); 
            }
            //控制打印每层的*个数 
            for(int j = 1;j <= 2 * i - 1;j++) { 
                //当前行的第一个位置是*,最后一个位置也是*, 最后一层全部 * 
                if(j == 1 || j == 2 * i - 1 || i == totalLevel) { 
                    System.out.print("*"); 
                } else { //其他情况输出空格 
                    System.out.print(" "); 
                } 
            }
            //每打印完一层的*后，就换行 println 本身会换行 
            System.out.println(""); 
        } 
    } 
}
```

### 5.11 跳转控制语句-break

#### 5.11.1 看下面一个需求

![img](https://img-blog.csdnimg.cn/img_convert/37f763c9c5b4b22f80f0ccdb9b093292.png)

#### 5.11.6 注意事项和细节说明：

![img](https://img-blog.csdnimg.cn/img_convert/cc2eb78566f3c0b03538d1593547fd83.png)

### 5.12 跳转控制语句-continue

#### 5.12.1 基本介绍：

![img](https://img-blog.csdnimg.cn/img_convert/ac621549133a9e8253f531a0b6dd0d59.png)

### 5.13 跳转控制语句-return

return 使用在方法，表示跳出所在的方法，在讲解方法的时候，会详细的介绍，这里我们简单的提一下。注意：如果 return 写在 main 方法，则退出程序。

## 第 6 章 数组、排序和查找

### 6.1 为什么需要数组

#### 6.1.1 数组介绍

![img](https://img-blog.csdnimg.cn/img_convert/897e7f1866bdf0a3d3fb76d3c6b08c05.png)

#### 6.1.2 数组快速入门

可以通过 数组名.length 得到数组的大小/长度

### 6.2 数组的使用

![img](https://img-blog.csdnimg.cn/img_convert/a96e5dac27ff14dd5bd832496633ee47.png)

注意：int a[ ] = new int [5] 和 int[ ] a = new int [5] 是等价的。

#### 6.2.1 使用方式 2-动态初始化

![img](https://img-blog.csdnimg.cn/img_convert/9e46784a9346f0eb53ce643bb10e02cd.png)

#### 6.2.2 使用方式 3-静态初始化

![img](https://img-blog.csdnimg.cn/img_convert/8c8eb92d51367e1ac90ea95cc9a329ad.png)

### 6.3 数组使用注意事项和细节

![img](https://img-blog.csdnimg.cn/img_convert/097d5673720b762a111052cf3f7c7bdf.png)

### 6.5 数组赋值机制

![img](https://img-blog.csdnimg.cn/img_convert/2e126d17d51ea323a2f7995ce54d8397.png)

### 6.6 数组拷贝

![img](https://img-blog.csdnimg.cn/img_convert/bd0ed3c8f76ec5a5458240348fbc753d.png)

### 6.7 数组反转

![img](https://img-blog.csdnimg.cn/img_convert/24eb0fbc59e4bbd58087bf17e2383603.png)

方式 1：通过找规律反转

```java
public class ArrayReverse { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        //定义数组 
        int[] arr = {11, 22, 33, 44, 55, 66}; 
        //规律 
        //1. 把 arr[0] 和 arr[5] 进行交换 {66,22,33,44,55,11}
        //2. 把 arr[1] 和 arr[4] 进行交换 {66,55,33,44,22,11} 
        //3. 把 arr[2] 和 arr[3] 进行交换 {66,55,44,33,22,11} 
        //4. 一共要交换 3 次 = arr.length / 2 
        //5. 每次交换时，对应的下标 是 arr[i] 和 arr[arr.length - 1 -i] 
        //代码 
        //优化 
        int temp = 0; 
        int len = arr.length; //计算数组的长度 
        for( int i = 0; i < len / 2; i++) { 
            temp = arr[len - 1 - i];//保存 
            arr[len - 1 - i] = arr[i]; 
            arr[i] = temp; 
        }

        System.out.println("===翻转后数组==="); 
        for(int i = 0; i < arr.length; i++) { 
            System.out.print(arr[i] + "\t");//66,55,44,33,22,11 
        } 
    } 
}
```

方式 2：使用逆序赋值方式

```java
public class ArrayReverse02 { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        //定义数组 
        int[] arr = {11, 22, 33, 44, 55, 66}; 
        //使用逆序赋值方式 
        //1. 先创建一个新的数组 arr2 ,大小 arr.length 
        //2. 逆序遍历 arr ,将 每个元素拷贝到 arr2 的元素中(顺序拷贝) 
        //3. 建议增加一个循环变量 j -> 0 -> 5 
        int[] arr2 = new int[arr.length]; 
        //逆序遍历 arr 
        for(int i = arr.length - 1, j = 0; i >= 0; i--, j++) { 
            arr2[j] = arr[i]; 
        }
        //4. 当 for 循环结束，arr2 就是一个逆序的数组 {66, 55, 44,33, 22, 11} 
        //5. 让 arr 指向 arr2 数据空间, 此时 arr 原来的数据空间就没有变量引用 
        // 会被当做垃圾，销毁 
        arr = arr2; 
        System.out.println("====arr 的元素情况====="); 
        //6. 输出 arr 看看 
        for(int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + "\t"); 
        } 
    } 
}
```

### 6.9 排序的介绍

![img](https://img-blog.csdnimg.cn/img_convert/b4b5a6bce5e2618a99099584d19087e0.png)

### 6.10 冒泡排序法

冒泡排序（Bubble Sorting）的基本思想是：通过对待排序序列从后向前（从下标较大的元素开始），依次比较相邻元素 的值，若发现逆序则交换，使值较大的元素逐渐从前移向后部，就象水底下的气泡一样逐渐向上冒。

![img](https://img-blog.csdnimg.cn/img_convert/f745ec52eed0cbc2842778754b8d1b48.png)

```java
public class BubbleSort { 
    //编写一个 main 方法 
    public static void main(String[] args) {
    int[] arr = {24, 69, 80, 57, 13, -1, 30, 200, -110}; 
    int temp = 0; //用于辅助交换的变量 
    
    //将多轮排序使用外层循环包括起来即可 
    for( int i = 0; i < arr.length - 1; i++) {//外层循环是 4 次 
        for( int j = 0; j < arr.length - 1 - i; j++) {//4 次比较-3 次-2 次-1 次 
            //如果前面的数>后面的数，就交换 
            if(arr[j] > arr[j + 1]) { 
                temp = arr[j]; 
                arr[j] = arr[j+1]; 
                arr[j+1] = temp; 
            } 
        }
        System.out.println("\n==第"+(i+1)+"轮=="); 
        for(int j = 0; j < arr.length; j++) { 
            System.out.print(arr[j] + "\t");
        } 
    }
}
```

### 6.12 查找

#### 6.12.1 介绍：

在 java 中，我们常用的查找有两种:

1. 顺序查找
2. 二分查找

#### 6.12.2 案例演示：

有一个数列：白眉鹰王、金毛狮王、紫衫龙王、青翼蝠王猜数游戏：从键盘中任意输入一个名称，判断数列中是否 包含此名称【顺序查找】 要求: 如果找到了，就提示找到，并给出下标值。

```java
import java.util.Scanner; 
public class SeqSearch { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        /*
        思路分析 
        1. 定义一个字符串数组 
        2. 接收用户输入, 遍历数组，逐一比较，如果有，则提示信息，并退出 
        */
        //定义一个字符串数组 
        String[] names = {"白眉鹰王", "金毛狮王", "紫衫龙王", "青翼蝠王"}; 
        Scanner myScanner = new Scanner(System.in); 
        System.out.println("请输入名字"); 
        String findName = myScanner.next(); 
        
        //遍历数组，逐一比较，如果有，则提示信息，并退出 
        //这里老师给大家一个编程思想/技巧, 一个经典的方法 
        int index = -1; 
        for(int i = 0; i < names.length; i++) { 
            //比较 字符串比较 equals, 如果要找到名字就是当前元素 
            if(findName.equals(names[i])) { 
                System.out.println("恭喜你找到 " + findName); 
                System.out.println("下标为= " + i); 
                //把 i 保存到 index 
                index = i; 
                break;//退出 
            } 
        }
        if(index == -1) { //没有找到 
            System.out.println("sorry ,没有找到 " + findName); 
        }
    }
}
```

### 6.14 二维数组的使用

#### 6.14.2 使用方式 1: 动态初始化

![img](https://img-blog.csdnimg.cn/img_convert/161805f75bcd31750973887863e11862.png)

#### 6.14.3 使用方式 2: 动态初始化

![img](https://img-blog.csdnimg.cn/img_convert/3a165c66b64fa37b07e3a6400fe22198.png)

#### 6.14.4 使用方式 3: 动态初始化-列数不确定

![img](https://img-blog.csdnimg.cn/img_convert/464365fe29f98f00b865296ce65dbd65.png)

```java
public class TwoDimensionalArray03 {
    //编写一个 main 方法 
    public static void main(String[] args) { 
        //创建 二维数组，一个有 3 个一维数组，但是每个一维数组还没有开数据空间 
        int[][] arr = new int[3][]; 
        for(int i = 0; i < arr.length; i++) {//遍历 arr 每个一维数组 
            //给每个一维数组开空间 new 
            //如果没有给一维数组 new ,那么arr[i]就是 null 
            arr[i] = new int[i + 1]; 
            
            //遍历一维数组，并给一维数组的每个元素赋值 
            for(int j = 0; j < arr[i].length; j++) { 
                arr[i][j] = i + 1;//赋值 
            }
        }
        System.out.println("=====arr 元素====="); 
        //遍历 arr 输出 
        for(int i = 0; i < arr.length; i++) { 
            //输出 arr 的每个一维数组 
            for(int j = 0; j < arr[i].length; j++) { 
                System.out.print(arr[i][j] + " "); 
            }
            System.out.println();//换行 
        } 
    } 
}
```

#### 6.14.5 使用方式 4: 静态初始化

![img](https://img-blog.csdnimg.cn/img_convert/065747121ddfc99b7d3429abe21aeb38.png)

### 6.15 二维数组的应用案例

使用二维数组打印一个 10 行杨辉三角

![img](https://img-blog.csdnimg.cn/img_convert/d82812496be195ff9e211d57b0a1a3f4.png)

```java
public class YangHui { 
    //编写一个 main 方法 
    public static void main(String[] args) {
        /*
            规律
            1.第一行有 1 个元素, 第 n 行有 n 个元素 
            2. 每一行的第一个元素和最后一个元素都是 1 
            3. 从第三行开始, 对于非第一个元素和最后一个元素的元素的值. arr[i][j] 
            arr[i][j] = arr[i-1][j] + arr[i-1][j-1]; //必须找到这个规律 
        */ 
        int[][] yangHui = new int[12][]; 
        for(int i = 0; i < yangHui.length; i++) {//遍历 yangHui 的每个元素 
            //给每个一维数组(行) 开空间 
            yangHui[i] = new int[i+1]; 
            //给每个一维数组(行) 赋值 
            for(int j = 0; j < yangHui[i].length; j++){ 
                //每一行的第一个元素和最后一个元素都是 1 
                if(j == 0 || j == yangHui[i].length - 1) { 
                    yangHui[i][j] = 1; 
                } else {//中间的元素 
                    yangHui[i][j] = yangHui[i-1][j] + yangHui[i-1][j-1]; 
                }
            } 
        }
        //输出杨辉三角 
        for(int i = 0; i < yangHui.length; i++) { 
            for(int j = 0; j < yangHui[i].length; j++) {//遍历输出该行 
                System.out.print(yangHui[i][j] + "\t"); 
            }
            System.out.println();//换行. 
        } 
    } 
}
```

### 6.16 二维数组使用细节和注意事项

![img](https://img-blog.csdnimg.cn/img_convert/23ce3f8a30451563646f9638fbaaf68a.png)

### 6.17 二维数组课堂练习

![img](https://img-blog.csdnimg.cn/img_convert/7d4a076ea4fceb52bc0049be62c8fd23.png)

## 第 7 章 面向对象编程(基础部分)

### 7.1 类与对象

#### 7.1.5 类与对象的关系示意图

![img](https://img-blog.csdnimg.cn/img_convert/e19f3ab60a6cbdeeb2bbc47a5327ee85.png)

#### 7.1.6 类与对象的关系示意图

![img](https://img-blog.csdnimg.cn/img_convert/7f64b0f77fcd724d9455c8eed3c22c87.png)

#### 7.1.8 类和对象的区别和联系

![img](https://img-blog.csdnimg.cn/img_convert/335a027c11e4fe7c09de928946b2c2ac.png)

#### 7.1.9 对象在内存中存在形式（重要，必须搞清楚）

![img](https://img-blog.csdnimg.cn/img_convert/0e611a5d310a71f9956bee7c3018b694.png)

#### 7.1.10 属性/成员变量/字段

![img](https://img-blog.csdnimg.cn/img_convert/3f5a799c583eaf42961575565009c8d2.png)

注意事项和细节说明：

#### 7.1.13 类和对象的内存分配机制

![img](https://img-blog.csdnimg.cn/img_convert/5260fe056f0ddd68fdff9474edbc1126.png)

看一个练习题，并分析画出内存布局图，进行分析 最后一句会报 NullPointerException 异常。

### 7.2 成员方法

#### 7.2.3 方法的调用机制原理：(重要!-示意图!!!)

![img](https://img-blog.csdnimg.cn/img_convert/7681ff6df974b8119a4ed1038e7bd83e.png)

#### 7.2.5 成员方法的好处

![img](https://img-blog.csdnimg.cn/img_convert/2e2b4205c6e7d97f2969a448334cec3e.png)

#### 7.2.7 注意事项和使用细节

![img](https://img-blog.csdnimg.cn/img_convert/bb55f8677fea3db095f52578d5e10494.png)

```java
public class MethodDetail02 { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        A a = new A(); 
        //a.sayOk(); 
        a.m1(); 
    } 
}
class A { 
    //同一个类中的方法调用：直接调用即可 
    public void print(int n) { 
        System.out.println("print()方法被调用 n=" + n);
    }
    public void sayOk() { //sayOk 调用 print(直接调用即可) 
        print(10); 
        System.out.println("继续执行 sayOK()~~~"); 
    }
    //跨类中的方法 A 类调用 B 类方法：需要通过对象名调用 
    public void m1() { 
        //创建 B 对象, 然后在调用方法即可 
        System.out.println("m1() 方法被调用"); 
        B b = new B(); 
        b.hi(); 
        System.out.println("m1() 继续执行:)"); 
    } 
}
class B { 
    public void hi() { 
        System.out.println("B 类中的 hi()被执行"); 
    } 
}
```

### 7.3 成员方法传参机制(非常非常重要)

![img](https://img-blog.csdnimg.cn/img_convert/748f6105373884c36ccf08413beb70d6.png)

```java
public class MethodParameter01 { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        int a = 10; 
        int b = 20; //创建 AA 对象 名字 obj 
        AA obj = new AA(); 
        obj.swap(a, b); //调用 swap 
        System.out.println("main 方法 a=" + a + " b=" + b);//a=10 b=20 
    } 
}
class AA { 
    public void swap(int a,int b){ 
        System.out.println("\na 和 b 交换前的值\na=" + a + "\tb=" + b);//a=10 b=20 
        //完成了 a 和 b 的交换 
        int tmp = a; 
        a = b; 
        b = tmp; 
        System.out.println("\na 和 b 交换后的值\na=" + a + "\tb=" + b);//a=20 b=10 
    } 
}
```

![img](https://img-blog.csdnimg.cn/img_convert/958690bd2fde9226cfae684cf0b038f3.png)

#### 7.3.2 引用数据类型的传参机制

![img](https://img-blog.csdnimg.cn/img_convert/a932be2e21658c0e9daa5d4890dbfb8c.png)

在看一个案例，下面的方法会对原来的对象有影响吗？ p=null 和 p = new Person(); 对应示意图

### 7.4 方法递归调用(非常非常重要，比较难)

#### 7.4.4 递归重要规则

![img](https://img-blog.csdnimg.cn/img_convert/142c364634be02ded9e9a212a8fcbc5d.png)

#### 7.4.5 课堂练习

![img](https://img-blog.csdnimg.cn/img_convert/78a49ac433e8b7bf1f71bd3e35c176e4.png)

```java
public class RecursionExercise01 { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        T t1 = new T(); 
        int n = 7; 
        int res = t1.fibonacci(n); 
        if(res != -1) { 
            System.out.println("当 n="+ n +" 对应的斐波那契数=" + res); 
        } 
        //桃子问题 
        int day = 0; 
        int peachNum = t1.peach(day); 
        if(peachNum != -1) { 
            System.out.println("第 " + day + "天有" + peachNum + "个桃子"); 
        }
    } 
}
class T {
    /*
    请使用递归的方式求出斐波那契数 1,1,2,3,5,8,13...给你一个整数 n，求出它的值是多 
    思路分析 
    1. 当 n = 1 斐波那契数 是 1 
    2. 当 n = 2 斐波那契数 是 1
    3. 当 n >= 3 斐波那契数 是前两个数的和 
    4. 这里就是一个递归的思路 
    */ 
    public int fibonacci(int n) { 
        if( n >= 1) { 
            if( n == 1 || n == 2) { 
                return 1; 
            } else { 
                return fibonacci(n-1) + fibonacci(n-2); 
            } 
        } else { 
            System.out.println("要求输入的 n>=1 的整数"); 
            return -1; 
        } 
    }
    /*
    猴子吃桃子问题：有一堆桃子，猴子第一天吃了其中的一半，并再多吃了一个！ 
    以后每天猴子都吃其中的一半，然后再多吃一个。当到第 10 天时， 
    想再吃时（即还没吃），发现只有 1 个桃子了。问题：最初共多少个桃子？ 
    思路分析 逆推 
    1. day = 10 时 有 1 个桃子 
    2. day = 9 时 有 (day10 + 1) * 2 = 4 
    3. day = 8 时 有 (day9 + 1) * 2 = 10 
    4. 规律就是 前一天的桃子 = (后一天的桃子 + 1) *2
    5. 递归 
     */ 
     public int peach(int day) { 
        if(day == 10) {//第 10 天，只有 1 个桃 
            return 1; 
        } else if ( day >= 1 && day <=9 ) { 
            return (peach(day + 1) + 1) * 2;//规则，自己要想 
        } else { 
            System.out.println("day 在 1-10"); return -1; 
        } 
     } 
}
```

#### 7.4.6 递归调用应用实例-迷宫问题

![img](https://img-blog.csdnimg.cn/img_convert/6cf20e1a128dd2bc3c6eb93be1c7ba03.png)

```java
public class MiGong { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        //思路 
        //1. 先创建迷宫，用二维数组表示 int[][] map = new int[8][7]; 
        //2. 先规定 map 数组的元素值: 0 表示可以走 1 表示障碍物 
        int[][] map = new int[8][7]; 
        //3. 将最上面的一行和最下面的一行，全部设置为 1 
        for(int i = 0; i < 7; i++) { 
            map[0][i] = 1; 
            map[7][i] = 1; 
        }
        //4.将最右面的一列和最左面的一列，全部设置为 1 
        for(int i = 0; i < 8; i++) {
            map[i][0] = 1; 
            map[i][6] = 1; 
        }
        map[3][1] = 1; 
        map[3][2] = 1; 
        map[2][2] = 1; //测试回溯 

        //输出当前的地图 
        System.out.println("=====当前地图情况======"); 
        for(int i = 0; i < map.length; i++) { 
            for(int j = 0; j < map[i].length; j++) { 
                System.out.print(map[i][j] + " ");//输出一行 
            }
            System.out.println(); 
        }
        //使用 findWay 给老鼠找路 
        T t1 = new T(); 
        //下右上左 
        t1.findWay(map, 1, 1); 
        System.out.println("\n====找路的情况如下=====");
        for(int i = 0; i < map.length; i++) { 
            for(int j = 0; j < map[i].length; j++) { 
                System.out.print(map[i][j] + " ");//输出一行 
            }
            System.out.println(); 
        } 
    } 
}
class T { 
    //使用递归回溯的思想来解决老鼠出迷宫 
    //老韩解读 
    //1. findWay 方法就是专门来找出迷宫的路径 
    //2. 如果找到，就返回 true ,否则返回 false 
    //3. map 就是二维数组，即表示迷宫 
    //4. i,j 就是老鼠的位置，初始化的位置为(1,1) 
    //5. 因为我们是递归的找路，所以我先规定 map 数组的各个值的含义 
    // 0 表示可以走 1 表示障碍物 2 表示可以走 3 表示走过，但是走不通是死路 
    //6. 当 map[6][5] =2 就说明找到通路,就可以结束，否则就继续找. 
    //7. 先确定老鼠找路策略 下->右->上->左
    public boolean findWay(int[][] map , int i, int j) { 
        if(map[6][5] == 2) {//说明已经找到 
            return true; 
        } else { 
            if(map[i][j] == 0) {//当前这个位置 0,说明表示可以走 
                //我们假定可以走通 
                map[i][j] = 2; 
                //使用找路策略，来确定该位置是否真的可以走通 
                //下->右->上->左 
                if(findWay(map, i + 1, j)) {//先走下 
                    return true; 
                } else if(findWay(map, i, j + 1)){//右 
                    return true; 
                } else if(findWay(map, i-1, j)) {//上 
                    return true; 
                } else if(findWay(map, i, j-1)){//左 
                    return true; 
                } else { 
                    map[i][j] = 3; 
                    return false; 
                } 
            } else { //map[i][j] = 1 , 2, 3 
                return false; 
            } 
        }
    }
}
```

![img](https://img-blog.csdnimg.cn/img_convert/98594032b8f1129310a3fc7998f26132.png)

#### 7.4.7 递归调用应用实例-汉诺塔

![img](https://img-blog.csdnimg.cn/img_convert/36acaea6bc403062d7e958e2c62190e4.png)

HanoiTower.java

```java
public class HanoiTower { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        Tower tower = new Tower(); 
        tower.move(64, 'A', 'B', 'C'); 
    } 
}
class Tower { 
    //方法 
    //num 表示要移动的个数, a, b, c 分别表示 A 塔，B 塔, C 塔 
    public void move(int num , char a, char b ,char c) { 
        //如果只有一个盘 num = 1
        if(num == 1) { 
            System.out.println(a + "->" + c); 
        } else { 
            //如果有多个盘，可以看成两个 , 最下面的和上面的所有盘(num-1) 
            //(1)先移动上面所有的盘到 b, 借助 c 
            move(num - 1 , a, c, b); 
            //(2)把最下面的这个盘，移动到 c 
            System.out.println(a + "->" + c); 
            //(3)再把 b 塔的所有盘，移动到 c ,借助 a 
            move(num - 1, b, a, c); 
        } 
    } 
}
```

#### 7.4.8 递归调用应用实例-八皇后问题[同学们先尝试做，后面老师评讲.]

![img](https://img-blog.csdnimg.cn/img_convert/87fa8cf1160401ee76aea56719592560.png)

### 7.5 方法重载(OverLoad)

#### 7.5.1 基本介绍

java 中允许同一个类中，多个同名方法的存在，但要求 形参列表不一致！ 比如：System.out.println(); 其中 out 是 PrintStream 类型

#### 7.5.2 重载的好处

1. 减轻了起名的麻烦
2. 减轻了记名的麻烦

#### 7.5.4 注意事项和使用细节

![img](https://img-blog.csdnimg.cn/img_convert/ee15185ec0f60d526a205128ea5a08ed.png)

### 7.6 可变参数

#### 7.6.1 基本概念

java 允许将同一个类中多个同名同功能但参数个数不同的方法，封装成一个方法。 就可以通过可变参数实现

#### 7.6.2 基本语法

访问修饰符 返回类型 方法名(数据类型… 形参名) { }

#### 7.6.3 快速入门案例(VarParameter01.java)

看一个案例：类 HspMethod，方法 sum 【可以计算 2 个数的和，3 个数的和 ， 4、5， 。。】

```java
public class VarParameter01 { 
    //编写一个 main 方法 
    public static void main(String[] args) { 
        HspMethod m = new HspMethod(); 
        System.out.println(m.sum(1, 5, 100)); //106 
        System.out.println(m.sum(1,19)); //20 
    } 
}
class HspMethod { 
    //可以计算 2 个数的和，3 个数的和 ， 4. 5， 。。
    //老韩解读
    //1. int... 表示接受的是可变参数，类型是 int ,即可以接收多个 int(0-多) 
    //2. 使用可变参数时，可以当做数组来使用 即 nums 可以当做数组 
    //3. 遍历 nums 求和即可 
    public int sum(int... nums) { 
        //System.out.println("接收的参数个数=" + nums.length); 
        int res = 0; 
        for(int i = 0; i < nums.length; i++) { 
            res += nums[i]; 
        }
        return res; 
    } 
}
```

#### 7.6.4 注意事项和使用细节

![img](https://img-blog.csdnimg.cn/img_convert/9ea401ae4350b6e0b6f656bf5fe43b04.png)

```java
public class VarParameterDetail { 
    //编写一个 main 方法 
    public static void main(String[] args) {
        //细节: 可变参数的实参可以为数组 
        int[] arr = {1, 2, 3}; 
        T t1 = new T(); 
        t1.f1(arr); 
    } 
}
class T { 
    public void f1(int... nums) { 
        System.out.println("长度=" + nums.length); 
    }
    //细节: 可变参数可以和普通类型的参数一起放在形参列表，但必须保证可变参数在最后 
    public void f2(String str, double... nums) { 
    }
    //细节: 一个形参列表中只能出现一个可变参数 
    //下面的写法是错的. 
    // public void f3(int... nums1, double... nums2) { 
    // } 
}
```

### 7.7 作用域

#### 7.7.1 基本使用

![img](https://img-blog.csdnimg.cn/img_convert/07e9063fa953800cd8375f8cfee644c7.png)

#### 7.7.2 注意事项和细节使用

![img](https://img-blog.csdnimg.cn/img_convert/8787141bfcf67240e6efeade701c5e36.png)

### 7.8 构造方法/构造器

#### 7.8.2 基本语法

![img](https://img-blog.csdnimg.cn/img_convert/6079bbdd5cc5c07042d21a726a18ac80.png)

#### 7.8.3 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/4d71d5f314312f6ea765ed3d8778209b.png)

#### 7.8.5 注意事项和使用细节

![img](https://img-blog.csdnimg.cn/img_convert/16f7eeed872a5fca94b333ae33faedbb.png)

### 7.9 对象创建的流程分析

#### 7.9.1 看一个案例

![img](https://img-blog.csdnimg.cn/img_convert/4f279bd0b5c071be969eaee1e3123b2c.png)

### 7.10 this 关键字

#### 7.10.2 深入理解 this

![img](https://img-blog.csdnimg.cn/img_convert/96e7262fff61ee231aa7812b62719f69.png)

#### 7.10.3 this 的注意事项和使用细节

![img](https://img-blog.csdnimg.cn/img_convert/078f2e9abc6adb21b956e30ed0a63191.png)

### 7.11 本章作业

![img](https://img-blog.csdnimg.cn/img_convert/a1837626984d425fc6b7376a8b2452a9.png)

```java
public class Homework01 { 
    //编写一个main方法
    public static void main(String[] args) {
        A01 a01 = new A01();
        double[] arr = {1, 1.4, -1.3, 89.8, 123.8 , 66}; //;{};
        Double res = a01.max(arr);
        if(res != null) {
            System.out.println("arr的最大值=" + res);
        } else {
            System.out.println("arr的输入有误, 数组不能为null, 或者{}");
        }
    }
}
/*
编写类A01，定义方法max，实现求某个double数组的最大值，并返回

思路分析
1. 类名 A01
2. 方法名 max
3. 形参 (double[])
4. 返回值 double

先完成正常业务，然后再考虑代码健壮性
 */
class A01 {
    public Double max(double[] arr) {
        //老韩先判断arr是否为null,然后再判断 length 是否>0
        if( arr!= null && arr.length > 0 ) {
            //保证arr至少有一个元素 
            double max = arr[0];//假定第一个元素就是最大值
            for(int i = 1; i < arr.length; i++) {
                if(max < arr[i]) {
                    max = arr[i];
                }
            }
            return max;//double
        } else {
            return null;
        }
    }
}
```

![img](https://img-blog.csdnimg.cn/img_convert/566786b34ab25ca4fc72b9fb258da877.png)

```java
public class Homework06 { 
    //编写一个main方法
    public static void main(String[] args) {
        Cale cale = new Cale(2, 10);
        System.out.println("和=" + cale.sum());
        System.out.println("差=" + cale.minus());
        System.out.println("乘=" + cale.mul());
        Double divRes = cale.div();
        if(divRes != null) {
            System.out.println("除=" + divRes);
        } 
    }
}
/*
 编程创建一个Cale计算类，在其中定义2个变量表示两个操作数，
 定义四个方法实现求和、差、乘、商(要求除数为0的话，要提示) 并创建两个对象，分别测试 
 */
class Cale {
    double num1;
    double num2;
    public Cale(double num1, double num2) {
        this.num1 = num1;
        this.num2 = num2;
    }
    //和
    public double sum() {
        return num1 + num2;
    }
    //差
    public double minus() {
        return num1 - num2;
    }
    //乘积
    public double mul() {
        return num1 * num2;
    }
    //除法
    public Double div() {
        //判断
        if(num2 == 0) {
            System.out.println("num2 不能为0");
            return null;
        } else {
            return num1 / num2;
        }
    }
}
```



## 第8章 面向对象编程(中级部分)

### 8.3 IDEA

#### 8.3.4 课堂练习

![img](https://img-blog.csdnimg.cn/img_convert/61afc6ba85e71cacc3fde142f36e66eb.png)

8.3.5 IDEA 常用快捷键

![img](https://img-blog.csdnimg.cn/img_convert/c4f0d08b1bbff3d0d709675b02aa7f10.png)

第11点也可以用 alt + enter

#### 8.3.6 模板/自定义模板

![img](https://img-blog.csdnimg.cn/img_convert/334b08ebfec99b5a6937c00396b57ceb.png)

### 8.4 包

#### 8.4.2 包的三大作用

![img](https://img-blog.csdnimg.cn/img_convert/74398056ea48b7f180c12955480f13f8.png)

#### 8.4.3 包基本语法

![img](https://img-blog.csdnimg.cn/img_convert/8229d13fd48dd790f021b41be0c27f23.png)

#### 8.4.4 包的本质分析(原理)

![img](https://img-blog.csdnimg.cn/img_convert/a8a9a4a814701308f8e4d96aa03bc166.png)

#### 8.4.5 快速入门

![img](https://img-blog.csdnimg.cn/img_convert/68011289503c46f6dad7380c91e24218.png)

#### 8.4.6 包的命名

![img](https://img-blog.csdnimg.cn/img_convert/f642c5c54065dce474b2c01f68ae82d0.png)

#### 8.4.7 常用的包

![img](https://img-blog.csdnimg.cn/img_convert/67b4d7bd4bdd9e9fb1aac28bbfa7aa64.png)

#### 8.4.8 如何引入包

![img](https://img-blog.csdnimg.cn/img_convert/a7ab500dfd7c896d681b6fa863930412.png)

```java
package com.hspedu.pkg; 
import java.util.Arrays; 
//注意: 
//老韩建议：我们需要使用到哪个类，就导入哪个类即可，不建议使用 *导入 
//import java.util.Scanner; //表示只会引入 java.util 包下的 Scanner 
//import java.util.*;//表示将 java.util 包下的所有类都引入(导入) 
public class Import01 { 
    public static void main(String[] args) { 
        //使用系统提供 Arrays 完成 数组排序 
        int[] arr = {-1, 20, 2, 13, 3}; 
        //比如对其进行排序 
        //传统方法是，自己编写排序(冒泡) 
        //系统是提供了相关的类，可以方便完成 
        Arrays.sort(arr); 
        //输出排序结果 
        for (int i = 0; i < arr.length ; i++) { 
            System.out.print(arr[i] + "\t"); 
        }
    }
}
```

#### 8.4.9 注意事项和使用细节

![img](https://img-blog.csdnimg.cn/img_convert/4d9ac1e70c537689c0a399d96b526db9.png)

### 8.5 访问修饰符

#### 8.5.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/954ca2f69e9a8d7c36ea45d243aec951.png)

#### 8.5.2 种访问修饰符的访问范围

![img](https://img-blog.csdnimg.cn/img_convert/7b4173fc01937cdb78bed342b9cf4476.png)

#### 8.5.3 使用的注意事项

![img](https://img-blog.csdnimg.cn/img_convert/bc4ab51bd8d1f16a7ffe1c2c35387590.png)

### 8.6 面向对象编程三大特征

#### 8.6.1 基本介绍

面向对象编程有三大特征：封装、继承和多态。

#### 8.6.2 封装介绍

![img](https://img-blog.csdnimg.cn/img_convert/284c8eacc8b1d30f3c5ffff746d6c7d0.png)

#### 8.6.3 封装的理解和好处

![img](https://img-blog.csdnimg.cn/img_convert/57a7c34c0f18c39f4ea09f6c8b749189.png)

#### 8.6.4 封装的实现步骤 (三步)

![img](https://img-blog.csdnimg.cn/img_convert/fe8a649d8ee644d65d05a6008b9aa36b.png)

#### 8.7.1 将构造器和 setXxx 结合

看一个案例

```java
//有三个属性的构造器 
public Person(String name, int age, double salary) { 
    // this.name = name; 
    // this.age = age; 
    // this.salary = salary; 
    //我们可以将 set 方法写在构造器中，这样仍然可以验证 
    setName(name); 
    setAge(age); 
    setSalary(sal8.8面向对象编程-继承
ary); 
}
```

### 8.8面向对象编程-继承

#### 8.8.1为什么需要继承

![img](https://img-blog.csdnimg.cn/img_convert/fb8a99a592531dbf2bb880f0a7111943.png)

#### 8.8.2 继承基本介绍和示意图

继承可以解决代码复用,让我们的编程更加靠近人类思维.当多个类存在相同的属性(变量)和方法时,可以从这些类中抽象出父类,在父类中定义这些相同的属性和方法，所有的子类不需要重新定义这些属性和方法，只需要通过 extends 来声明继承父类即可。画出继承的示意图

![img](https://img-blog.csdnimg.cn/img_convert/0b39f9916022584380f48e269a13de11.png)



#### 8.8.3 继承的基本语法

![img](https://img-blog.csdnimg.cn/img_convert/ff45507819b46f8ec3f8541acf226ee2.png)



#### 8.8.5继承给编程带来的便利

1. 代码的复用性提高了

2. 代码的扩展性和维护性提高了

   

#### 8.8.6继承的深入讨论/细节问题

1、子类继承了所有的属性和方法，非私有的属性和方法可以在子类直接访问, 但是私有属性和方法不能在子类直接访问，要通过父类提供公共的方法去访问

2、子类必须调用父类的构造器，完成父类的初始化

3、当创建子类对象时，不管使用子类的哪个构造器，默认情况下总会去调用父类的无参构造器，如果父类没有提供无 参构造器，则必须在子类的构造器中用 super 去指定使用父类的哪个构造器完成对父类的初始化工作，否则，编译不会通过(怎么理解。) [举例说明]

4、如果希望指定去调用父类的某个构造器，则显式的调用一下 : super(参数列表)

5、super 在使用时，必须放在构造器第一行(super 只能在构造器中使用)

6、super() 和 this() 都只能放在构造器第一行，因此这两个方法不能共存在一个构造器

7、java 所有类都是 Object 类的子类, Object 是所有类的基类.

8、父类构造器的调用不限于直接父类！将一直往上追溯直到 Object 类(顶级父类)

9、子类最多只能继承一个父类(指直接继承)，即 java 中是单继承机制。 思考：如何让 A 类继承 B 类和 C 类？ 【A 继承 B， B 继承 C】

10、不能滥用继承，子类和父类之间必须满足 is-a 的逻辑关系



#### 8.8.7 继承的本质分析(重要)



案例

![img](https://img-blog.csdnimg.cn/img_convert/210d12e9e08f029be9565cc74b54c46f.png)

```java
/**
 * 讲解继承的本质
 */
public class ExtendsTheory {
    public static void main(String[] args) {
        Son son = new Son();//内存的布局
        //?-> 这时请大家注意，要按照查找关系来返回信息
        //(1) 首先看子类是否有该属性
        //(2) 如果子类有这个属性，并且可以访问，则返回信息
        //(3) 如果子类没有这个属性，就看父类有没有这个属性(如果父类有该属性，并且可以访问，就返回信息..)
        //(4) 如果父类没有就按照(3)的规则，继续找上级父类，直到Object...
        System.out.println(son.name);//返回就是大头儿子
        //System.out.println(son.age);//返回的就是39
        //System.out.println(son.getAge());//通过公共函数调用私有信息，返回的就是39
        System.out.println(son.hobby);//返回的就是旅游
    }
}
//如果father 年龄是私有，grandfather 年龄是公共，堆中任然会有father的age的空间，
// 且System.out.println(son.age);不会跳过父亲的私有直接访问爷爷的公共，会直接报错
class GrandPa { //爷类
    String name = "大头爷爷";
    String hobby = "旅游";
}

class Father extends GrandPa {//父类
    String name = "大头爸爸";
    private int age = 39;

    public int getAge() {
        return age;
    }
}

class Son extends Father { //子类
    String name = "大头儿子";
}
```

![img](https://img-blog.csdnimg.cn/img_convert/c9da1095ae69701aeff568a21d2579e2.png)

类的加载先object->grandfather.....

#### 8.8.8 课堂练习

1. 案例 1 ExtendsExercise01.java

   ![img](https://img-blog.csdnimg.cn/img_convert/9429c7d44b221eb574afb3e5a5c77dd6.png)

```java
package com.hspedu.extend_.exercise;

public class ExtendsExercise01 {
   public static void main(String[] args) {
        B b=new B();//a , b name, b
    }
}

class A {
    A() {
        System.out.println("a");
    }

    A(String name) {
       System.out.println("a name");
    }
}

class B extends A {
    B() {
        this("abc");//this和super不能共存
        System.out.println("b");
    }

    B(String name) {
        //默认有 super();
        //super("jack")会调用 A(String name)
       System.out.println("b name");
    }
}

```

2.案例 2 ExtendsExercise02.java

```java
public class ExtendsExercise02 {
    public static void main(String[] args) {
        C c = new C();
    }
}

class A {//A类

    public A() {
        System.out.println("我是A类");
    }
}

class B extends A { //B类,继承A类       //main方法中： C c =new C(); 输出么内容? 3min
    public B() {
        System.out.println("我是B类的无参构造");
    }

    public B(String name) {
        System.out.println(name + "我是B类的有参构造");
    }
}

class C extends B {   //C类，继承 B类
    public C() {
        this("hello");
        System.out.println("我是c类的无参构造");
    }

    public C(String name) {
        super("hahah");
        System.out.println("我是c类的有参构造");
    }
}
```



结果：

我是A类  hahah我是B类的有参构造  我是c类的有参构造  我是c类的无参构造

3、案例 3 ExtendsExercise03.java

编写 Computer 类，包含 CPU、内存、硬盘等属性，getDetails 方法用于返回 Computer 的详细信息

编写 PC 子类，继承 Computer 类，添加特有属性【品牌 brand】

编写 NotePad 子类，继承 Computer 类，添加特有属性【color】

编写 Test 类，在 main 方法中创建 PC 和 NotePad 对象，分别给对象中特有的属性赋值，以及从 Computer 类继承的属性赋值，并使用方法并打印输出信息



computer类

```java
 package com.hspedu.extend_.exercise;

//编写Computer类，包含CPU、内存、硬盘等属性，getDetails方法用于返回Computer的详细信息
public class Computer {
    private String cpu;
    private int memory;
    private int disk;
    public Computer(String cpu, int memory, int disk) {//通过构造器给赋值
        // 有构造器存在导致后面get.. set..全部失效，在构造器中添加set 或者 get
        this.cpu = cpu;
        this.memory = memory;
        this.disk = disk;
    }
    //返回Computer信息
    public String getDetails() {

        return "cpu=" + cpu + " memory=" + memory + " disk=" + disk;
    }

    public String getCpu() {

        return cpu;
    }

    public void setCpu(String cpu) {

        this.cpu = cpu;
    }

    public int getMemory() {

        return memory;
    }

    public void setMemory(int memory) {

        this.memory = memory;
    }

    public int getDisk() {

        return disk;
    }

    public void setDisk(int disk) {

        this.disk = disk;
    }
}

```

pc类

```java
package com.hspedu.extend_.exercise;

//编写PC子类，继承Computer类，添加特有属性【品牌brand】

public class PC extends Computer{

    private String brand;
    //这里IDEA 根据继承的规则，自动把构造器的调用写好
    //这里也体现： 继承设计的基本思想，父类的构造器完成父类属性初始化
    //子类的构造器完成子类属性初始化
    public PC(String cpu, int memory, int disk, String brand) {
        super(cpu, memory, disk);
        this.brand = brand;
    }
    public String getBrand() {

        return brand;
    }
    public void setBrand(String brand) {

        this.brand = brand;
    }
    public void printInfo() {
        System.out.println("PC信息=");
//        System.out.println(getCpu() + getMemory() + getDisk());
        //调用父类的getDetails方法，得到相关属性信息..
        System.out.println(getDetails() + " brand=" + brand);
    }

}

```

主程序

```java
package com.hspedu.extend_.exercise;

public class ExtendsExercise03 {
    public static void main(String[] args) {
        PC pc = new PC("intel", 16, 500, "IBM");
        pc.printInfo();
    }
}
/*
编写Computer类，包含CPU、内存、硬盘等属性，getDetails方法用于返回Computer的详细信息
编写PC子类，继承Computer类，添加特有属性【品牌brand】
编写NotePad子类，继承Computer类，添加特有属性【color】//同学们自己写。
编写Test类，在main方法中创建PC和NotePad对象，分别给对象中特有的属性赋值，
以及从Computer类继承的属性赋值，并使用方法并打印输出信息
 */

```



### 8.9 super关键字

#### 8.9.1基本语法

![img](https://img-blog.csdnimg.cn/img_convert/6a19783b60eecdf51a07f51ab8d4db76.png)

子类B

```java
public class B extends A {

    public int n1 = 888;

    //编写测试方法
    public void test() {
        //super的访问不限于直接父类，如果爷爷类和本类中有同名的成员，也可以使用super去访问爷爷类的成员；
        // 如果多个基类(上级类)中都有同名的成员，使用super访问遵循就近原则。A->B->C

        System.out.println("super.n1=" + super.n1);
        super.cal();
    }

    //访问父类的属性 , 但不能访问父类的private属性 [案例]super.属性名
    public void hi() {

        System.out.println(super.n1 + " " + super.n2 + " " + super.n3 );
    }
    public void cal() {

        System.out.println("B类的cal() 方法...");
    }
    public void sum() {
        System.out.println("B类的sum()");
        //希望调用父类-A 的cal方法
        //这时，因为子类B没有cal方法，因此我可以使用下面三种方式

        //找cal方法时(cal() 和 this.cal())，顺序是:
        // (1)先找本类，如果有，则调用
        // (2)如果没有，则找父类(如果有，并可以调用，则调用)
        // (3)如果父类没有，则继续找父类的父类,整个规则，就是一样的,直到 Object类
        // 提示：如果查找方法的过程中，找到了，但是不能访问，也不会再往上找其他父类， 报错, cannot access
        //      如果查找方法的过程中，没有找到，则提示方法不存在
        //cal();
        this.cal(); //等价 cal

        //找cal方法(super.call()) 的顺序是不查找本类，直接查找父类，其他的规则一样
        //super.cal();

        //演示访问属性的规则
        //n1 和 this.n1 查找的规则是
        //(1) 先找本类，如果有，则调用
        //(2) 如果没有，则找父类(如果有，并可以调用，则调用)
        //(3) 如果父类没有，则继续找父类的父类,整个规则，就是一样的,直到 Object类
        // 提示：如果查找属性的过程中，找到了，但是不能访问，也不会再往上找其他父类，报错, cannot access
        //      如果查找属性的过程中，没有找到，则提示属性不存在
        System.out.println(n1);//888
        System.out.println(this.n1);//888

        //找n1 (super.n1) 的顺序是是不查找本类，直接查找父类属性，其他的规则一样
        System.out.println(super.n1);//100

    }
    //访问父类的方法，不能访问父类的private方法 super.方法名(参数列表);
    public void ok() {
        super.test100();
        super.test200();
        super.test300();
        //super.test400();//不能访问父类private方法
    }
    //访问父类的构造器(这点前面用过)：super(参数列表);只能放在构造器的第一句，只能出现一句！
    public  B() {
        //super();
        //super("jack", 10);
        super("jack");
    }
}

```

B的父类A

```java
public class A extends Base{
    //4个属性
    //public int n1 = 100;
    protected int n2 = 200;
    int n3 = 300;
    private int n4 = 400;

    public A() {}
    public A(String name) {}
    public A(String name, int age) {}

//    public void cal() {
//        System.out.println("A类的cal() 方法...");
//    }

    public void test100() {
    }

    protected void test200() {
    }

    void test300() {
    }

    private void test400() {
    }
}


```



A的父类Base

```java
public class Base { //父类是Object

    public int n1 = 999;
    public int age = 111;
    public void cal() {
        System.out.println("Base类的cal() 方法...");
    }
    public void eat() {
        System.out.println("Base类的eat().....");
    }
}

```



主程序

```java
public class Super01 {
    public static void main(String[] args) {
        B b = new B();//子类对象
        //b.sum();
        b.test();
    }
}
```



#### 8.9.3 super 给编程带来的便利/细节

![img](https://img-blog.csdnimg.cn/img_convert/281efb03886cca8b4e0151f105aed118.png)



![img](https://img-blog.csdnimg.cn/img_convert/0909b8181f40ef9600d3dbd2301a5751.png)



#### 8.9.4 super和this的比较

![img](https://img-blog.csdnimg.cn/img_convert/f1835093cc64fee0d202468c13b25bbf.png)



### 8.10 方法重写/覆盖(override)

#### 8.10.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/dc231457a74d2fdd178f05bfd1ed01cb.png)

#### 8.10.3 注意事项和使用细节

方法重写也叫方法覆盖，需要满足下面的条件

![img](https://img-blog.csdnimg.cn/img_convert/a4cae5da434c92b37ca8b2aad8acd773.png)

代码

```java
public class Animal { 
    public void cry() {
        System.out.println("动物叫唤..");
}


public Object m1() { 
    return null;
}


public String m2() { 
    return null;
}


public AAA m3() { 
    return null;
}
protected void eat() {


}
public class Dog extends Animal{
    //老韩解读
    //1. 因为Dog 是 Animal子类
    //2. Dog的 cry方法和 Animal的 cry定义形式一样(名称、返回类型、参数)
    //3. 这时我们就说 Dog的cry方法，重写了Animal的cry方法
    public void cry() {
        System.out.println("小狗汪汪叫..");
    }

    //细节: 子类方法的返回类型和父类方法返回类型一样，
    //      或者是父类返回类型的子类•比如 父类 返回类型是 Object ,
    //      子类方法返回类型是String
    public String m1() {
        return null;
    }
    
    //这里Object 不是 String的子类，因此编译错误
//    public Object m2() {
//        return null;
//    }

//    public BBB m3() {
//        return null;
//    }
    //细节: 子类方法不能缩小父类方法的访问权限 【演示】
    //public > protected > 默认>private
    public void eat() {//若为protected则报错，子类可以扩大父类的访问权限eg：父类：protected 子类: public

    }
}

class AAA {

}

class BBB extends AAA  {

}
```



#### 8.10.4 课堂练习

题1

重写和重载比较：

![img](https://img-blog.csdnimg.cn/img_convert/670d1fc99f6d160358f5736936f16976.png)

题2

1、 编写一个 Person 类，包括属性/private（name、age），构造器、方法 say(返回自我介绍的字符串）。

2、编写一个 Student 类，继承 Person 类，增加 id、score 属性/private，以及构造器，定义 say 方法(返回自我介绍的信息)。

3、在 main 中,分别创建 Person 和 Student 对象，调用 say 方法输出自我介绍



代码

父类

```java
package com.baseCode.override;
// 编写一个 Person 类，包括属性/private（name、age），构造器、方法 say(返回自我介绍的字符串）。
public class Person {
    private String name;
    private int age;
    public Person(String name,int age){
        this.name=name;
        this.age=age;

    }
    public String say(){
        return "name=" + name + " age=" + age;
    }
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

}

```

子类

```java
package com.baseCode.override;

import javax.xml.namespace.QName;

public class Student extends Person {
    private int Id;
    private double score;
    public Student(String name,int age,int Id,double score){
        super(name,age);
        this.Id=Id;
        this.score=score;

    }
    public String say(){
        return super.say()+" id="+Id+" score="+score;
    }
    public int getId() {
        return Id;
    }

    public void setId(int id) {
        Id = id;
    }

    public double getScore() {
        return score;
    }

    public void setScore(double score) {
        this.score = score;
    }
}

```

主程序

```java
package com.baseCode.override;
//在 main 中,分别创建 Person 和 Student 对象，调用 say 方法输出自我介绍
public class OverrideExercise {
    public static void main(String[] args) {
        Person person=new Person("jack",10);
        System.out.println(person.say());
        Student student= new Student("smith",20,12345,99.8);
        System.out.println(student.say());

    }
}

```



### 8.11 面向对象编程-多态(polymorphic)

#### 8.11.1 多[多种]态[状态]基本介绍

方法或对象具有多种形态。是面向对象的第三大特征，多态是建立在封装和继承基础之上的。

#### 8.11.2 多态的具体体现

1、 方法的多态 PloyMethod.java

重写和重载就体现多态 [案例说明：]

```java
public class PloyMethod {
    public static void main(String[] args) {
        //方法重载体现多态
        A a = new A();
        //这里我们传入不同的参数(利用重载)，就会调用不同sum方法，就体现多态
        System.out.println(a.sum(10, 20));
        System.out.println(a.sum(10, 20, 30));

        //方法重写体现多态，对象不同
        B b = new B();
        a.say();
        b.say();

    }
}
class B { //父类
    public void say() {
        System.out.println("B say() 方法被调用...");
    }
}
class A extends B {//子类
    public int sum(int n1, int n2){//和下面sum 构成重载
        return n1 + n2;
    }
    public int sum(int n1, int n2, int n3){
        return n1 + n2 + n3;
    }


    public void say() {
        System.out.println("A say() 方法被调用...");
    }
}
```



2、对象的多态 **(核心，困难，重点**）

![img](https://img-blog.csdnimg.cn/img_convert/d330ad118adb002c6350aebc0b2c8c85.png)

![img](https://img-blog.csdnimg.cn/img_convert/7897459b37003a63b52a5429a6cbdaf2.png)

代码

主类

```java
package com.hspedu.poly_.objectpoly_;

public class Animal {
    public void  cry() {
        System.out.println("Animal cry() 动物在叫....");
    }
}

```

子类dog

```java
package com.hspedu.poly_.objectpoly_;

public class Dog extends Animal {

    public void cry() {
        System.out.println("Dog cry() 小狗汪汪叫...");
    }
}

```

子类cat

```java
package com.hspedu.poly_.objectpoly_;

public class Cat extends Animal {

    public void cry() {
        System.out.println("Cat cry() 小猫喵喵叫...");
    }
}

```

主程序

```java
package com.hspedu.poly_.objectpoly_;

public class PolyObject {
    public static void main(String[] args) {
        //体验对象多态特点
        //animal 编译类型就是 Animal , 运行类型 Dog
        Animal animal = new Dog();
        //因为运行时 , 执行到改行时，animal运行类型是Dog,所以cry就是Dog的cry
        animal.cry(); //小狗汪汪叫

        //animal 编译类型 Animal,运行类型就是 Cat
        animal = new Cat();
        animal.cry(); //小猫喵喵叫
    }
}

```



#### 8.11.5 多态注意事项和细节讨论

com.hspedu.poly*.detail* 包 : PolyDetail.java

多态的**前提是**：两个对象(类)存在继承关系

多态的向上转型

![img](https://img-blog.csdnimg.cn/img_convert/7f0040aa77d4099856defa4f4d06d90d.png)

多态向下转型

![img](https://img-blog.csdnimg.cn/img_convert/594940be5dee71c6a6d30f10b9f123b4.png)



案例

主类

```java
package com.hspedu.poly_.detail_;

public class Animal {
    String name = "动物";
    int age = 10;
    public void sleep(){
        System.out.println("睡");
    }
    public void run(){
        System.out.println("跑");
    }
    public void eat(){
        System.out.println("吃");
    }
    public void show(){
        System.out.println("hello,你好");
    }

}
```



子类dog

```java
package com.hspedu.poly_.detail_;

public class Dog extends Animal {//Dog是Animal的子类
}

```

子类cat

```java
package com.hspedu.poly_.detail_;

public class Cat extends Animal {
    public void eat(){//方法重写
        System.out.println("猫吃鱼");
    }
    public void catchMouse(){//Cat特有方法
        System.out.println("猫抓老鼠");
    }
}

```



主程序

```java
package com.hspedu.poly_.detail_;

public class PolyDetail {
    public static void main(String[] args) {

        //向上转型: 父类的引用指向了子类的对象
        //语法：父类类型引用名 = new 子类类型();
        Animal animal = new Cat();
        Object obj = new Cat();//可以吗? 可以 Object 也是 Cat的父类

        //向上转型调用方法的规则如下:
        //(1)可以调用父类中的所有成员(需遵守访问权限)
        //(2)但是不能调用子类的特有的成员
        //(#)因为在编译阶段，能调用哪些成员,是由编译类型来决定的
        //animal.catchMouse();错误 不能调用子类特有的成员
        //(4)最终运行效果看子类(运行类型)的具体实现, 即调用方法时，按照从子类(运行类型)开始查找方法
        //，然后调用，规则我前面我们讲的方法调用规则一致。
        // 从最小 子类往上查找（和前面方法调用方法和规则一致）
        animal.eat();//猫吃鱼..
        animal.run();//跑
        animal.show();//hello,你好
        animal.sleep();//睡

        //老师希望，可以调用Cat的 catchMouse方法
        //多态的向下转型
        //(1)语法：子类类型 引用名 =（子类类型）父类引用;
        //问一个问题? cat 的编译类型 Cat,运行类型是 Cat
        Cat cat = (Cat) animal;//原来animal就是指向cat，可以执行此操作
        cat.catchMouse();//猫抓老鼠,此时可以调用子类特有成员 
        //或者两个合并写出((Cat)animal).catchMouse()
        //(2)要求父类的引用必须指向的是当前目标类型的对象
        Dog dog = (Dog) animal; //可以吗？不可以，原来animal就是指向cat，此时不可强转
        //子类与子类之间没有什么关系
        System.out.println("ok~~");
    }
}


```





属性没有重写之说！属性的值看编译类型 PolyDetail02.java

```java
package com.hspedu.poly_.detail_;

public class PolyDetail02 {
    public static void main(String[] args) {
        //属性没有重写之说！属性的值看编译类型
        Base base = new Sub();//向上转型
        System.out.println(base.count);// ？ 看编译类型Base 结果：10
        Sub sub = new Sub();
        System.out.println(sub.count);//?  20
    }
}

class Base { //父类
    int count = 10;//属性
}
class Sub extends Base {//子类
    int count = 20;//属性
}
```



instanceOf 比较操作符，用于判断对象的运行类型是否为 XX 类型或XX 类型的子类型【举例说明】PolyDetail03.java

```java
package com.hspedu.poly_.detail_;

public class PolyDetail03 {
    public static void main(String[] args) {
        BB bb = new BB();
        System.out.println(bb instanceof  BB);// true
        System.out.println(bb instanceof  AA);// true

        //aa 编译类型 AA, 运行类型是BB
        //BB是AA子类
        AA aa = new BB();
        System.out.println(aa instanceof AA);
        System.out.println(aa instanceof BB);//ture BB是AA的子类型

        Object obj = new Object();
        System.out.println(obj instanceof AA);//false
        String str = "hello";
        //System.out.println(str instanceof AA);
        System.out.println(str instanceof Object);//true
    }
}

class AA {} //父类
class BB extends AA {}//子类
```



#### 8.11.6 课堂练习

请说出下面的每条语言，哪些是正确的，哪些是错误的，为什么?

第1题

![img](https://img-blog.csdnimg.cn/img_convert/eade531970c4f668d687112bb52da9a9.png)

第2题 PolyExercise02.java

![img](https://img-blog.csdnimg.cn/img_convert/c833be4aae98904f03ae8ab8e0cce5d6.png)



b.count //访问属性看编译类型b的编译类型为Base->属性count=10；

Base b = s;//s和b都是指向sub(对象)地址

b.display(); //其运行对象是sub





#### 8.11.7 java 的动态绑定机制(非常非常重要)

![img](https://img-blog.csdnimg.cn/img_convert/425ba69059cb031cdbfe0454d072bdfb.png)

a.sum() 运行类型为B()

若注销掉子类的sum,B类无sum找父类A的sum方法

```java
public class DynamicBinding {
    public static void main(String[] args) {
        //a 的编译类型 A, 运行类型 B
        A a = new B();//向上转型
        System.out.println(a.sum());//?40 -> 30
        System.out.println(a.sum1());//?30-> 20
    }
}

class A {//父类
    public int i = 10;
    //动态绑定机制:

    public int sum() {//父类sum()
        //当调用对象方法的时候，该方法会和该对象的内存地址/运行类型绑定
        return getI() + 10;//20 + 10
    }

    public int sum1() {//父类sum1()
        //当注销掉子类的sum1，从父类找方法sum1
        //调用对象属性时，没有动态绑定，哪里声明哪里使用，i=10；
        return i + 10;//10 + 10
    }

    public int getI() {//父类getI
        return i;
    }
}

class B extends A {//子类
    public int i = 20;

//    public int sum() {
//        return i + 20;
//    }

    public int getI() {//子类getI()
        return i;
    }

//    public int sum1() {
//        return i + 10;
//    }
}

```



#### 8.11.8 多态的应用

1、多态数组 com.hspedu.poly*.polyarr* 包 PloyArray.java

数组的定义类型为父类类型，里面保存的实际元素类型为子类类型

应用实例:现有一个继承结构如下：要求创建 1 个 Person 对象、2 个 Student 对象和 2 个 Teacher 对象, 统一放在数组中，并调用每个对象 say 方法.

应用实例升级：如何调用子类特有的方法，比如 Teacher 有一个 teach , Student 有一个 study



学生子类

```java
package com.hspedu.poly_.polyarr_;

public class Student extends Person {
    private double score;

    public Student(String name, int age, double score) {
        super(name, age);
        this.score = score;
    }

    public double getScore() {
        return score;
    }

    public void setScore(double score) {
        this.score = score;
    }
    //重写父类say

    @Override
    public String say() {
        return "学生 " + super.say() + " score=" + score;
    }
    //特有的方法
    public void study() {
        System.out.println("学生 " + getName() + " 正在学java...");
    }
}

```



老师子类

```java
package com.hspedu.poly_.polyarr_;

public class Teacher extends Person {
    private double salary;

    public Teacher(String name, int age, double salary) {
        super(name, age);
        this.salary = salary;
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }
    //写重写父类的say方法

    @Override
    public String say() {
        return "老师 " + super.say() + " salary=" + salary;
    }
    //特有方法
    public void teach() {
        System.out.println("老师 " + getName() + " 正在讲java课程...");
    }
}

```



Person主类

```java
package com.hspedu.poly_.polyarr_;

public class Person {//父类
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String say() {//返回名字和年龄
        return name + "\t" + age;
    }
}

```



主程序

```java
package com.hspedu.poly_.polyarr_;

public class PloyArray {
    public static void main(String[] args) {
        //应用实例:现有一个继承结构如下：要求创建1个Person对象、
        // 2个Student 对象和2个Teacher对象, 统一放在数组中，并调用每个对象say方法

        Person[] persons = new Person[5];
        persons[0] = new Person("jack", 20);
        persons[1] = new Student("mary", 18, 100);
        persons[2] = new Student("smith", 19, 30.1);
        persons[3] = new Teacher("scott", 30, 20000);
        persons[4] = new Teacher("king", 50, 25000);

        //循环遍历多态数组，调用say
        for (int i = 0; i < persons.length; i++) {
            //老师提示: person[i] 编译类型是 Person ,运行类型是是根据实际情况有JVM来判断
            System.out.println(persons[i].say());//动态绑定机制
            //persons[i].teach();
            //persons[i].study();//编译类型是Person，Person中无这两个方法
            
            //这里大家聪明. 使用 类型判断 + 向下转型.
            if(persons[i]  instanceof  Student) {//判断person[i] 的运行类型是不是Student
                Student student = (Student)persons[i];//向下转型
                student.study();
                //小伙伴也可以合成一条语句 ((Student)persons[i]).study();
            } else if(persons[i] instanceof  Teacher) {
                Teacher teacher = (Teacher)persons[i];
                teacher.teach();
            } else if(persons[i] instanceof  Person){
                //System.out.println("你的类型有误, 请自己检查...");
            } else {
                System.out.println("你的类型有误, 请自己检查...");
            }

        }

    }
}

```



2、多态参数

![img](https://img-blog.csdnimg.cn/img_convert/68614cb236b54ec97d281d191894750d.png)

worker 子类

```java
package com.hspedu.poly_.polyparameter_;

public class Worker extends Employee {
    public Worker(String name, double salary) {
        super(name, salary);
    }
    public void work() {
        System.out.println("普通员工 " + getName() + " is working");
    }

    @Override
    public double getAnnual() { //因为普通员工没有其它收入，则直接调用父类方法
        return super.getAnnual();
    }
}

```



manager 子类

```java
package com.hspedu.poly_.polyparameter_;

public class Manager extends Employee{

    private double bonus;

    public Manager(String name, double salary, double bonus) {
        super(name, salary);
        this.bonus = bonus;
    }

    public double getBonus() {
        return bonus;
    }

    public void setBonus(double bonus) {
        this.bonus = bonus;
    }
    public void manage() {
        System.out.println("经理 " + getName() + " is managing");
    }
    //重写获取年薪方法
    @Override
    public double getAnnual() {
        return super.getAnnual() + bonus;
    }
}

```



Employer 主类

```java
package com.hspedu.poly_.polyparameter_;

public class Employee {
    private String name;
    private double salary;

    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }
    //得到年工资的方法
    public double getAnnual() {
        return 12 * salary;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }
}

```



**主程序**

```java
package com.hspedu.poly_.polyparameter_;

public class PloyParameter {
    public static void main(String[] args) {
        Worker tom = new Worker("tom", 2500);
        Manager milan = new Manager("milan", 5000, 200000);
        //需要调用主程序中的方法，创建主程序类
        PloyParameter ployParameter = new PloyParameter(); 
        ployParameter.showEmpAnnual(tom);
        ployParameter.showEmpAnnual(milan);

        ployParameter.testWork(tom);
        ployParameter.testWork(milan);

    }

    //showEmpAnnual(Employee e)
    //实现获取任何员工对象的年工资,并在main方法中调用该方法 [e.getAnnual()]
    public void showEmpAnnual(Employee e) {
        System.out.println(e.getAnnual());//动态绑定机制.
    }
    //添加一个方法，testWork,如果是普通员工，则调用work方法，如果是经理，则调用manage方法
    public void testWork(Employee e) {
        if(e instanceof  Worker) {
            ((Worker) e).work();//有向下转型操作
        } else if(e instanceof Manager) {
            ((Manager) e).manage();//有向下转型操作
        } else {
            System.out.println("不做处理...");
        }
    }
}

```



### 8.12 Object 类详解

#### 8.12.1 equals 方法

==和 equals 的对比 [面试题]

![img](https://img-blog.csdnimg.cn/img_convert/3a23b1e6db8fba456e15c2a6e444024b.png)

![img](https://img-blog.csdnimg.cn/img_convert/f34b500773d8449e8d01aa7638c4d1d9.png)



```java
package com.hspedu.object_;


public class Equals01 {


    public static void main(String[] args) {
        A a = new A();
        A b = a;
        A c = b;
        System.out.println(a == c);//true System.out.println(b == c);//true B bObj = a;
        System.out.println(bObj == c);//true
        int num1 = 10;
        double num2 = 10.0;
        System.out.println(num1 == num2);//基本数据类型，判断值是否相等


//equals 方法，源码怎么查看.
//把光标放在 equals 方法，直接输入 ctrl+b
//如果你使用不了. 自己配置. 即可使用.


带大家看看 Jdk 的源码 String 类的 equals 方法
把 Object 的 equals 方法重写了,变成了比较两个字符串值是否相同
//        public boolean equals (Object anObject){
//            if (this == anObject) {//如果是同一个对象
//                return true;//返回 true
//            }
//            if (anObject instanceof String) {//判断类型
//                String anotherString = (String) anObject;//向下转型int n = value.length;
//                if (n == anotherString.value.length) {//如果长度相同char v1[] = value;
//                    char v2[] = anotherString.value;
//                    int i = 0;
//                    while (n-- != 0) {//然后一个一个的比较字符
//                        if (v1[i] != v2[i]) {
//                          return false;
//                    }
                            
//                        i++;
//                    }
//                    return true;//如果两个字符串的所有字符都相等，则返回 true
//                }
//            }
//            return false;//如果比较的不是字符串，则直接返回 false
//        }


        "hello".equals("abc");


//看看 Object 类的 equals 是
//即 Object 的 equals 方法默认就是比较对象地址是否相同
//也就是判断两个对象是不是同一个对象. public boolean equals(Object obj) {
        return (this == obj);
    }


    //从源码可以看到 Integer 也重写了 Object 的 equals 方法,
//变成了判断两个值是否相同public boolean equals(Object obj) {
//    if(obj instanceof Integer){
//        return value == ((Integer) obj).intValue();
//    }
//     return false;
//}
    Integer integer1 = new Integer(1000);
    Integer integer2 = new Integer(1000);
        System.out.println(integer1==integer2);//false 不同的对象对应地址不同
    System.out.println(integer1.equals(integer2));//true

    String str1 = new String("hspedu");
    String str2 = new String("hspedu");
                System.out.println(str1==str2);//false 判断是否为同一个对象
                System.out.println(str1.equals(str2));//true 判断值是否相同


}
                }


class B {
}

class A extends B {
}
```





#### 8.12.2 如何重写equals 方法

课堂练习：

应用实例: 判断两个Person 对象的内容是否相等，如果两个 Person 对象的各个属性值都一样，则返回 true，反之 false

代码

```java
package com.hspedu.object_;

public class EqualsExercise01 {
    public static void main(String[] args) {
        Person person1 = new Person("jack", 10, '男');
        Person person2 = new Person("jack", 10, '男');

        System.out.println(person1.equals(person2));//假
    }
}
//判断两个Person对象的内容是否相等，
//如果两个Person对象的各个属性值都一样，则返回true，反之false
class Person{ //extends Object
    private String name;
    private int age;
    private char gender;

    //重写Object 的 equals方法
    public boolean equals(Object obj) {//Object obj系统自带
        //判断如果比较的两个对象是同一个对象，则直接返回true
        if(this == obj) {
            return true;
        }
        //类型判断
        if(obj instanceof  Person) {//是Person，我们才比较

            //进行 向下转型, 因为我需要得到obj的 各个属性
            Person p = (Person)obj;
            return this.name.equals(p.name) && this.age == p.age && this.gender == p.gender;
        }
        //如果不是Person ，则直接返回false
        return false;

    }

    public Person(String name, int age, char gender) {
        this.name = name;
        this.age = age;
        this.gender = gender;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public char getGender() {
        return gender;
    }

    public void setGender(char gender) {
        this.gender = gender;
    }

}

```



EqualsExercise02 .java

```java
public class EqualsExercise02 {
    public static void main(String[] args) {


        Person_ p1 = new Person_(); p1.name = "hspedu";
        Person_ p2 = new Person_(); p2.name = "hspedu";

        System.out.println(p1==p2); //False 
        System.out.println(p1.name .equals( p2.name));//T 字符串重写比较内容是否相同
        System.out.println(p1.equals(p2));//False 
       //person类对于equals并没有重写，来自Object的equals，默认判断对象是否相同

        String s1 = new String("asdf");
        String s2 = new String("asdf");
        System.out.println(s1.equals(s2));//T   
        System.out.println(s1==s2); //F

    }
}


class Person_{//类
        public String name;
}


```





代码如下 EqualsExercise03.java

```java
//代码如下 EqualsExercise03.java 2min int it = 65;
float fl = 65.0f;
System.out.println(“65 和 65.0f 是否相等？” + (it == fl));//T
char ch1 = ‘A’; char ch2 = 12;
System.out.println(“65 和‘A’是否相等？” + (it == ch1));//T 
System.out.println(“12 和 ch2 是否相等？” + (12 == ch2));//T

String str1 = new String("hello"); 
String str2 = new String("hello");
System.out.println("str1 和 str2 是否相等？"+ (str1 == str2)); //F


System.out.println(“str1 是否 equals str2？”+(str1.equals(str2)));//T System.out.println(“hello” == new java.sql.Date()); //编译错误,不是一个数据类型

```



#### 8.12.4 hashCode 方法

![img](https://img-blog.csdnimg.cn/img_convert/4638acf66260f26c5631bff438a9509e.png)

老韩的 6 个小结:

1. 提高具有哈希结构的容器的效率！
2. 两个引用，如果指向的是同一个对象，则哈希值肯定是一样的！
3. 两个引用，如果指向的是不同对象，则哈希值是不一样的
4. 哈希值主要根据地址号来的， 不能完全将哈希值等价于地址。
5. 案例演示[HashCode_.java]: obj.hashCode() [测试：A obj1 = new A(); A obj2 = new A(); A obj3 = obj1]
6. 后面在集合，中 hashCode 如果需要的话，也会重写, 在讲解集合时，老韩在说如何重写 hashCode()



```java
package com.hspedu.object_;


    public class HashCode_ {
    public static void main(String[] args) {


        AA aa = new AA(); 
        AA aa2 = new AA();
        AA aa3 = aa;
        System.out.println("aa.hashCode()=" + aa.hashCode());
        System.out.println("aa2.hashCode()=" + aa2.hashCode()); 
        System.out.println("aa3.hashCode()=" + aa3.hashCode());



    }
}
class AA {}

```



#### 8.12.5 toString 方法

![img](https://img-blog.csdnimg.cn/img_convert/352a5167d8e7cf05ce66b24cb4ed0521.png)



代码

```java
package com.hspedu.object_;

public class ToString_ {
    public static void main(String[] args) {

        /*
        Object的toString() 源码
        (1)getClass().getName() 类的全类名(包名+类名 )
        (2)Integer.toHexString(hashCode()) 将对象的hashCode值转成16进制字符串
        public String toString() {
            return getClass().getName() + "@" + Integer.toHexString(hashCode());
        }
         */

        Monster monster = new Monster("小妖怪", "巡山的", 1000);
        //没重写toSting之前默认执行系统输出
        // return getClass().getName() + "@" + Integer.toHexString(hashCode());
        System.out.println(monster.toString() + " hashcode=" + monster.hashCode());

        System.out.println("==当直接输出一个对象时，toString 方法会被默认的调用==");
        System.out.println(monster); //等价 monster.toString()

    }
}

class Monster {
    private String name;
    private String job;
    private double sal;

    public Monster(String name, String job, double sal) {
        this.name = name;
        this.job = job;
        this.sal = sal;
    }

    //重写toString方法, 输出对象的属性
    //使用快捷键即可 alt+insert -> toString

    @Override
    public String toString() {
        return "Monster{" +
                "name='" + name + '\'' +
                ", job='" + job + '\'' +
                ", sal=" + sal +
                '}';
    }

    @Override
    protected void finalize() throws Throwable {
        System.out.println("fin..");
    }
}
//结果
Monster{name='小妖怪', job='巡山的', sal=1000.0} hashcode=1975012498
==当直接输出一个对象时，toString 方法会被默认的调用==
Monster{name='小妖怪', job='巡山的', sal=1000.0}


```



#### 8.12.6 finalize 方法

![img](https://img-blog.csdnimg.cn/img_convert/4f22c4f5576fac3b52797f3756048786.png)

代码

```java
package com.hspedu.object_;

//演示 Finalize的用法
public class Finalize_ {
    public static void main(String[] args) {

        Car bmw = new Car("宝马");
        //这时 car对象就是一个垃圾,垃圾回收器就会回收(销毁)对象, 在销毁对象前，会调用该对象的finalize方法
        //,程序员就可以在 finalize中，写自己的业务逻辑代码(比如释放资源：数据库连接,或者打开文件..)
        //,如果程序员不重写 finalize,那么就会调用 Object类的 finalize, 即默认处理
        //,如果程序员重写了finalize, 就可以实现自己的逻辑
        bmw = null;//不会马上就执行垃圾调用
        System.gc();//主动调用垃圾回收器

        System.out.println("程序退出了....");
    }
}
class Car {
    private String name;
    //属性, 资源。。
    public Car(String name) {
        this.name = name;
    }
    //重写finalize
    //使用快捷键即可 alt+insert ->finalize 
    @Override
    protected void finalize() throws Throwable {
        System.out.println("我们销毁 汽车" + name );
        System.out.println("释放了某些资源...");

    }
}

```



### 8.13 断点调试(debug)

#### 8.13.1 一个实际需求

![img](https://img-blog.csdnimg.cn/img_convert/65ff5636a9b3b19aa76058e5ed29e6b0.png)



#### 8.13.2 断点调试介绍

![img](https://img-blog.csdnimg.cn/img_convert/53efd6ad3d6b1e063020ac982733f4ac.png)



#### 8.13.3 断点调试的快捷键

![img](https://img-blog.csdnimg.cn/img_convert/0cb66535613435200ffc59d9ef9945ea.png)

![img](https://img-blog.csdnimg.cn/img_convert/b7dc55eda7d4aa0a7634a0aa21b2cf40.png)

#### 8.13.4 断点调试应用案例

1、案例1

com.hspedu.debug_ 包 Debug01.java

2、案例2

Debug02.java

3、案例3

演示如何追源码，看看 java 设计者是怎么实现的。(提高编程思想)。小技巧：将光标放在某个变量上，可以看到最新的数据。Debug03.java

![img](https://img-blog.csdnimg.cn/img_convert/e595a9ae3a6471615f28b5a4d498edeb.png)



操作图：

![img](https://img-blog.csdnimg.cn/img_convert/0c9923384331dbf911e67ff8bd482b10.png)





4、案例4



![img](https://img-blog.csdnimg.cn/img_convert/c8138f436bc084b1fd600268700bc99c.png)



#### 8.13.6 断点调试课后练习

![img](https://img-blog.csdnimg.cn/img_convert/6fa598ac11958c822dc5d34dcb08e414.png)

具体操作看视频

```java
package com.hspedu.debug_;

//debug对象创建的过程，加深对调试的理解
public class DebugExercise {
    public static void main(String[] args) {
        //创建对象的流程
        //(1) 加载 Person类信息
        //(2) 初始化 2.1默认初始化, 2.2 显式初始化 2.3 构造器初始化
        //(3) 返回对象的地址
        Person jack = new Person("jack", 20);
        System.out.println(jack);//jack等同jack.toString()

    }
}
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}

```



动态转移机制

看 package com.hspedu.poly*.dynamic*;

用debug看具体步骤





### 8.14 项目-零钱通

#### 8.14.1 项目开发流程说明

#### 8.14.2 项目需求和界面





#### 8.14.3 化繁为简

1. 先完成显示菜单，并可以选择

2. 完成零钱通明细.

3. 完成收益入账

4. 消费

5. 退出

   

#### 8.14.4 项目代码的实现

![img](https://img-blog.csdnimg.cn/img_convert/aeb2469582308586c6d057b3f62991d4.png)

```java
package com.hspedu.smallchange;

import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Scanner;

public class SmallChangeSys {

    //化繁为简
    //1. 先完成显示菜单，并可以选择菜单，给出对应提示
    //2. 完成零钱通明细
    //3. 完成收益入账
    //4. 消费
    //5. 退出
    //6. 用户输入4退出时，给出提示"你确定要退出吗? y/n"，必须输入正确的y/n ，否则循环输入指令，直到输入y 或者 n
    //7. 在收益入账和消费时，判断金额是否合理，并给出相应的提示
    public static void main(String[] args) {

        //定义相关的变量
        boolean loop = true;
        Scanner scanner = new Scanner(System.in);
        String key = "";

        //2. 完成零钱通明细
        //老韩思路, (1) 可以把收益入账和消费，保存到数组 (2) 可以使用对象 (3) 简单的话可以使用String拼接
        String details = "-----------------零钱通明细------------------";

        //3. 完成收益入账  完成功能驱动程序员增加新的变化和代码
        //老韩思路, 定义新的变量
        double money = 0;
        double balance = 0;
        Date date = null; // date 是 java.util.Date 类型，表示日期
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm"); //可以用于日期格式化的

        //4. 消费
        //定义新变量，保存消费的原因
        String note = "";
        do {

            System.out.println("\n================零钱通菜单===============");
            System.out.println("\t\t\t1 零钱通明细");
            System.out.println("\t\t\t2 收益入账");
            System.out.println("\t\t\t3 消费");
            System.out.println("\t\t\t4 退     出");

            System.out.print("请选择(1-4): ");
            key = scanner.next();

            //使用switch 分支控制
            switch (key) {
                case "1":
                    System.out.println(details);
                    break;
                case "2":
                    System.out.print("收益入账金额:");
                    money = scanner.nextDouble();
                    //money 的值范围应该校验 -》 一会在完善
                    //老师思路, 编程思想
                    //找出不正确的金额条件，然后给出提示, 就直接break
                    if(money <= 0) {
                        System.out.println("收益入账金额 需要 大于 0");
                        break;
                    }
                    //找出正确金额的条件
                    balance += money;
                    //拼接收益入账信息到 details
                    date = new Date(); //获取当前日期
                    details += "\n收益入账\t+" + money + "\t" + sdf.format(date) + "\t" + balance;


                    break;
                case "3":
                    System.out.print("消费金额:");
                    money = scanner.nextDouble();
                    //money 的值范围应该校验 -》 一会在完善
                    //找出金额不正确的情况
                    //过关斩将 校验方式.
                    if(money <= 0 || money > balance) {
                        System.out.println("你的消费金额 应该在 0-" + balance);
                        break;
                    }
                    System.out.print("消费说明:");
                    note = scanner.next();
                    balance -= money;
                    //拼接消费信息到 details
                    date = new Date(); //获取当前日期
                    details += "\n" + note + "\t-" + money + "\t" + sdf.format(date) + "\t" + balance;
                    break;
                case "4":
                    //用户输入4退出时，给出提示"你确定要退出吗? y/n"，必须输入正确的y/n ，
                    // 否则循环输入指令，直到输入y 或者 n
                    // 老韩思路分析
                    // (1) 定义一个变量 choice, 接收用户的输入
                    // (2) 使用 while + break, 来处理接收到的输入时 y 或者 n
                    // (3) 退出while后，再判断choice是y还是n ,就可以决定是否退出
                    // (4) 建议一段代码，完成一个小功能，尽量不要混在一起
                    String choice = "";
                    while (true) { //要求用户必须输入y/n ,否则就一直循环
                        System.out.println("你确定要退出吗? y/n");
                        choice = scanner.next();
                        if ("y".equals(choice) || "n".equals(choice)) {
                            break;
                        }
                        //第二个方案
//                        if("y".equals(choice)) {
//                            loop = false;
//                            break;
//                        } else if ("n".equals(choice)) {
//                            break;
//                        }
                    }

                    //当用户退出while ,进行判断
                    if (choice.equals("y")) {
                        loop = false;
                    }
                    break;
                default:
                    System.out.println("选择有误，请重新选择");
            }

        } while (loop);

        System.out.println("-----退出了零钱通项目-----");

    }
}

```



#### 8.14.5 项目代码实现改进

![img](https://img-blog.csdnimg.cn/img_convert/b9031f432e328de358b16fb1edabf63c.png)



```java
package com.hspedu.smallchange.oop;

/**
 * 这里我们直接调用SmallChangeSysOOP 对象，显示主菜单即可
 */
public class SmallChangeSysApp {

    public static void main(String[] args) {
        System.out.println("====hello公司====");
        new SmallChangeSysOOP().mainMenu();
    }
}

```



```java
package com.hspedu.smallchange.oop;

import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Scanner;

/**
 * 该类是完成零钱通的各个功能的类
 * 使用OOP(面向对象编程)
 * 将各个功能对应一个方法.
 */
public class SmallChangeSysOOP {

    //属性..
    //定义相关的变量
    boolean loop = true;
    Scanner scanner = new Scanner(System.in);
    String key = "";

    //2. 完成零钱通明细
    //老韩思路, (1) 可以把收益入账和消费，保存到数组 (2) 可以使用对象 (3) 简单的话可以使用String拼接
    String details = "-----------------零钱通明细------------------";

    //3. 完成收益入账  完成功能驱动程序员增加新的变化和代码
    //老韩思路, 定义新的变量
    double money = 0;
    double balance = 0;
    Date date = null; // date 是 java.util.Date 类型，表示日期
    SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm"); //可以用于日期格式化的

    //4. 消费
    //定义新变量，保存消费的原因
    String note = "";

    //先完成显示菜单，并可以选择
    public void mainMenu() {
        do {

            System.out.println("\n================零钱通菜单(OOP)===============");
            System.out.println("\t\t\t1 零钱通明细");
            System.out.println("\t\t\t2 收益入账");
            System.out.println("\t\t\t3 消费");
            System.out.println("\t\t\t4 退     出");

            System.out.print("请选择(1-4): ");
            key = scanner.next();

            //使用switch 分支控制
            switch (key) {
                case "1":
                    this.detail();
                    break;
                case "2":
                    this.income();
                    break;
                case "3":
                    this.pay();
                   break;
                case "4":
                    this.exit();
                    break;
                default:
                    System.out.println("选择有误，请重新选择");
            }

        } while (loop);
    }

    //完成零钱通明细
    public void detail() {
        System.out.println(details);
    }
    //完成收益入账
    public void income() {
        System.out.print("收益入账金额:");
        money = scanner.nextDouble();
        //money 的值范围应该校验 -》 一会在完善
        //老师思路, 编程思想
        //找出不正确的金额条件，然后给出提示, 就直接return
        if(money <= 0) {
            System.out.println("收益入账金额 需要 大于 0");
            return; //退出方法，不在执行后面的代码。
        }
        //找出正确金额的条件
        balance += money;
        //拼接收益入账信息到 details
        date = new Date(); //获取当前日期
        details += "\n收益入账\t+" + money + "\t" + sdf.format(date) + "\t" + balance;

    }
    //消费
    public void pay() {
        System.out.print("消费金额:");
        money = scanner.nextDouble();
        //money 的值范围应该校验 -》 一会在完善
        //找出金额不正确的情况
        //过关斩将 校验方式.
        if(money <= 0 || money > balance) {
            System.out.println("你的消费金额 应该在 0-" + balance);
            return;
        }
        System.out.print("消费说明:");
        note = scanner.next();
        balance -= money;
        //拼接消费信息到 details
        date = new Date(); //获取当前日期
        details += "\n" + note + "\t-" + money + "\t" + sdf.format(date) + "\t" + balance;
    }

    //退出
    public void exit() {
        //用户输入4退出时，给出提示"你确定要退出吗? y/n"，必须输入正确的y/n ，
        // 否则循环输入指令，直到输入y 或者 n
        // 老韩思路分析
        // (1) 定义一个变量 choice, 接收用户的输入
        // (2) 使用 while + break, 来处理接收到的输入时 y 或者 n
        // (3) 退出while后，再判断choice是y还是n ,就可以决定是否退出
        // (4) 建议一段代码，完成一个小功能，尽量不要混在一起
        String choice = "";
        while (true) { //要求用户必须输入y/n ,否则就一直循环
            System.out.println("你确定要退出吗? y/n");
            choice = scanner.next();
            if ("y".equals(choice) || "n".equals(choice)) {
                break;
            }
            //第二个方案
//                        if("y".equals(choice)) {
//                            loop = false;
//                            break;
//                        } else if ("n".equals(choice)) {
//                            break;
//                        }
        }

        //当用户退出while ,进行判断
        if (choice.equals("y")) {
            loop = false;
        }
    }
}

```





### 8.15 本章作业

![img](https://img-blog.csdnimg.cn/img_convert/745395537006f7a7a2149fbdcfeb94c2.png)

默认不同包的子类不可访问



![img](https://img-blog.csdnimg.cn/img_convert/082c4a67425e4fd4eaeff0435eae2a3a.png)



![img](https://img-blog.csdnimg.cn/img_convert/2991302431a0ee43b0af2219040017bf.png)





![img](https://img-blog.csdnimg.cn/img_convert/5bd01266772ca59ac9bf984ba6f61d02.png)



![img](https://img-blog.csdnimg.cn/img_convert/c1c8b88315daf2c80d943900181ccdfc.png)

super那章有具体讲解

this也是先本级再往父级走，super直接往父级走

this遵循就近原则，找到最近的，更高级的属性或者方法不会再去调用



![img](https://img-blog.csdnimg.cn/img_convert/bbb9aefc5cf78293e2b1a0408b09d3e1.png)

```java
package com.hspedu.homework;

public class Homework07 {
    public static void main(String[] args)  {
        //老韩分析
        //1. new Demo()
        new Demo().test(); //先创建匿名对象Demo，先看Demo(),再看Demo().test()及Demo()中的test()方法
        new Demo("john").test();//匿名
    }


}
class Test{ //父类
    String name = "Rose";
    Test(){
        System.out.println("Test");//(1)
    }
    Test(String name){//name john
        this.name = name;//这里把父类的 name 修改 john
    }
}
class Demo extends Test{//子类
    String name="Jack";
    Demo()  {
        super();
        System.out.println("Demo");//(2)
    }
    Demo(String s){
        super(s);
    }
    public void test(){
        System.out.println(super.name);//(3) Rose (5) john
        System.out.println(this.name);//(4) Jack (6) Jack
    }

}
//结果
Test
Demo
Rose
Jack
john
Jack
```



![img](https://img-blog.csdnimg.cn/img_convert/d089aa4817b79ea274aa3582bfc10c5b.png)



```java
package com.hspedu.homework;

public class BankAccount {//父类
    private double balance ;//余额
    public BankAccount(double initialBalance) {
        this.balance = initialBalance;
    }
    //存款
    public void deposit(double amount)  {
        balance += amount;
    }
    //取款
    public void withdraw(double amount)  {
        balance -= amount;
    }

    public double getBalance() {
        return balance;
    }

    public void setBalance(double balance) {
        this.balance = balance;
    }
}
================================================================
package com.hspedu.homework;


/*
在上面类的基础上扩展 新类CheckingAccount对每次存款和取款都收取1美元的手续费
 */
public class CheckingAccount extends BankAccount{//新的账号
    //属性
    public CheckingAccount(double initialBalance) {
        super(initialBalance);
    }

    @Override
    public void deposit(double amount) {//存款
        super.deposit(amount - 1);//巧妙的使用了父类的 deposit
        //1 块钱转入银行的账号
    }

    @Override
    public void withdraw(double amount) {//取款
        super.withdraw(amount + 1);
        //1 块钱转入银行的账号
    }
}
=====================================================================
package com.hspedu.homework;

/*
扩展前一个练习的BankAccount类，
新类SavingsAccount每个月都有利息产生(earnMonthlyInterest方法被调用)，
并且有每月三次免手续费的存款或取款。在earnMonthlyInterest方法中重置交易计数
 */
public class SavingsAccount extends BankAccount {

    //老韩分析
    //新增加属性
    private int count = 3;
    private double rate = 0.01;//利率

    public void earnMonthlyInterest() {//每个月初，我们统计上个月的利息，同时将count=3
        count = 3;//
        super.deposit(getBalance() * rate);
    }

    @Override
    public void deposit(double amount) {
        //判断是否还可以免手续费
        if(count > 0) {
            super.deposit(amount);
        } else {
            super.deposit(amount - 1);//1 块转入银行
        }
        count--;//减去一次
    }

    @Override
    public void withdraw(double amount) {//取款
        //判断是否还可以免手续费
        if(count > 0) {
            super.withdraw(amount);
        } else {
            super.withdraw(amount + 1);//1 块转入银行
        }
        count--;
    }

    public SavingsAccount(double initialBalance) {
        super(initialBalance);
    }


    public int getCount() {
        return count;
    }

    public void setCount(int count) {
        this.count = count;
    }

    public double getRate() {
        return rate;
    }

    public void setRate(double rate) {
        this.rate = rate;
    }
}
===============================================================
package com.hspedu.homework;

public class Homework08 {
    public static void main(String[] args) {
//        CheckingAccount checkingAccount = new CheckingAccount(1000);
//        checkingAccount.deposit(10);// 1010 - 1 = 1009
//        checkingAccount.withdraw(9);//1009 - 9 = 1000 -1= 999
//        System.out.println(checkingAccount.getBalance());

        //测试SavingsAccount
        SavingsAccount savingsAccount = new SavingsAccount(1000);
        savingsAccount.deposit(100);
        savingsAccount.deposit(100);
        savingsAccount.deposit(100);
        System.out.println(savingsAccount.getBalance());//1300
        savingsAccount.deposit(100);
        System.out.println(savingsAccount.getBalance());//1400-1=1399

        //月初，定时器自动调用一下 earnMonthlyInterest
        savingsAccount.earnMonthlyInterest();//统计利息
        System.out.println(savingsAccount.getBalance());//1399 + 13.99 =1412.99
        savingsAccount.withdraw(100);//免手续
        System.out.println(savingsAccount.getBalance());//1412.99 -100 =1312.99
        savingsAccount.withdraw(100);//免手续
        savingsAccount.withdraw(100);//免手续
        System.out.println(savingsAccount.getBalance());//1412.99 -200 =1112.99
        savingsAccount.deposit(100);//扣手续费
        System.out.println(savingsAccount.getBalance());//1112.99 + 100 = 1212.99 - 1 = 1211.99

    }
}


```



![img](https://img-blog.csdnimg.cn/img_convert/81d0b7280df654970a8ddd192ad337a1.png)



```java
9.
package com.hspedu.homework;

public class Point {
    private double x;
    private double y;

    public Point(double x, double y) {
        this.x = x;
        this.y = y;
    }
}
===================================================================
package com.hspedu.homework;

public class LabeledPoint extends Point {
    //特有属性
    private String label;

    public LabeledPoint(String label, double x, double y) {
        super(x, y);
        this.label = label;
    }
    //方法
}
=================================================================
package com.hspedu.homework;

public class Homework09 {
    public static void main(String[] args) {
        new LabeledPoint("Black",1929,230.07);
    }
}



---------------------------------------------------------------------------------------
10
package com.homework.Homework10;

public class HomeWork10 {
    public static void main(String[] args) {
        Doctor doctor1=new Doctor("jack",20,"牙科医生",'男',20000);
        Doctor doctor2=new Doctor("jack",20,"牙科医生",'男',20000);
        System.out.println(doctor1.equals(doctor2));
    }
}
===================================================================
package com.homework.Homework10;

public class Doctor {

        //属性
        //{name, age, job, gender, sal}
        private String name;
        private int age;
        private String job;
        private char gender;
        private double sal;
        //5个参数的构造器

        public Doctor(String name, int age, String job, char gender, double sal) {
            this.name = name;
            this.age = age;
            this.job = job;
            this.gender = gender;
            this.sal = sal;
        }

        //方法
        //相应的getter()和setter()方法

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }

        public int getAge() {
            return age;
        }

        public void setAge(int age) {
            this.age = age;
        }

        public String getJob() {
            return job;
        }

        public void setJob(String job) {
            this.job = job;
        }

        public char getGender() {
            return gender;
        }

        public void setGender(char gender) {
            this.gender = gender;
        }

        public double getSal() {
            return sal;
        }

        public void setSal(double sal) {
            this.sal = sal;
        }

        //重写父类(Object)的equals()方法：public boolean equals(Object obj)，并判断测试类中创建的两个对象是否相等。相等就是判断属性是否相同
        public boolean equals(Object obj){
            if(this==obj){
                return true;
            }
            //判断obj是否是Doctor类型或者子类

            //过关斩将 校验法 同零钱通
            if (!(obj instanceof Doctor)){//不是的话
                return false;
            }

            //向下转型，因为obj的运行类型是Doctor或者其子类型
            Doctor doctor=(Doctor) obj;
            return this.name.equals(doctor.name)&&this.age==doctor.age&&
                    this.gender==doctor.gender&&this.job.equals(doctor.job)&&this.sal==doctor.sal;

        }
}

```



![img](https://img-blog.csdnimg.cn/img_convert/4620b449ba77b16e1453001f909901b5.png)



![img](https://img-blog.csdnimg.cn/img_convert/375521f023f3abf3fa136deb53e3d942.png)



![img](https://img-blog.csdnimg.cn/img_convert/982d5b3f96d62f5e69590a66763e3afe.png)

```java
父类：
package com.homework.Homework13;

public class Person {
    public String name;
    public char sex;
    private int age;

    public Person(String name, char sex, int age) {
        this.name = name;
        this.sex = sex;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public char getSex() {
        return sex;
    }

    public void setSex(char sex) {
        this.sex = sex;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
    public String play(){
        return name+"爱玩";
    }


}
==================================================================
package com.homework.Homework13;

public class Teacher extends Person{

    private int work_age;

    public Teacher(String name, char sex, int age, int work_age) {
        super(name, sex, age);
        this.work_age = work_age;
    }

    public int getWork_age() {
        return work_age;
    }

    public void setWork_age(int work_age) {
        this.work_age = work_age;
    }

    public void teach(){
        System.out.println(getName()+": 我承诺，我会认真教学。");

    }

    @Override
    public String play() {
        return super.play()+"爱玩象棋";
    }

    @Override
    public String toString() {
        return "老师信息" +
                "\n姓名：" + name +
                "\n性别：" + sex +"\n年龄: " + getAge() +
                "\n工龄：" + work_age +"\n"+this.play();
    }
}
=====================================================================
package com.homework.Homework13;

public class Student extends Person{
    private String stu_id;

    public Student(String name, char sex, int age, String stu_id) {
        super(name, sex, age);
        this.stu_id = stu_id;
    }

    public String getStu_id() {
        return stu_id;
    }

    public void setStu_id(String stu_id) {
        this.stu_id = stu_id;
    }
    public void study(){
        System.out.println(getName()+": 我承诺，我会好好学习。");

    }

    @Override
    public String play() {
        return super.play()+"爱玩足球";
    }

    @Override
    public String toString() {
        return "学生信息" +
                "\n姓名：" + name +
                "\n性别：" + sex +"\n年龄: " + getAge() +
                "\n学号：" + stu_id +"\n"+this.play();
    }
}
==================================================================
主程序：
package com.homework.Homework13;

public class HomeWork13 {
    public static void main(String[] args) {
        Person [] person =new Person[4];
        person[0]=new Student("小明",'男',15,"00023102");
        person[1]=new Student("小红",'女',14,"00023103");
        person[2]=new Teacher("老李",'男',45,20);
        person[3]=new Teacher("老王",'女',42,18);

        HomeWork13 homeWork13=new HomeWork13();
        homeWork13.bubbleSort(person);

        System.out.println("-----------");
        for (int i = 0; i <=person.length - 1; i++) {
            homeWork13.test(person[i]);//?
        }

    }
    public void bubbleSort(Person[] person){
        Person tempt = null;
        for (int i = 0; i < person.length - 1; i++) {
            for (int j = 0; j < person.length - i - 1; j++) {
                if (person[j].getAge() < person[j + 1].getAge()) {
                    tempt = person[j];
                    person[j] = person[j + 1];
                    person[j + 1] = tempt;
                }
            }
        }
    }
    public void  test (Person p ){

            if(p instanceof Teacher){
                Teacher teacher=(Teacher) p;
                System.out.println(p);
                teacher.teach();
                System.out.println("-----------");

            }else if (p instanceof Student){
                Student student=(Student) p;
                System.out.println(p);
                student.study();
                System.out.println("-----------");
            }else {
                System.out.println("do nothing....");
            }


    }

}
  
```



![img](https://img-blog.csdnimg.cn/img_convert/7f8ee960fc0a710faab1216ecd67719d.png)



![img](https://img-blog.csdnimg.cn/img_convert/5a283368e64b465efe6ebfb9a69cc323.png)

```java
package com.hspedu.homework;

public class Homework15 {
    public static void main(String[] args) {
        AAA obj = new BBB();//向上转型
        AAA b1 = obj;//b1指向obj的地址
        System.out.println("obj的运行类型=" + obj.getClass());//BBB
        obj = new CCC();//向上转型

        System.out.println("obj的运行类型=" + obj.getClass());//CCC
        obj = b1;

        System.out.println("obj的运行类型=" + obj.getClass());//BBB
    }
}

class AAA {//超类

}
class BBB extends AAA {//父类

}
class CCC extends BBB {//子类

}
```



## 第9章 项目-房屋出租系统

### 9.1 房屋出租系统-需求

#### 9.1.1 项目需求说明

实现基于文本界面的《房屋出租软件》。

能够实现对房屋信息的添加、修改和删除（用数组实现），并能够打印房屋明细表

### 9.2 房屋出租系统-界面

#### 9.2.1 项目界面 - 主菜单

![img](https://img-blog.csdnimg.cn/img_convert/9e984a045b632116e7bd76bfde238845.png)

#### 9.2.2 项目界面- 新增房源

![img](https://img-blog.csdnimg.cn/img_convert/0bb2f856da553c175611cfdaa50b8057.png)

#### 9.2.3 项目界面- 查找房源

![img](https://img-blog.csdnimg.cn/img_convert/0bb2f856da553c175611cfdaa50b8057.png)

#### 9.2.4 目界面- 删除房源

![img](https://img-blog.csdnimg.cn/img_convert/9f33185e00fb275a06095a629d873fd2.png)

#### 9.2.5 项目界面- 修改房源

![img](https://img-blog.csdnimg.cn/img_convert/a7b100233c4921d4d38157da3b0c9a5b.png)

#### 9.2.6 项目界面- 房屋列表

![img](https://img-blog.csdnimg.cn/img_convert/ebac6bdba36c43e3fe50395976423a03.png)

#### 9.2.7 项目界面- 退出系统

![img](https://img-blog.csdnimg.cn/img_convert/4d8dd1bd4062183bdddf9c84bfcd7312.png)





### 9.3 房屋出租系统-设计

项目设计-程序框架图 (分层模式=>当软件比较复杂，需要模式管理)

![img](https://img-blog.csdnimg.cn/img_convert/1ed839683c26fa3913b3a8cca27673a8.png)





### 9.4 房屋出租系统-实现

#### 9.4.1 准备工具类Utility,并提高开发效率

```java
package com.hspedu.houserent.utils;


/**
    工具类的作用:
    处理各种情况的用户输入，并且能够按照程序员的需求，得到用户的控制台输入。
*/

import java.util.*;
/**

    
*/
public class Utility {
    //静态属性。。。
    private static Scanner scanner = new Scanner(System.in);

    
    /**
     * 功能：读取键盘输入的一个菜单选项，值：1——5的范围
     * @return 1——5
     */
    public static char readMenuSelection() {
        char c;
        for (; ; ) {
            String str = readKeyBoard(1, false);//包含一个字符的字符串
            c = str.charAt(0);//将字符串转换成字符char类型
            if (c != '1' && c != '2' && 
                c != '3' && c != '4' && c != '5') {
                System.out.print("选择错误，请重新输入：");
            } else break;
        }
        return c;
    }

    /**
     * 功能：读取键盘输入的一个字符
     * @return 一个字符
     */
    public static char readChar() {
        String str = readKeyBoard(1, false);//就是一个字符
        return str.charAt(0);
    }
    /**
     * 功能：读取键盘输入的一个字符，如果直接按回车，则返回指定的默认值；否则返回输入的那个字符
     * @param defaultValue 指定的默认值
     * @return 默认值或输入的字符
     */
    
    public static char readChar(char defaultValue) {
        String str = readKeyBoard(1, true);//要么是空字符串，要么是一个字符
        return (str.length() == 0) ? defaultValue : str.charAt(0);
    }
    
    /**
     * 功能：读取键盘输入的整型，长度小于2位
     * @return 整数
     */
    public static int readInt() {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, false);//一个整数，长度<=10位
            try {
                n = Integer.parseInt(str);//将字符串转换成整数
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }
    /**
     * 功能：读取键盘输入的 整数或默认值，如果直接回车，则返回默认值，否则返回输入的整数
     * @param defaultValue 指定的默认值
     * @return 整数或默认值
     */
    public static int readInt(int defaultValue) {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, true);
            if (str.equals("")) {
                return defaultValue;
            }
            
            //异常处理...
            try {
                n = Integer.parseInt(str);
                break;
            } catch (NumberFormatException e) {
                System.out.print("数字输入错误，请重新输入：");
            }
        }
        return n;
    }

    /**
     * 功能：读取键盘输入的指定长度的字符串
     * @param limit 限制的长度
     * @return 指定长度的字符串
     */

    public static String readString(int limit) {
        return readKeyBoard(limit, false);
    }

    /**
     * 功能：读取键盘输入的指定长度的字符串或默认值，如果直接回车，返回默认值，否则返回字符串
     * @param limit 限制的长度
     * @param defaultValue 指定的默认值
     * @return 指定长度的字符串
     */
    
    public static String readString(int limit, String defaultValue) {
        String str = readKeyBoard(limit, true);
        return str.equals("")? defaultValue : str;
    }


    /**
     * 功能：读取键盘输入的确认选项，Y或N
     * 将小的功能，封装到一个方法中.
     * @return Y或N
     */
    public static char readConfirmSelection() {
        System.out.println("请输入你的选择(Y/N): 请小心选择");
        char c;
        for (; ; ) {//无限循环
            //在这里，将接受到字符，转成了大写字母
            //y => Y n=>N
            String str = readKeyBoard(1, false).toUpperCase();
            c = str.charAt(0);
            if (c == 'Y' || c == 'N') {
                break;
            } else {
                System.out.print("选择错误，请重新输入：");
            }
        }
        return c;
    }

    /**
     * 功能： 读取一个字符串
     * @param limit 读取的长度
     * @param blankReturn 如果为true ,表示 可以读空字符串。 
     *                    如果为false表示 不能读空字符串。
     *          
     *  如果输入为空，或者输入大于limit的长度，就会提示重新输入。
     * @return
     */
    private static String readKeyBoard(int limit, boolean blankReturn) {
        
        //定义了字符串
        String line = "";

        //scanner.hasNextLine() 判断有没有下一行
        while (scanner.hasNextLine()) {
            line = scanner.nextLine();//读取这一行
           
            //如果line.length=0, 即用户没有输入任何内容，直接回车
            if (line.length() == 0) {
                if (blankReturn) return line;//如果blankReturn=true,可以返回空串
                else continue; //如果blankReturn=false,不接受空串，必须输入内容
            }

            //如果用户输入的内容大于了 limit，就提示重写输入  
            //如果用户如的内容 >0 <= limit ,我就接受
            if (line.length() < 1 || line.length() > limit) {
                System.out.print("输入长度（不能大于" + limit + "）错误，请重新输入：");
                continue;
            }
            break;
        }

        return line;
    }
}
===============================================================================
package com.hspedu.houserent.utils;

public class TestUtility {
    public static void main(String[] args) {

        //这是一个测试类，使用完毕，就可以删除了
        //要求输入一个字符串，长度最大为3
//        String s = Utility.readString(3);
//        System.out.println("s=" + s);

        //要求输入一个字符串，长度最大为10, 如果用户直接回车，就给一个默认值
        //老师提示：就把该方法当做一个api使用即可
        //"hspedu"
        System.out.println("请输入字符串:");
        String s2 = Utility.readString(10, "hspedu");
        System.out.println("s2=" + s2);


        //老师解释一个问题
        //这里老师是直接使用 类.方法() => 因为当一个方法是static时，就是一个静态方法
        //注意：静态方法可以直接通过类名调用. => 具体细节老师后面在说.

        A.cry();
    }
}

class A {
    public void hi() {

    }
    public static void cry() {

    }
}

```



#### 9.4.2 项目功能实现-完成House 类

编号 房主 电话 地址 月租 状态(未出租/已出租）

#### 9.4.3 项目功能实现-显示主菜单和完成退出软件功能

老师说明：实现功能的三部曲 [明确完成功能->思路分析->代码实现]

功能说明:

用户打开软件， 可以看到主菜单，可以退出软件.

思路分析:

在 HouseView.java 中，编写一个方法 mainMenu,显示菜单.



#### 9.4.4 项目功能实现-完成显示房屋列表的功能

![img](https://img-blog.csdnimg.cn/img_convert/45b2587185c86c2f2dae94278cbf5968.png)



#### 9.4.5 项目功能实现-添加房屋信息的功能

![img](https://img-blog.csdnimg.cn/img_convert/00784207a80e481753c36f4aa9db7d05.png)

#### 9.4.6 项目功能实现-完成删除房屋信息的功能

![img](https://img-blog.csdnimg.cn/img_convert/6cdc3c3e2bb64f1e4392fde775bf3074.png)

#### 9.4.7 项目功能实现-完善退出确认功能

![img](https://img-blog.csdnimg.cn/img_convert/0b13283e8c54a8a161ba970f9fa39048.png)

#### 9.4.8 项目功能实现-完成根据id 查找房屋信息的功能

#### 9.4.9 项目功能实现-完成修改房屋信息的功能

![img](https://img-blog.csdnimg.cn/img_convert/86fb0d74504a17bef9fdec6868b947c6.png)





主要见代码，好好研究





## 第10 章面向对象编程(高级部分)

### 10.1 类变量和类方法

#### 10.1.1 类变量-提出问题

提出问题的主要目的就是让大家思考解决之道，从而引出我要讲的知识点.

说：有一群小孩在玩堆雪人,不时有新的小孩加入,请问如何知道现在共有多少人在玩?，编写程序解决。

![img](https://img-blog.csdnimg.cn/img_convert/bd60de942096e0186318dc00b4035aa5.png)

#### 10.1.2 传统的方法来解决

![img](https://img-blog.csdnimg.cn/img_convert/70ab10133fb79e467c1b2b21885da3bf.png)

```java
package com.shj.static_;

public class ChildGame {
    public static void main(String[] args) {
        int count = 0;
        Child child1=new Child("白骨精");
        child1.join();
        count++;
        Child child2=new Child("狐狸精");
        child2.join();
        count++;
        Child child3=new Child("老鼠精");
        child3.join();
        count++;
        System.out.println("共有" + count  + " 小孩加入了游戏...");
    }

}
class Child{
    private String name;
    public Child(String name){
        this.name=name;
    }
    public void join() {
        System.out.println(name + " 加入了游戏..");
    }

}
```



#### 10.1.3 类变量快速入门

思考: 如果,设计一个 int count 表示总人数,我们在创建一个小孩时，就把 count 加 1,并且 count 是所有对象共享的就 ok 了!，我们使用类变量来解决 ChildGame.java 改进

```java
package com.hspedu.static_;

public class ChildGame {

    public static void main(String[] args) {

        //定义一个变量 count, 统计有多少小孩加入了游戏
        int count = 0;

        Child child1 = new Child("白骨精");
        child1.join();
        //count++;
        child1.count++;

        Child child2 = new Child("狐狸精");
        child2.join();
        //count++;
        child2.count++;

        Child child3 = new Child("老鼠精");
        child3.join();
        //count++;
        child3.count++;

        //===========
        //类变量，可以通过类名来访问
        System.out.println("共有" + Child.count  + " 小孩加入了游戏...");
        //下面的代码输出什么?
        System.out.println("child1.count=" + child1.count);//3
        System.out.println("child2.count=" + child2.count);//3
        System.out.println("child3.count=" + child3.count);//3



    }
}

class Child { //类
    private String name;
    //定义一个变量 count ,是一个类变量(静态变量) static 静态
    //该变量最大的特点就是会被Child 类的所有的对象实例共享
    public static int count = 0;
    public Child(String name) {
        this.name = name;
    }
    public void join() {
        System.out.println(name + " 加入了游戏..");
    }
}

```



#### 10.1.4 类变量内存布局

![img](https://img-blog.csdnimg.cn/img_convert/634fa5105e2a1f7eb6e77664409fcf3c.png)

java8以前是方法区里面，之后子堆中。

静态变量特点：

1、被所有对象共享

2、在类加载时生成

![img](https://img-blog.csdnimg.cn/img_convert/b67fe19857fea2595007adef1b5e127b.png)



#### 10.1.5 什么是类变量

![img](https://img-blog.csdnimg.cn/img_convert/6e66e78fca62c4f3e98eda30aff342be.png)





```java
package com.hspedu.static_;

public class VisitStatic {
    public static void main(String[] args) {

        //类名.类变量名
        //说明：类变量是随着类的加载而创建，所以即使没有创建对象实例也可以访问
        System.out.println(A.name);
        A a = new A();
        //通过对象名.类变量名
        System.out.println("a.name=" + a.name);

    }
}

class A {
    //类变量
    //类变量的访问，必须遵守 相关的访问权限.
    public static  String name = "韩顺平教育";
    //普通属性/普通成员变量/非静态属性/非静态成员变量/实例变量
    private int num = 10;

}

```

#### 10.1.8 类变量使用注意事项和细节讨论 StaticDetail.java

![img](https://img-blog.csdnimg.cn/img_convert/4b7f921ab3b1c4460e5bc4f8066372ba.png)

![img](https://img-blog.csdnimg.cn/img_convert/c68a263ef93db47cfd62eaadb046aef4.png)



```java
package com.hspedu.static_;

public class StaticDetail {
    public static void main(String[] args) {
        B b = new B();
        //System.out.println(B.n1);
        System.out.println(B.n2);

        //静态变量是类加载的时候，就创建了,所以我们没有创建对象实例
        //也可以通过类名.类变量名来访问
        System.out.println(C.address);

    }
}

class B {
    public  int n1 = 100;
    public static int n2 = 200;
}

class C {
    public static String address = "北京";
}

```



#### 10.1.9 类方法基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/a1309fc86ff3df640a35e174fb104aef.png)





```java
package com.hspedu.static_;

public class StaticMethod {
    public static void main(String[] args) {
        //创建2个学生对象，叫学费
        Stu tom = new Stu("tom");
        //tom.payFee(100);
        Stu.payFee(100);//对不对?对

        Stu mary = new Stu("mary");
        //mary.payFee(200);
        Stu.payFee(200);//对


        //输出当前收到的总学费
        Stu.showFee();//300

        //如果我们希望不创建实例，也可以调用某个方法(即当做工具来使用)
        //这时，把方法做成静态方法时非常合适
        System.out.println("9开平方的结果是=" + Math.sqrt(9));


        System.out.println(MyTools.calSum(10, 30));
    }
}
//开发自己的工具类时，可以将方法做成静态的，方便调用
class MyTools  {
    //求出两个数的和
    public static double calSum(double n1, double n2) {
        return  n1 + n2;
    }
    //可以写出很多这样的工具方法...
}
class Stu {
    private String name;//普通成员
    //定义一个静态变量，来累积学生的学费
    private static double fee = 0;

    public Stu(String name) {
        this.name = name;
    }
    //说明
    //1. 当方法使用了static修饰后，该方法就是静态方法
    //2. 静态方法就可以访问静态属性/变量
    public static void payFee(double fee) {
        Stu.fee += fee;//累积到
    }
    public static void showFee() {
        System.out.println("总学费有:" + Stu.fee);
    }
}

```



#### 10.1.12 类方法经典的使用场景

![img](https://img-blog.csdnimg.cn/img_convert/c63d79cea831876153eb56f3515b7d0f.png)

见上代码



#### 10.1.13 类方法使用注意事项和细节讨论 StaticMethodDetail.java

![img](https://img-blog.csdnimg.cn/img_convert/b3b202ee8a7409c32ea5aad9163349bd.png)

![img](https://img-blog.csdnimg.cn/img_convert/ce2b8cac002d310f023b673ef5220029.png)



```java
package com.hspedu.static_;

public class StaticMethodDetail {
    public static void main(String[] args) {

        D.hi();//ok
        //非静态方法，不能通过类名调用
        //D.say();, 错误，需要先创建对象，再调用
        new D().say();//可以
    }
}
class D {

    private int n1 = 100;
    private static  int n2 = 200;
    public void say() {//非静态方法,普通方法

    }

    public static  void hi() {//静态方法,类方法
        //类方法中不允许使用和对象有关的关键字，
        //比如this和super。普通方法(成员方法)可以。
        //System.out.println(this.n1);//报错
    }

    //类方法(静态方法)中 只能访问 静态变量 或静态方法
    //口诀:静态方法只能访问静态成员.
    public static void hello() {
        System.out.println(n2);
        System.out.println(D.n2);
        //System.out.println(this.n2);不能使用
        hi();//OK
        //say();//错误
    }
    //普通成员方法，既可以访问  非静态成员，也可以访问静态成员
    //小结: 非静态方法可以访问 静态成员和非静态成员
    public void ok() {
        //非静态成员
        System.out.println(n1);
        say();
        //静态成员
        System.out.println(n2);
        hello();

    }
}

```





#### 10.1.14 课堂练习

题一

![img](https://img-blog.csdnimg.cn/img_convert/2ba1443d8ba9bf3c95bfaecb3aa35392.png)

输出 9,10,11



题二

![img](https://img-blog.csdnimg.cn/img_convert/2205c97e9954f68d4f426aa18eb1f6e0.png)

new Person() 后使用构造器



题三

![img](https://img-blog.csdnimg.cn/img_convert/8ba11eb9bb06cdf1ce32712c3ec90f2b.png)





### 10.2 理解main 方法语法

#### 10.2.1 深入理解main 方法

![img](https://img-blog.csdnimg.cn/img_convert/779d3306553c9430c44f902e721a93c3.png)

执行程序时传入数据

#### 10.2.2 特别提示：

![img](https://img-blog.csdnimg.cn/img_convert/ec25f279f49130c34128e185841424b4.png)



```
package com.hspedu.main_;

public class Main01 {

    //静态的变量/属性
    private static  String name = "韩顺平教育";
    //非静态的变量/属性
    private int n1 = 10000;

    //静态方法
    public static  void hi() {
        System.out.println("Main01的 hi方法");
    }
    //非静态方法
    public void cry() {
        System.out.println("Main01的 cry方法");
    }

    public static void main(String[] args) {

        //可以直接使用 name
        //1. 静态方法main 可以访问本类的静态成员
        System.out.println("name=" + name);
        hi();
        //2. 静态方法main 不可以访问本类的非静态成员
        //System.out.println("n1=" + n1);//错误
        //cry();
        //3. 静态方法main 要访问本类的非静态成员，需要先创建对象 , 再调用即可
        Main01 main01 = new Main01();
        System.out.println(main01.n1);//ok
        main01.cry();
    }
}

```



#### 10.2.3 案例演示

![img](https://img-blog.csdnimg.cn/img_convert/176a9aeee424d5e4fdef587eb0a4c6a8.png)

打开右上角configurations

![img](https://img-blog.csdnimg.cn/img_convert/710a34adfd32dc1853d98d54171e3b80.png)





### 10.3 代码块

#### 10.3.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/1a40087c83568229d7fc1852367ca536.png)

![img](https://img-blog.csdnimg.cn/img_convert/d8812f0af397cf5e729071713761f2ea.png)



```java
package com.hspedu.codeblock_;

public class CodeBlock01 {
    public static void main(String[] args) {

        Movie movie = new Movie("你好，李焕英");
        System.out.println("===============");
        Movie movie2 = new Movie("唐探3", 100, "陈思诚");
    }
}

class Movie {
    private String name;
    private double price;
    private String director;

    //3个构造器-》重载
    //老韩解读
    //(1) 下面的三个构造器都有相同的语句
    //(2) 这样代码看起来比较冗余
    //(3) 这时我们可以把相同的语句，放入到一个代码块中，即可
    //(4) 这样当我们不管调用哪个构造器，创建对象，都会先调用代码块的内容
    //(5) 代码块调用的顺序优先于构造器..
    {//代码块
        System.out.println("电影屏幕打开...");
        System.out.println("广告开始...");
        System.out.println("电影正是开始...");
    };

    public Movie(String name) {
        System.out.println("Movie(String name) 被调用...");
        this.name = name;
    }

    public Movie(String name, double price) {

        this.name = name;
        this.price = price;
    }

    public Movie(String name, double price, String director) {

        System.out.println("Movie(String name, double price, String director) 被调用...");
        this.name = name;
        this.price = price;
        this.director = director;
    }
}

```



#### 10.3.4 代码块使用注意事项和细节讨论 CodeBlockDetail01.java

![img](https://img-blog.csdnimg.cn/img_convert/67f76832adbbd842ced8cf3c7eef2253.png)



```java
package com.hspedu.codeblock_;

public class CodeBlockDetail01 {
    public static void main(String[] args) {

        //类被加载的情况举例
        //1. 创建对象实例时(new)
        // AA aa = new AA();
        //2. 创建子类对象实例，父类也会被加载, 而且，父类先被加载，子类后被加载  BB先执行，AA在执行
        // AA aa2 = new AA();
        //3. 使用类的静态成员时(静态属性，静态方法)  父类必先加载
        // System.out.println(Cat.n1);

        //static代码块，是在类加载时，执行的，而且只会执行一次.
//        DD dd = new DD();
//        DD dd1 = new DD();
        //结果
        //DD 的静态代码1被执行...
        //DD 的普通代码块...
        //DD 的普通代码块...

        //普通的代码块，在创建对象实例时，会被隐式的调用。
        // 被创建一次，就会调用一次。
        // 如果只是使用类的静态成员时，普通代码块并不会执行

        System.out.println(DD.n1);//8888, 静态模块一定会执行，普通代码块不会调用

    }
}

class DD {
    public static int n1 = 8888;//静态属性
    //静态代码块
    static {
        System.out.println("DD 的静态代码1被执行...");//
    }
    //普通代码块, 在new 对象时，被调用，而且是每创建一个对象，就调用一次
    //可以这样简单的，理解 普通代码块是构造器的补充
    {
        System.out.println("DD 的普通代码块...");
    }
}

class Animal {
    //静态代码块
    static {
        System.out.println("Animal 的静态代码1被执行...");//
    }
}

class Cat extends Animal {

    public static  int n1 = 999;//静态属性

    //静态代码块
    static {
        System.out.println("Cat 的静态代码1被执行...");//
    }
}

class BB {
    //静态代码块
    static {
        System.out.println("BB 的静态代码1被执行...");//1
    }
}

class AA extends BB {


    //静态代码块
    static {
        System.out.println("AA 的静态代码1被执行...");//2
    }
}

```



![img](https://img-blog.csdnimg.cn/img_convert/31828e652618e6f12f9f6a8eb4617922.png)



```java
package com.hspedu.codeblock_;

public class CodeBlockDetail02 {
    public static void main(String[] args) {
        A a = new A();
        // (1) A 静态代码块01 （优先级高）
        // (2) getN1被调用...
        // (3)A 普通代码块01
        // (4)getN2被调用...
        // (5)A() 构造器被调用
        
        //静态代码块和静态属性的初始化，谁写前面谁先被调用
    }
}

class A {
    { //普通代码块
        System.out.println("A 普通代码块01");
    }
    private int n2 = getN2();//普通属性的初始化


    static { //静态代码块
        System.out.println("A 静态代码块01");
    }

    //静态属性的初始化
    private static  int n1 = getN1();

    public static int getN1() {
        System.out.println("getN1被调用...");
        return 100;
    }
    public int getN2() { //普通方法/非静态方法
        System.out.println("getN2被调用...");
        return 200;
    }

    //无参构造器
    public A() {
        System.out.println("A() 构造器被调用");
    }

}

```



![img](https://img-blog.csdnimg.cn/img_convert/abd8a86f3e9a78c8af7c7a3ab339fe4e.png)

```java
package com.hspedu.codeblock_;

public class CodeBlockDetail03 {
    public static void main(String[] args) {
        new BBB();//(1)AAA的普通代码块(2)AAA() 构造器被调用(3)BBB的普通代码块(4)BBB() 构造器被调用
    }
}

class AAA { //父类Object
    {
        System.out.println("AAA的普通代码块");
    }
    public AAA() {
        //(1)super()
        //(2)调用本类的普通代码块
        System.out.println("AAA() 构造器被调用....");
    }
}

class BBB extends AAA  {
    {
        System.out.println("BBB的普通代码块...");
    }
    public BBB() {
        //(1)super()
        //(2)调用本类的普通代码块
        System.out.println("BBB() 构造器被调用....");
    }
}

```



![img](https://img-blog.csdnimg.cn/img_convert/1992a4be1a728dcf5b6d69155c0b90a8.png)



```java
package com.hspedu.codeblock_;

public class CodeBlockDetail04 {
    public static void main(String[] args) {
        //老师说明
        //(1) 进行类的加载
        //1.1 先加载 父类 A02 1.2 再加载 B02
        //(2) 创建对象
        //2.1 从子类的构造器开始
        new B02();//对象

        //new C02();
    }
}

class A02 { //父类
    private static int n1 = getVal01();
    static {
        System.out.println("A02的一个静态代码块..");//(2)
    }
    {
        System.out.println("A02的第一个普通代码块..");//(5)
    }
    public int n3 = getVal02();//普通属性的初始化
    public static int getVal01() {
        System.out.println("getVal01");//(1)
        return 10;
    }

    public int getVal02() {
        System.out.println("getVal02");//(6)
        return 10;
    }

    public A02() {//构造器
        //隐藏
        //super()
        //普通代码和普通属性的初始化......
        System.out.println("A02的构造器");//(7)
    }

}

class C02 {
    private int n1 = 100;
    private static  int n2 = 200;

    private void m1() {

    }
    private static void m2() {

    }

    static {
        //静态代码块，只能调用静态成员
        //System.out.println(n1);错误
        System.out.println(n2);//ok
        //m1();//错误
        m2();
    }
    {
        //普通代码块，可以使用任意成员
        System.out.println(n1);
        System.out.println(n2);//ok
        m1();
        m2();
    }
}

class B02 extends A02 { //

    private static int n3 = getVal03();

    static {
        System.out.println("B02的一个静态代码块..");//(4)
    }
    public int n5 = getVal04();
    {
        System.out.println("B02的第一个普通代码块..");//(9)
    }

    public static int getVal03() {
        System.out.println("getVal03");//(3)
        return 10;
    }

    public int getVal04() {
        System.out.println("getVal04");//(8)
        return 10;
    }
    //一定要慢慢的去品..
    public B02() {//构造器
        //隐藏了
        //super()
        //普通代码块和普通属性的初始化...
        System.out.println("B02的构造器");//(10)
        // TODO Auto-generated constructor stub
    }
}
new B02()输出结果
getVal01
A02的一个静态代码块..
getVal03
B02的一个静态代码块..
A02的第一个普通代码块..
getVal02
A02的构造器
getVal04
B02的第一个普通代码块..
B02的构造器
```



#### 10.3.5 课堂练习

题一

![img](https://img-blog.csdnimg.cn/img_convert/6e12264f6067a93b8e5b506a0eee905d.png)

```java
package com.hspedu.codeblock_;

public class CodeBlockExercise01 {
}
class Person {
    public static int total;//静态变量
    static {//静态代码块
        total = 100;
        System.out.println("in static block!");
        //(1)  先加载类信息，加载完以后才调用total的值，静态代码块只加载一次
    }
}

class Test {
    public static void main(String[] args) {
        System.out.println("total = "+ Person.total); //100
        System.out.println("total = "+ Person.total); //100
    }
}
结果：
in static block!
total = 100
total = 100

```



题二

![img](https://img-blog.csdnimg.cn/img_convert/95cc9e682eb86fc536fee284590a99e3.png)

```java
package com.hspedu.codeblock_;

public class CodeBlockExercise02 {
}

class Sample
{
    Sample(String s)
    {
        System.out.println(s);
    }
    Sample()
    {
        System.out.println("Sample默认构造函数被调用");
    }
}
class Test{
    Sample sam1=new Sample("sam1成员初始化");//
    static Sample sam=new Sample("静态成员sam初始化 ");//
    static{
        System.out.println("static块执行");//
        if(sam==null)System.out.println("sam is null");
    }
    Test()//构造器
    {
        System.out.println("Test默认构造函数被调用");//
    }
    //主方法
    public static void  main(String  str[])
    {
        Test a=new Test();//无参构造器
    }

}



```





### 10.4 单例设计模式

#### 10.4.1 什么是设计模式

![img](https://img-blog.csdnimg.cn/img_convert/5d9318e823a595643f3c8c666cb40c00.png)



#### 10.4.2 什么是单例模式

![img](https://img-blog.csdnimg.cn/img_convert/671ce14adac682d2efdf9118869fc26d.png)

![img](https://img-blog.csdnimg.cn/img_convert/86e7c533f9b1770bdf691a48e28befba.png)



```java
饿汉式
package com.hspedu.single_;

public class SingleTon01 {

    public static void main(String[] args) {
//        GirlFriend xh = new GirlFriend("小红");
//        GirlFriend xb = new GirlFriend("小白");

        //通过方法可以获取对象
        GirlFriend instance = GirlFriend.getInstance();
        System.out.println(instance);

        GirlFriend instance2 = GirlFriend.getInstance();
        System.out.println(instance2);

        System.out.println(instance == instance2);//True
        //System.out.println(GirlFriend.n1);//gf对象没有调用但已经提前创建好了-饿汗式，加载类信息，“构造器被调用.”

        //...


    }

}

//有一个类， GirlFriend
//只能有一个女朋友
class GirlFriend {

    private String name;
    //public static  int n1 = 100;
    //为了能够在静态方法中，返回 gf对象，需要将其修饰为static
    //對象，通常是重量級的對象, 饿汗式可能造成創建了對象，但是沒有使用.资源浪费
    private static GirlFriend gf = new GirlFriend("小红红");//静态变量只会初始化一次

    //如何保障我们只能创建一个 GirlFriend 对象
    //步骤[单例模式-饿汉式]
    //1. 将构造器私有化
    //2. 在类的内部直接创建对象(该对象是static)
    //3. 提供一个公共的static方法，返回 gf对象
    private GirlFriend(String name) {
        System.out.println("构造器被调用.");
        this.name = name;
    }
//如果不是静态方法，上面主程序又得创建一个new方法，这就不是一个了
    public static GirlFriend getInstance() {
        return gf;

    }

    @Override
    public String toString() {
        return "GirlFriend{" +
                "name='" + name + '\'' +
                '}';
    }
}

```



```java
懒汉式
package com.hspedu.single_;

/**
 * 演示懶漢式的單例模式
 */
public class SingleTon02 {
    public static void main(String[] args) {
        //new Cat("大黃");
        //System.out.println(Cat.n1);
        Cat instance = Cat.getInstance();//此时创建了对象
        System.out.println(instance);


        //再次調用getInstance
        Cat instance2 = Cat.getInstance();
        System.out.println(instance2);

        System.out.println(instance == instance2);//T

    }
}


//希望在程序運行過程中，只能創建一個Cat對象
//使用單例模式
class Cat {
    private String name;
    public static  int n1 = 999;
    private static Cat cat ; //默認是null

    //步驟
    //1.仍然構造器私有化，防止直接用
    //2.定義一個static靜態屬性對象
    //3.提供一個public的static方法，可以返回一個Cat對象
    //4.懶漢式，只有當用戶使用getInstance時，才返回cat對象, 後面再次調用時，會返回上次創建的cat對象
    //  從而保證了單例
    private Cat(String name) {//类已经加载，但并没有创建cat对象，不调用构造器
        System.out.println("構造器調用...");
        this.name = name;
    }
    public static Cat getInstance() {

        if(cat == null) {//如果還沒有創建cat對象
            cat = new Cat("小可愛");
        }
        return cat;
    }

    @Override
    public String toString() {
        return "Cat{" +
                "name='" + name + '\'' +
                '}';
    }
}
```

#### 10.4.4 饿汉式VS 懒汉式

![img](https://img-blog.csdnimg.cn/img_convert/98d3cd77b0070ba4337592b737db3e0f.png)



第二条实例

![img](https://img-blog.csdnimg.cn/img_convert/902c7097ace7856ef967f2e1aea31ef7.png)

三条同时调用出现问题

#### 10.4.5 小结

![img](https://img-blog.csdnimg.cn/img_convert/65c28c672d3200146d69c67998a91faf.png)





### 10.5 final 关键字

#### 10.5.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/d04befc89f0831e5a222cc38e11cabc0.png)



```java
package com.hspedu.final_;

public class Final01 {
    public static void main(String[] args) {
        E e = new E();
        //e.TAX_RATE = 0.09;
    }
}

//如果我们要求A类不能被其他类继承
//可以使用final修饰 A类
final class A { }

//class B extends A {}

class C {
    //如果我们要求hi不能被子类重写
    //可以使用final修饰 hi方法
    public final void hi() {}
}
class D extends C {
//    @Override
//    public void hi() {
//        System.out.println("重写了C类的hi方法..");
//    }
}

//当不希望类的的某个属性的值被修改,可以用final修饰
class E {
    public final double TAX_RATE = 0.08;
}

//当不希望某个局部变量被修改，可以使用final修饰
class F {
    public void cry() {
        //这时，NUM 也称为 局部常量
        final double NUM = 0.01;
        //NUM = 0.9;
        System.out.println("NUM=" + NUM);
    }
}

```



#### 10.5.2 final 使用注意事项和细节讨论

![img](https://img-blog.csdnimg.cn/img_convert/32952589b5191e46fa92529b8de2646f.png)

XX_XX_XX 都为大写

```java
package com.hspedu.final_;

public class FinalDetail01 {
    public static void main(String[] args) {
        CC cc = new CC();

        new EE().cal();
    }
}

class AA {
    /*
    1. 定义时：如 public final double TAX_RATE=0.08;
    2. 在构造器中
    3. 在代码块中
     */
    public final double TAX_RATE = 0.08;//1.定义时赋值
    public final double TAX_RATE2 ;
    public final double TAX_RATE3 ;

    public AA() {//构造器中赋值
        TAX_RATE2 = 1.1;
    }
    {//在代码块赋值
        TAX_RATE3 = 8.8;
    }
}

class BB {
    /*
    如果final修饰的属性是静态的，则初始化的位置只能是
    1 定义时  2 在静态代码块 不能在构造器中赋值。
     */
    public static final double TAX_RATE = 99.9;
    public static final double TAX_RATE2 ;

//    public static  final double TAX_RATE3 ;

//    public  BB(){  //类加载最后才会调用构造器，TAX_RATE3之前就会需要值，且必须先创建对象才会加载构造器
//        TAX_RATE3=8.8;
//    }

    static {
        TAX_RATE2 = 3.3;
    }


}

//final类不能继承，但是可以实例化对象
final class CC { }//   CC cc = new CC();


//如果类不是final类，但是含有final方法，则该方法虽然不能重写，但是可以被继承
//即，仍然遵守继承的机制.
class DD {
    public final void cal() {
        System.out.println("cal()方法");
    }
}
class EE extends DD { }

```



![img](https://img-blog.csdnimg.cn/img_convert/3017ec8e08649b9b913a2d1aa506587f.png)

```java
package com.hspedu.final_;

public class FinalDetail02 {
    public static void main(String[] args) {
        System.out.println(BBB.num);

        //包装类,String 是final类，不能被继承   eg:String Double

    }
}

//final 和 static 往往搭配使用，效率更高，不会导致类加载.底层编译器做了优化处理
class BBB {
    public final static  int num = 10000;
    static {
        System.out.println("BBB 静态代码块被执行");
    }
}
final class AAA{
    //一般来说，如果一个类已经是final类了，就没有必要再将方法修饰成final方法
    //public final void cry() {}
}

```



#### 10.5.3 final 应用实例

![img](https://img-blog.csdnimg.cn/img_convert/7f342b826c7e0fb87c0d7c6a3e341807.png)



```java
package com.hspedu.final_;

public class FinalExercise01 {
    public static void main(String[] args) {
        Circle circle = new Circle(5.0);
        System.out.println("面积=" + circle.calArea());
    }
}

class Circle {
    private double radius;
    private final double PI;// = 3.14;法1
    //构造器
    public Circle(double radius) {
        this.radius = radius;
        //PI = 3.14;法2
    }
    {
        PI = 3.14;法3
    }

    public double calArea() {
        return PI * radius * radius;
    }
}
```



![img](https://img-blog.csdnimg.cn/img_convert/e3f893714393741758e7f69bffc77d11.png)





### 10.6 抽象类



![img](https://img-blog.csdnimg.cn/img_convert/a49c8272b7f4dd3816db91efd4367b7b.png)



#### 10.6.2 解决之道-抽象类快速入门

![img](https://img-blog.csdnimg.cn/img_convert/87adbcc64e261fed48b4d306c37dc3e5.png)

```java
package com.hspedu.abstract_;

public class Abstract01 {
    public static void main(String[] args) {

    }
}

abstract class Animal {
    private String name;

    public Animal(String name) {
        this.name = name;
    }

    //思考：这里eat 这里你实现了，其实没有什么意义
    //即： 父类方法不确定性的问题
    //===> 考虑将该方法设计为抽象(abstract)方法
    //===> 所谓抽象方法就是没有实现的方法
    //===> 所谓没有实现就是指，没有方法体
    //===> 当一个类中存在抽象方法时，需要将该类声明为abstract类
    //===> 一般来说，抽象类会被继承，有其子类来实现抽象方法.
//    public void eat() {
//        System.out.println("这是一个动物，但是不知道吃什么..");
//    }
    public abstract void eat()  ;
}

```



#### 10.6.3 抽象类的介绍

![img](https://img-blog.csdnimg.cn/img_convert/50ebc9c55fbc5232d14ca8fd667d15a7.png)



10.6.4 抽象类使用的注意事项和细节讨论 AbstractDetail01.java

![img](https://img-blog.csdnimg.cn/img_convert/2d51e8e71f77a22ff42fdcbb3f7458be.png)



```java
package com.hspedu.abstract_;

public class AbstractDetail01 {
    public static void main(String[] args) {
        //抽象类，不能被实例化
        //new A();
    }
}
//抽象类不一定要包含abstract方法。也就是说,抽象类可以没有abstract方法
//，还可以有实现的方法。
abstract class A {
    public void hi() {
        System.out.println("hi");
    }
}
//一旦类包含了abstract方法,则这个类必须声明为abstract
abstract class B {
    public abstract void hi();
}
//abstract 只能修饰类和方法，不能修饰属性和其它的
class C {
   // public abstract int n1 = 1;
}
```



![img](https://img-blog.csdnimg.cn/img_convert/79eb8b32186eb393f5645bad1a243693.png)

![img](https://img-blog.csdnimg.cn/img_convert/d887fa42b017c01221f07ca2a339feef.png)

所谓实现抽象类的所有抽象方法，在子类重写方法



```java
package com.hspedu.abstract_;

public class AbstractDetail02 {
    public static void main(String[] args) {
        System.out.println("hello");
    }
}
//抽象方法不能使用private、final 和 static来修饰，因为这些关键字都是和重写相违背的
abstract class H {
    public   abstract void hi();//抽象方法
}

//如果一个类继承了抽象类，则它必须实现抽象类的所有抽象方法，除非它自己也声明为abstract类
abstract class E {
    public abstract void hi();
}
abstract class F extends E {

}
class G extends E {
    @Override
    public void hi() { //这里相等于G子类实现了父类E的抽象方法，所谓实现方法，就是有方法体

    }
}

//抽象类的本质还是类，所以可以有类的各种成员
abstract class D {
    public int n1 = 10;
    public static  String name = "韩顺平教育";
    public void hi() {
        System.out.println("hi");
    }
    public abstract void hello();
    public static void ok() {
        System.out.println("ok");
    }
}

```



#### 10.6.6 课堂练习题 AbstractExercise01.java

![img](https://img-blog.csdnimg.cn/img_convert/cb150a2d0580bdb9a56df5d0fa315614.png)



```java
package com.hspedu.abstract_;

abstract public class Employee {
    private String name;
    private int id;
    private double salary;

    public Employee(String name, int id, double salary) {
        this.name = name;
        this.id = id;
        this.salary = salary;
    }
    //将work做成一个抽象方法
    public abstract void work();
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }
}
----------------------------------------------------------------------
package com.hspedu.abstract_;

public class Manager extends Employee {

    private double bonus;
    public Manager(String name, int id, double salary) {
        super(name, id, salary);
    }

    public double getBonus() {
        return bonus;
    }

    public void setBonus(double bonus) {
        this.bonus = bonus;
    }

    @Override
    public void work() {//重写方法，才能继承
        System.out.println("经理 " + getName() + " 工作中...");
    }
}
-------------------------------------------------------------------------
package com.hspedu.abstract_;

public class CommonEmployee extends Employee{
    public CommonEmployee(String name, int id, double salary) {
        super(name, id, salary);
    }

    @Override
    public void work() {
        System.out.println("普通员工 " + getName() + " 工作中...");
    }
}
-------------------------------------------------------------------------
package com.hspedu.abstract_;

public class AbstractExercise01 {
    public static void main(String[] args) {
        //测试
        Manager jack = new Manager("jack", 999, 50000);
        jack.setBonus(8000);
        jack.work();

        CommonEmployee tom = new CommonEmployee("tom", 888, 20000);
        tom.work();
    }
}

```



### 10.7 抽象类最佳实践-模板设计模

#### 10.7.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/fdc38eaec5c98e2697d2540a6e2a15fd.png)

#### 10.7.2 模板设计模式能解决的问题

![img](https://img-blog.csdnimg.cn/img_convert/00bc42b885e55caf0c9d2706edce44dd.png)



#### 10.7.3 最佳实践

![img](https://img-blog.csdnimg.cn/img_convert/b44e4d548dfe659a026170aa0c27a4f5.png)

10000.for 快捷键

![img](https://img-blog.csdnimg.cn/img_convert/ef29f2fa4ca919c28715beac90cc7a0e.png)

![img](https://img-blog.csdnimg.cn/img_convert/c7bd7df75a686d124f0afa80bbbd9a02.png)





```java
父类将共同方法集合于此
package com.hspedu.abstract_;

abstract public class Template { //抽象类-模板设计模式

    public abstract void job();//抽象方法

    public void calculateTime() {//实现方法，调用job方法
        //得到开始的时间
        long start = System.currentTimeMillis();
        job(); //动态绑定机制
        //得的结束的时间
        long end = System.currentTimeMillis();
        System.out.println("任务执行时间 " + (end - start));
    }
}
---------------------------------------------------------------------------------
package com.hspedu.abstract_;

public class AA extends Template {

    //计算任务
    //1+....+ 800000
    @Override
    public void job() { //实现Template的抽象方法job，重写方法

        long num = 0;
        for (long i = 1; i <= 800000; i++) {
            num += i;
        }
    }
}
--------------------------------------------------------------------------------
package com.hspedu.abstract_;

public class BB extends Template{

    public void job() {//这里也去，重写了Template的job方法

        long num = 0;
        for (long i = 1; i <= 80000; i++) {
            num *= i;
        }

    }
}
---------------------------------------------------------------------------------
package com.hspedu.abstract_;

public class TestTemplate {
    public static void main(String[] args) {

        AA aa = new AA();
        aa.calculateTime(); //这里还是需要有良好的OOP基础，对多态

        BB bb = new BB();
        bb.calculateTime();
    }
}

```



### 10.8 接口

#### 10.8.1 接口快速入门

![img](https://img-blog.csdnimg.cn/img_convert/8e03c4b3b869878754aee100ff58893d.png)

```java
package com.hspedu.interface_;

public class Camera implements UsbInterface{//实现接口,就是把接口方法实现

    @Override
    public void start() {
        System.out.println("相机开始工作...");
    }

    @Override
    public void stop() {
        System.out.println("相机停止工作....");
    }
}
--------------------------------------------------------------
package com.hspedu.interface_;

//Phone 类 实现 UsbInterface
//解读1. 即 Phone类需要实现 UsbInterface接口 规定/声明的方法
public class Phone implements UsbInterface {

    @Override
    public void start() {
        System.out.println("手机开始工作...");
    }

    @Override
    public void stop() {
        System.out.println("手机停止工作.....");
    }
}
------------------------------------------------------------------
package com.hspedu.interface_;

public class Computer {
    //编写一个方法, 计算机工作
    //解读:
    //1. UsbInterface usbInterface 形参是接口类型 UsbInterface
    //2. 看到 接收 实现了 UsbInterface接口的类的对象实例
    public void work(UsbInterface usbInterface) {
        //通过接口，来调用方法
        usbInterface.start();
        usbInterface.stop();
    }
}
-------------------------------------------------------------------
package com.hspedu.interface_;

public class Interface01 {
    public static void main(String[] args) {
        //创建手机，相机对象
        //Camera 实现了 UsbInterface
        Camera camera = new Camera();
        //Phone 实现了 UsbInterface
        Phone phone = new Phone();
        //创建计算机
        Computer computer = new Computer();
        computer.work(phone);//把手机接入到计算机
        System.out.println("===============");
        computer.work(camera);//把相机接入到计算机

    }
}

```





#### 10.8.2 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/b3613649228636a8ce2d7375a956731d.png)



```java
//package com.hspedu.interface_;
//
//public class Interface02 {
//    public static void main(String[] args) {
//
//    }
//}
//
老韩解读
1.如果一个类 implements实现 接口
2. 需要将该接口的所有抽象方法都实现
//class A implements AInterface {
//    @Override
//    public void hi() {
//        System.out.println("hi()....");
//    }
//}
//
//
------------------------------------------------
package com.hspedu.interface_;

public interface AInterface {
    //写属性
    public int n1 = 10;
    //写方法
    //在接口中，抽象方法，可以省略abstract关键字
    public void hi();

    //在jdk8后，可以有默认实现方法,需要使用default关键字修饰
    default public void ok() {
        System.out.println("ok ...");
    }
    //在jdk8后, 可以有静态方法
    public static void cry() {
        System.out.println("cry ....");
    }
}

```



#### 10.8.3 深入讨论

![img](https://img-blog.csdnimg.cn/img_convert/f272012e12d8008c73b6bf22b947699c.png)

![img](https://img-blog.csdnimg.cn/img_convert/7c22da03a0889e29a9a2027ef0b3023c.png)

![img](https://img-blog.csdnimg.cn/img_convert/550309f2cb86773dbc69d89e68eac7af.png)



```java
package com.hspedu.interface_;

public interface DBInterface { //项目经理

    public void connect();//连接方法
    public void close();//关闭连接
}
==========================================================================
package com.hspedu.interface_;

//B程序员连接Oracle
public class OracleDB implements DBInterface{

    @Override
    public void connect() {
        System.out.println("连接oracle");
    }

    @Override
    public void close() {
        System.out.println("关闭oracle");
    }
}
=============================================================================
package com.hspedu.interface_;
//A程序
public class MysqlDB implements DBInterface {
    @Override
    public void connect() {
        System.out.println("连接mysql");
    }

    @Override
    public void close() {
        System.out.println("关闭mysql");
    }
}
=================================================================================
package com.hspedu.interface_;

public class Interface03 {
    public static void main(String[] args) {

        MysqlDB mysqlDB = new MysqlDB();
        t(mysqlDB);
        OracleDB oracleDB = new OracleDB();
        t(oracleDB);
    }

    public static void t(DBInterface db) {
        db.connect();
        db.close();
    }
}
```



#### 10.8.4 注意事项和细节

![img](https://img-blog.csdnimg.cn/img_convert/f3ca5da90e6b90ec1433bc20ab1890cc.png)



```java
package com.hspedu.interface_;

public class InterfaceDetail01 {
    public static void main(String[] args) {
        //new IA();
    }
}

//1.接口不能被实例化
//2.接口中所有的方法是 public方法,  接口中抽象方法，可以不用abstract 修饰
//3.一个普通类实现接口,就必须将该接口的所有方法都实现,可以使用alt+enter来解决
//4.抽象类去实现接口时，可以不实现接口的抽象方法
interface IA {
    void say();//修饰符 public protected 默认 private
    void hi();
}
class Cat implements IA{
    @Override
    public void say() {//若为void say() 则会报错，会将原来的类的范围缩小

    }

    @Override
    public void hi() {

    }
}
abstract class Tiger implements  IA {

}

```



![img](https://img-blog.csdnimg.cn/img_convert/45679cf68723f0cfac935751d23b98ca.png)

```java
package com.hspedu.interface_;

public class InterfaceDetail02 {
    public static void main(String[] args) {
        //老韩证明 接口中的属性,是 public static final
        System.out.println(IB.n1);//说明n1 就是static
        //IB.n1 = 30; 说明n1 是 final
    }
}
interface IB {
    //接口中的属性,只能是final的，而且是 public static final 修饰符
    int n1 = 10; //等价 public static final int n1 = 10;
    void hi();
}
interface IC {
    void say();
}
//接口不能继承其它的类,但是可以继承多个别的接口，不能implements ，不允许放在这个位置
interface ID extends IB,IC {
}
//接口的修饰符 只能是 public 和默认，这点和类的修饰符是一样的
interface IE{}

//一个类同时可以实现多个接口
class Pig implements IB,IC {
    @Override
    public void hi() {
    }
    @Override
    public void say() {
    }
}

```



#### 10.8.5 课堂练习

![img](https://img-blog.csdnimg.cn/img_convert/1e4013b6f877d30b205baf3fe7fd68f9.png)



implements 相当于extends B可以使用A的东西

```java
package com.hspedu.interface_;

public class InterfaceExercise01 {
    public static void main(String[] args) {
        B b = new B();//ok
        System.out.println(b.a);  //23
        System.out.println(A.a);  //23  静态变量
        System.out.println(B.a);  //23  B可以使用A的东西类似于继承
    }
}

interface A {
    int a = 23; //等价 public static final int a = 23;
}

class B implements A {//正确，A中没有方法
}
```



#### 10.8.6 现接口 vs 继承类

![img](https://img-blog.csdnimg.cn/img_convert/b4a88ba3944e68360a6c17191be0bc51.png)

```java
package com.hspedu.interface_;

public class ExtendsVsInterface {
    public static void main(String[] args) {
        LittleMonkey wuKong = new LittleMonkey("悟空");
        wuKong.climbing();
        wuKong.swimming();
        wuKong.flying();
    }
}

//猴子
class Monkey {
    private String name;

    public Monkey(String name) {
        this.name = name;
    }
    public void climbing() {
        System.out.println(name + " 会爬树...");
    }

    public String getName() {
        return name;
    }
}

//接口
interface Fishable {
    void swimming();
}
interface Birdable {
    void flying();
}

//继承
//小结:  当子类继承了父类，就自动的拥有父类的功能
//      如果子类需要扩展功能，可以通过实现接口的方式扩展.
//      可以理解 实现接口 是 对java 单继承机制的一种补充.
class LittleMonkey extends Monkey implements Fishable,Birdable {//继承只能单继承 

    public LittleMonkey(String name) {
        super(name);
    }

    @Override
    public void swimming() {
        System.out.println(getName() + " 通过学习，可以像鱼儿一样游泳...");
    }

    @Override
    public void flying() {
        System.out.println(getName() + " 通过学习，可以像鸟儿一样飞翔...");
    }
}

```



![img](https://img-blog.csdnimg.cn/img_convert/ec438fb01f30a415be30fb19f0c3dc98.png)



#### 10.8.7 接口的多态特性

![img](https://img-blog.csdnimg.cn/img_convert/ea3163200a31196818dab92477995dc0.png)



```java
多态体现
package com.hspedu.interface_;

public class Computer {
    //编写一个方法, 计算机工作
    //解读:
    //1. UsbInterface usbInterface 形参是接口类型 UsbInterface
    //2. 看到 接收 实现了 UsbInterface接口的类的对象实例
    public void work(UsbInterface usbInterface) {
        //通过接口，来调用方法
        usbInterface.start();
        usbInterface.stop();
    }
}
==================================================================
package com.hspedu.interface_;

public class Camera implements UsbInterface{//实现接口,就是把接口方法实现

    @Override
    public void start() {
        System.out.println("相机开始工作...");
    }

    @Override
    public void stop() {
        System.out.println("相机停止工作....");
    }
}
===================================================================
package com.hspedu.interface_;

//Phone 类 实现 UsbInterface
//解读1. 即 Phone类需要实现 UsbInterface接口 规定/声明的方法
public class Phone implements UsbInterface {

    @Override
    public void start() {
        System.out.println("手机开始工作...");
    }

    @Override
    public void stop() {
        System.out.println("手机停止工作.....");
    }
}
========================================================================
package com.hspedu.interface_;

public class Interface01 {
    public static void main(String[] args) {
        //创建手机，相机对象
        //Camera 实现了 UsbInterface
        Camera camera = new Camera();
        //Phone 实现了 UsbInterface
        Phone phone = new Phone();
        //创建计算机
        Computer computer = new Computer();
        computer.work(phone);//把手机接入到计算机
        System.out.println("===============");
        computer.work(camera);//把相机接入到计算机

    }
}

```





```java
package com.hspedu.interface_;

public class InterfacePolyParameter {
    public static void main(String[] args) {

        //接口的多态体现
        //接口类型的变量 if01 可以指向 实现了IF接口类的对象实例
        IF if01 = new Monster();
        if01 = new Car();

        //继承体现的多态
        //父类类型的变量 a 可以指向 继承AAA的子类的对象实例
        AAA a = new BBB();
        a = new CCC();
    }
}

interface IF {}
class Monster implements IF{}
class Car implements  IF{}

class AAA {

}
class BBB extends AAA {}
class CCC extends AAA {}

```



```java
第二条
package com.hspedu.interface_;

public class InterfacePolyArr {
    public static void main(String[] args) {

        //多态数组 -> 接口类型数组
        Usb[] usbs = new Usb[2];
        usbs[0] = new Phone_();
        usbs[1] = new Camera_();
        /*
        给Usb数组中，存放 Phone  和  相机对象，Phone类还有一个特有的方法call（），
        请遍历Usb数组，如果是Phone对象，除了调用Usb 接口定义的方法外，
        还需要调用Phone 特有方法 call
         */
        for(int i = 0; i < usbs.length; i++) {
            usbs[i].work();//动态绑定..
            //和前面一样，我们仍然需要进行类型的向下转型;usbs[i].call()这样容易出问题 
            if(usbs[i] instanceof Phone_) {//判断他的运行类型是 Phone_
                ((Phone_) usbs[i]).call();//向下转型
            }
        }

    }
}

interface Usb{
    void work();
}
class Phone_ implements Usb {
    public void call() {
        System.out.println("手机可以打电话...");
    }

    @Override
    public void work() {
        System.out.println("手机工作中...");
    }
}
class Camera_ implements Usb {

    @Override
    public void work() {
        System.out.println("相机工作中...");
    }
}


```



```java
第三条
package com.hspedu.interface_;

/**
 * 演示多态传递现象
 */
public class InterfacePolyPass {
    public static void main(String[] args) {
        //接口类型的变量可以指向，实现了该接口的类的对象实例，通俗理解为向上转型
        IG ig = new Teacher();
        //如果IG 继承了 IH 接口，而Teacher 类实现了 IG接口
        //那么，实际上就相当于 Teacher 类也实现了 IH接口.
        //这就是所谓的 接口多态传递现象.
        IH ih = new Teacher();
    }
}

interface IH {
    void hi();
}
interface IG extends IH{ }//extends 使得 IH ih = new Teacher();可运行
class Teacher implements IG {
    @Override
    public void hi() {
    }
}
```





#### 10.8.8 课堂练习

![img](https://img-blog.csdnimg.cn/img_convert/f3f09c7d52e2fccba473bd9767f0ec88.png)



```java
package com.hspedu.interface_;

public class InterfaceExercise02 {
    public static void main(String[] args) {

    }
}

interface A {  // 1min 看看
    int x = 0;
}  //想到 等价 public static final int x = 0;

class B {
    int x = 1;
} //普通属性

class C extends B implements A {
    public void pX() {
        //System.out.println(x); //错误，原因不明确x
        //可以明确的指定x
        //访问接口的 x 就使用 A.x
        //访问父类的 x 就使用 super.x
        System.out.println(A.x + " " + super.x);
    }

    public static void main(String[] args) {
        new C().pX();
    }
}


```



#### 10.8.9 类的完善

![img](https://img-blog.csdnimg.cn/img_convert/45c3f14232d1f9b548bdfe7c5c998122.png)





### 10.9 内部类

#### 10.9.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/d1a6209a900759b93b15d8090b106119.png)



#### 10.9.2 快速入门案例

```java
package com.hspedu.innerclass;

public class InnerClass01 { //外部其他类
    public static void main(String[] args) {

    }
}
class Outer { //外部类
    private int n1 = 100;//属性
    public Outer(int n1) {//构造器
        this.n1 = n1;
    }
    public void m1() {//方法
        System.out.println("m1()");
    }
    {//代码块
        System.out.println("代码块...");
    }
    class Inner { //内部类, 在Outer类的内部

    }
}

```



#### 10.9.3 内部类的分类

![img](https://img-blog.csdnimg.cn/img_convert/ec6bed53fa980ad92799a7e5095a3574.png)



#### 10.9.4 局部内部类的使用

![img](https://img-blog.csdnimg.cn/img_convert/af7eced76b32dc92951db9347a370da8.png)

![img](https://img-blog.csdnimg.cn/img_convert/d56cc9e7d08848bd675744730498f939.png)

![img](https://img-blog.csdnimg.cn/img_convert/107cba2858bceb99a7ff86b5a6d00439.png)



```java
package com.hspedu.innerclass;
/**
 * 演示局部内部类的使用
 */
public class   LocalInnerClass {//
    public static void main(String[] args) {
        //演示一遍
        Outer02 outer02 = new Outer02();
        outer02.m1();
        System.out.println("outer02的hashcode=" + outer02);
    }
}


class Outer02 {//外部类
    private int n1 = 100;
    private void m2() {
        System.out.println("Outer02 m2()");
    }//私有方法
    public void m1() {//方法
        //1.局部内部类是定义在外部类的局部位置,通常在方法
        //3.不能添加访问修饰符,但是可以使用final 修饰，加了final这个类无法再被其他类继承
        //它的地位就是一个局部变量，局部变量不可以使用修饰符
        //4.作用域 : 仅仅在定义它的方法或代码块中
        final class Inner02 {
            
//局部内部类(本质仍然是一个类)，只在这个方法中可以在定义它的方法或代码块中作用类似于String name =“xxx”;
            
            //2.可以直接访问外部类的所有成员，包含私有的
            private int n1 = 800;
            
            public void f1() {
         //5. 局部内部类可以直接访问外部类的成员，比如下面 外部类n1 和 m2()
         //7. 如果外部类和局部内部类的成员重名时，默认遵循就近原则，如果想访问外部类的成员，
         // 使用 外部类名.this.成员）去访问
         //老韩解读 Outer02.this 本质就是外部类的对象, 即哪个对象调用了m1, Outer02.this就是哪个对象
                
                System.out.println("n1=" + n1 + " 外部类的n1=" + Outer02.this.n1);
                
        //上面的outer02.m1()调用m1方法，Outer02.this对象就是outer02.m1()，两个对象指向的地址都相同
                
                System.out.println("Outer02.this hashcode=" + Outer02.this);
                m2();
            }
        }
        //6. 外部类在方法中，可以创建Inner02对象，然后调用方法即可
        Inner02 inner02 = new Inner02();
        inner02.f1();
    }

}


```





#### 10.9.5 匿名内部类的使用！！！！！

![img](https://img-blog.csdnimg.cn/img_convert/9f7617df6316e1f0f9d449b33f37a93e.png)

```java
基于接口
package com.hspedu.innerclass;


/**
 * 演示匿名内部类的使用
 */
public class AnonymousInnerClass {
    public static void main(String[] args) {
        Outer04 outer04 = new Outer04();
        outer04.method();
    }
}

class Outer04 { //外部类
    private int n1 = 10;//属性
    public void method() {//方法
        //基于接口的匿名内部类
        //老韩解读
        //1.需求： 想使用IA接口,并创建对象
        
        
        //2.传统方式，是写一个类，
        //实现该接口（class Tiger implements IA；），
        //并创建对象  IA tiger = new Tiger();  tiger.cry();
        
        
        //3.老韩需求是 Tiger/Dog 类只是使用一次，后面再不使用
        //4. 可以使用匿名内部类来简化开发
        //5. tiger的编译类型 ? IA
        //6. tiger的运行类型 ? 就是匿名内部类  Outer04$1
        /*
            我们看底层 会分配 类名 Outer04$1
            class Outer04$1 implements IA {
                @Override
                public void cry() {
                    System.out.println("老虎叫唤...");
                }
            }
         */
        //7. jdk底层在创建匿名内部类 Outer04$1,立即马上就创建了 Outer04$1实例，并且把地址
        //   返回给 tiger
        //8. 匿名内部类使用一次，就不能再使用
        IA tiger = new IA() {//4. 可以使用匿名内部类来简化开发
            @Override
            public void cry() {
                System.out.println("老虎叫唤...");
            }
        };
        System.out.println("tiger的运行类型=" + tiger.getClass());
        tiger.cry();
        tiger.cry();
        tiger.cry();

//        IA tiger = new Tiger();
//        tiger.cry();

        
       //演示基于类的匿名内部类
        //分析
        //1. father编译类型 Father
        //2. father运行类型 Outer04$2
        //3. 底层会创建匿名内部类
        /*
            class Outer04$2 extends Father{
                @Override
                public void test() {
                    System.out.println("匿名内部类重写了test方法");
                }
            }
         */
        //4. 同时也直接返回了 匿名内部类 Outer04$2的对象
        //5. 注意("jack") 参数列表会传递给 构造器
        Father father = new Father("jack"){

            @Override
            public void test() {
                System.out.println("匿名内部类重写了test方法");
            }
        };
        System.out.println("father对象的运行类型=" + father.getClass());//Outer04$2
        father.test();

        //基于抽象类的匿名内部类
        Animal animal = new Animal(){
            @Override
            void eat() {
                System.out.println("小狗吃骨头...");
            }
        };
        animal.eat();
    }
}

interface IA {//接口
    public void cry();
}
//class Tiger implements IA {//传统方法去调用
//
//    @Override
//    public void cry() {
//        System.out.println("老虎叫唤...");
//    }
//}
//class Dog implements  IA{
//    @Override
//    public void cry() {
//        System.out.println("小狗汪汪...");
//    }
//}

class Father {//类
    public Father(String name) {//构造器
        System.out.println("接收到name=" + name);
    }
    public void test() {//方法
    }
}

abstract class Animal { //抽象类
    abstract void eat();
}


```





![img](https://img-blog.csdnimg.cn/img_convert/26ed9febb7e97715934dad1748f27ee7.png)

![img](https://img-blog.csdnimg.cn/img_convert/d7e93f9b6b4eef901d87a4e71507400a.png)

![img](https://img-blog.csdnimg.cn/img_convert/ae9d8530cee948203bc1968f93449c58.png)

![img](https://img-blog.csdnimg.cn/img_convert/8c52f9bab0f72bfcfb3a0652b4fb988d.png)



```java
package com.hspedu.innerclass;

public class AnonymousInnerClassDetail {
    public static void main(String[] args) {

        Outer05 outer05 = new Outer05();
        outer05.f1();
        //外部其他类---不能访问----->匿名内部类
        System.out.println("main outer05 hashcode=" + outer05);
    }
}

class Outer05 {
    private int n1 = 99;
    public void f1() {
        //创建一个基于类的匿名内部类
        //不能添加访问修饰符,因为它的地位就是一个局部变量
        //作用域 : 仅仅在定义它的方法或代码块中
        Person p = new Person(){
            private int n1 = 88;
            @Override//没有重写方法则会直接调用Person的方法，若重写则是匿名内部类
            public void hi() {
                //可以直接访问外部类的所有成员，包含私有的
                //如果外部类和匿名内部类的成员重名时，匿名内部类访问的话，
                //默认遵循就近原则，如果想访问外部类的成员，则可以使用 （外部类名.this.成员）去访问
                System.out.println("匿名内部类重写了 hi方法 n1=" + n1 +
                        " 外部内的n1=" + Outer05.this.n1 );
                //Outer05.this 就是调用 f1的 对象
                System.out.println("Outer05.this hashcode=" + Outer05.this);
            }
        };
        p.hi();//动态绑定, 运行类型是 Outer05$1

        //也可以直接调用, 匿名内部类本身也是返回对象,只能有一个匿名内部类
        // class 匿名内部类 extends Person {}
//        new Person(){
//            @Override
//            public void hi() {
//                System.out.println("匿名内部类重写了 hi方法,哈哈...");
//            }
//            @Override
//            public void ok(String str) {
//                super.ok(str);
//            }
//        }.ok("jack");


    }
}

class Person {//类
    public void hi() {
        System.out.println("Person hi()");
    }
    public void ok(String str) {
        System.out.println("Person ok() " + str);
    }
}
//抽象类/接口...

```



#### 10.9.6 匿名内部类的实践

![img](https://img-blog.csdnimg.cn/img_convert/94cfddc4bb4b1fccf99b59016c94dfeb.png)

```java
package com.hspedu.innerclass;

import com.hspedu.abstract_.AA;

public class InnerClassExercise01 {
    public static void main(String[] args) {

        //当做实参直接传递，简洁高效
        f1(new IL() {
            @Override
            public void show() {
                System.out.println("这是一副名画~~...");//这里修改只会影响本处
            }
        });
        //传统方法
        f1(new Picture());

    }

    //静态方法,形参是接口类型
    public static void f1(IL il) {
        il.show();
    }
}
//接口
interface IL {
    void show();
}
//类->实现IL => 编程领域 (硬编码)
class Picture implements IL {

    @Override
    public void show() {
        System.out.println("这是一副名画XX...");//这里修改会影响全局
    }
}


```



![img](https://img-blog.csdnimg.cn/img_convert/53924a293cd888f7a0daac4687ebde7f.png)

```java
package com.hspedu.innerclass;

public class InnerClassExercise02 {
    public static void main(String[] args) {
        /*
        1.有一个铃声接口Bell，里面有个ring方法。(右图)
        2.有一个手机类Cellphone，具有闹钟功能alarmClock，参数是Bell类型(右图)
        3.测试手机类的闹钟功能，通过匿名内部类(对象)作为参数，打印：懒猪起床了
        4.再传入另一个匿名内部类(对象)，打印：小伙伴上课了
         */
        CellPhone cellPhone = new CellPhone();
        //老韩解读
        //1. 传递的是实现了 Bell接口的匿名内部类 InnerClassExercise02$1
        //2. 重写了 ring
        //3. Bell bell = new Bell() {//new Bell....  为运行类型
        //            @Override
        //            public void ring() {
        //                System.out.println("懒猪起床了");
        //            }
        //        }
        cellPhone.alarmClock(new Bell() {//匿名内部类
            @Override
            public void ring() {
                System.out.println("懒猪起床了");
            }
        });

        cellPhone.alarmClock(new Bell() {
            @Override
            public void ring() {
                System.out.println("小伙伴上课了");
            }
        });
    }
}
interface Bell{ //接口
    void ring();//方法
}
class CellPhone{//类
    public void alarmClock(Bell bell){//形参是Bell接口类型
        System.out.println(bell.getClass());
        bell.ring();//动态绑定
    }
}

```



#### 10.9.7 内部类的分类

![img](https://img-blog.csdnimg.cn/img_convert/e64bc8bdb3227182692b36345156fa70.png)

![img](https://img-blog.csdnimg.cn/img_convert/1b1407a5fe4da1c1cc63cc39a556abc2.png)

![img](https://img-blog.csdnimg.cn/img_convert/84eef441a147231cc9a0d0ca4f8a7b83.png)

```java
package com.hspedu.innerclass;

public class MemberInnerClass01 {
    public static void main(String[] args) {
        Outer08 outer08 = new Outer08();
        outer08.t1();

        //外部其他类，使用成员内部类的三种方式
        //老韩解读
        // 第一种方式
        // outer08.new Inner08(); 相当于把 new Inner08()当做是outer08成员
        // 这就是一个语法，不要特别的纠结.
        Outer08.Inner08 inner08 = outer08.new Inner08();
        inner08.say();
        // 第二方式 在外部类中，编写一个方法，可以返回 Inner08对象
        Outer08.Inner08 inner08Instance = outer08.getInner08Instance();
        inner08Instance.say();


    }
}

class Outer08 { //外部类
    private int n1 = 10;
    public String name = "张三";

    private void hi() {
        System.out.println("hi()方法...");
    }

    //1.注意: 成员内部类，是定义在外部内的成员位置上
    //2.可以添加任意访问修饰符(public、protected 、默认、private),因为它的地位就是一个成员
    public class Inner08 {//成员内部类
        private double sal = 99.8;
        private int n1 = 66;
        public void say() {
            //可以直接访问外部类的所有成员，包含私有的
            //如果成员内部类的成员和外部类的成员重名，会遵守就近原则.
            //，可以通过  外部类名.this.属性 来访问外部类的成员
            System.out.println("n1 = " + n1 + " name = " + name + " 外部类的n1=" + Outer08.this.n1);
            hi();
        }
    }
    //方法，返回一个Inner08实例
    public Inner08 getInner08Instance(){
        return new Inner08();
    }


    //写方法
    public void t1() {
        //使用成员内部类
        //创建成员内部类的对象，然后使用相关的方法
        Inner08 inner08 = new Inner08();
        inner08.say();
        System.out.println(inner08.sal);
    }
}


```



#### 10.9.8 静态内部类

![img](https://img-blog.csdnimg.cn/img_convert/d8a4ed60460db641b3201433ee4062ee.png)

![img](https://img-blog.csdnimg.cn/img_convert/5a95062def48bf4d51ce677a343aab5f.png)

![img](https://img-blog.csdnimg.cn/img_convert/167fb01f7d2ee0ad01a624ba938379d5.png)

![img](https://img-blog.csdnimg.cn/img_convert/9be85c56b3d9c3e58ab5c367df032383.png)

![img](https://img-blog.csdnimg.cn/img_convert/f6ad9e9da897220ff959ebd41f879efa.png)

![img](https://img-blog.csdnimg.cn/img_convert/d5a018e1dfb58f89d39ee312e7032833.png)

```java
package com.hspedu.innerclass;

public class StaticInnerClass01 {
    public static void main(String[] args) {
        Outer10 outer10 = new Outer10();
        outer10.m1();

        //外部其他类 使用静态内部类
        //方式1
        //因为静态内部类，是可以通过类名直接访问(前提是满足访问权限)
        Outer10.Inner10 inner10 = new Outer10.Inner10();//若static前面加private就无法这样访问
        inner10.say();
        //方式2
        //编写一个方法，可以返回静态内部类的对象实例.
        Outer10.Inner10 inner101 = outer10.getInner10();
        System.out.println("============");
        inner101.say();

        Outer10.Inner10 inner10_ = Outer10.getInner10_();//静态方法
        System.out.println("************");
        inner10_.say();
    }
}

class Outer10 { //外部类
    private int n1 = 10;
    private static String name = "张三";
    private static void cry() {}
    //Inner10就是静态内部类
    //1. 放在外部类的成员位置
    //2. 使用static 修饰
    //3. 可以直接访问外部类的所有静态成员，包含私有的，但不能直接访问非静态成员
    //4. 在static前可以添加任意访问修饰符(public、protected 、默认、private),因为它的地位就是一个成员
    //5. 作用域 ：同其他的成员，为整个类体
    static class Inner10 {
        private static String name = "韩顺平教育";
        public void say() {
            //如果外部类和静态内部类的成员重名时，静态内部类访问的时，
            //默认遵循就近原则，如果想访问外部类的成员，则可以使用 （外部类名.成员）
            System.out.println(name + " 外部类name= " + Outer10.name);
            cry();
        }
    }

    public void m1() { //外部类---访问------>静态内部类 访问方式：创建对象，再访问
        Inner10 inner10 = new Inner10();
        inner10.say();
    }

    public Inner10 getInner10() {
        return new Inner10();
    }

    public static Inner10 getInner10_() {
        return new Inner10();
    }
}


```



#### 10.9.9 课堂测试

![img](https://img-blog.csdnimg.cn/img_convert/420820d8c926f45f3f09515af57416a5.png)



```java
package com.hspedu.innerclass;

public class InnerClassExercise {
    public static void main(String[] args) {

    }
}

class Test {//外部类

    public Test() {//构造器
        Inner s1 = new Inner();
        s1.a = 10;
        Inner s2 = new Inner();
        System.out.println(s2.a);
    }

    class Inner { //内部类，成员内部类
        public int a = 5;
    }

    public static void main(String[] args) {
        Test t = new Test();
        Inner r = t.new Inner();//5
        System.out.println(r.a);//5
    }
}

```



## 第 11 章枚举和注解

### 11.1 需求

![img](https://img-blog.csdnimg.cn/img_convert/bffc11d232b483eaa373e55306da8f00.png)

```java
package com.hspedu.enum_;
/**
 * @author 韩顺平
 * @version 1.0
 */
public class Enumeration01 {
    public static void main(String[] args) {
        //使用
        Season spring = new Season("春天", "温暖");
        Season winter = new Season("冬天", "寒冷");
        Season summer = new Season("夏天", "炎热");
        Season autumn = new Season("秋天", "凉爽");
//        autumn.setName("XXX");
//        autumn.setDesc("非常的热..");
        //因为对于季节而已，他的对象(具体值)，是固定的四个，不会有更多
        //安老师的这个设计类的思路，不能体现季节是固定的四个对象
        //因此，这样的设计不好===> 枚举类[枚: 一个一个 举： 例举 , 即把具体的对象一个一个例举出来的类
        // 就称为枚举类]
        Season other = new Season("红天", "~~~");
    }
}
class Season{//类
    private String name;
    private String desc;//描述

    public Season(String name, String desc) {
        this.name = name;
        this.desc = desc;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getDesc() {
        return desc;
    }

    public void setDesc(String desc) {
        this.desc = desc;
    }
}

```



### 11.2 解决方案-枚举

![img](https://img-blog.csdnimg.cn/img_convert/c701e4295f724527ab20e73a8786c8bb.png)



### 11.3 枚举的两种实现方式

![img](https://img-blog.csdnimg.cn/img_convert/2bff53476e90647d4bb4ef2d594afb1a.png)



#### 11.3.1 自定义类实现枚举

![img](https://img-blog.csdnimg.cn/img_convert/f008872cfe1789a3959302bfc1f3ad60.png)

```java
package com.hspedu.enum_;


public class Enumeration02 {
    public static void main(String[] args) {
        System.out.println(Season.AUTUMN);
        System.out.println(Season.SPRING);
    }
}

//演示字定义枚举实现
class Season {//类
    private String name;
    private String desc;//描述

    //定义了四个对象, 固定.
    public static final Season SPRING = new Season("春天", "温暖");
    public static final Season WINTER = new Season("冬天", "寒冷");
    public static final Season AUTUMN = new Season("秋天", "凉爽");
    public static final Season SUMMER = new Season("夏天", "炎热");


    //1. 将构造器私有化,目的防止 直接 new
    //2. 去掉setXxx方法, 防止属性被修改
    //3. 在Season 内部，直接创建固定的对象
    //4. 优化，可以加入 final 修饰符
    private Season(String name, String desc) {
        this.name = name;
        this.desc = desc;
    }

    public String getName() {
        return name;
    }

    public String getDesc() {
        return desc;
    }

    @Override
    public String toString() {
        return "Season{" +
                "name='" + name + '\'' +
                ", desc='" + desc + '\'' +
                '}';
    }
}
```



#### 11.3.2 自定义类小结

![img](https://img-blog.csdnimg.cn/img_convert/758c7f72a784e6de213ec6b91748a5f2.png)



#### 11.3.3 enum关键字实现枚举

![img](https://img-blog.csdnimg.cn/img_convert/a7edb0515eeb5d9460aa6fb13e69e562.png)

```java
package com.hspedu.enum_;


public class Enumeration03 {
    public static void main(String[] args) {
        System.out.println(Season2.AUTUMN);
        System.out.println(Season2.SUMMER);
    }
}
//演示使用enum关键字来实现枚举类
enum  Season2 {//类


    //定义了四个对象, 固定.
//    public static final Season SPRING = new Season("春天", "温暖");
//    public static final Season WINTER = new Season("冬天", "寒冷");
//    public static final Season AUTUMN = new Season("秋天", "凉爽");
//    public static final Season SUMMER = new Season("夏天", "炎热");
    //如果使用了enum 来实现枚举类
    //1. 使用关键字 enum 替代 class
    //2. public static final Season SPRING = new Season("春天", "温暖") 直接使用
    //   SPRING("春天", "温暖") 解读 常量名(实参列表)
    //3. 如果有多个常量(对象)， 使用 ,号间隔即可
    //4. 如果使用enum 来实现枚举，要求将定义常量对象，写在前面
    //5. 如果我们使用的是无参构造器，创建常量对象，则可以省略 ()
    SPRING("春天", "温暖"), WINTER("冬天", "寒冷"), AUTUMN("秋天", "凉爽"),
    SUMMER("夏天", "炎热")/*, What()//调用无参构造器，括号也可以省略*/;

    private String name;
    private String desc;//描述

    private Season2() {//无参构造器

    }

    private Season2(String name, String desc) {
        this.name = name;
        this.desc = desc;
    }

    public String getName() {
        return name;
    }

    public String getDesc() {
        return desc;
    }

    @Override
    public String toString() {
        return "Season{" +
                "name='" + name + '\'' +
                ", desc='" + desc + '\'' +
                '}';
    }
}


```



#### 11.3.4 enum使用细节

![img](https://img-blog.csdnimg.cn/img_convert/0fb3a8ee82b1e1096b0f2dcfca121869.png)



#### 11.3.5 enum课堂练习

第一题

![img](https://img-blog.csdnimg.cn/img_convert/1e3603a3974de3c512e7b29eea5bb740.png)

加上privte Gender (String name){}之后是错误的，后面必须再加上private Gender{};

![img](https://img-blog.csdnimg.cn/img_convert/a8b1cc0731021cfb1dd08e366ad2b685.png)





第二题

![img](https://img-blog.csdnimg.cn/img_convert/2e7bafa0bf2225db2c307df179a04fa5.png)

```java
package com.hspedu.enum_;


public class EnumExercise01 {
    public static void main(String[] args) {
        Gender2 boy = Gender2.BOY;//OK
        Gender2 boy2 = Gender2.BOY;//OK
        System.out.println(boy);//输出BOY //本质就是调用 Gender2 的父类Enum的 toString()
//        public String toString() {
//            return name;
//        }
        System.out.println(boy2 == boy);  //True
    }
}

enum Gender2{ //父类 Enum 的toString
    BOY , GIRL;
}


```



#### 11.3.6 enum常用方法说明

![img](https://img-blog.csdnimg.cn/img_convert/d95ca573f2d4aafb6398195f13486acc.png)

![img](https://img-blog.csdnimg.cn/img_convert/c5188399bffc60c6ac40bef7fe46a0a3.png)

![img](https://img-blog.csdnimg.cn/img_convert/fbd801a78e8d12179afe48ba26cb215e.png)

```java
package com.hspedu.enum_;


 //* 演示Enum类的各种方法的使用

public class EnumMethod {
    public static void main(String[] args) {
        //使用Season2 枚举类，来演示各种方法
        Season2 autumn = Season2.AUTUMN;

        //输出枚举对象的名字
        System.out.println(autumn.name());


        //ordinal() 输出的是该枚举对象的次序/编号，从0开始编号
        //AUTUMN 枚举对象是第三个，因此输出 2
        System.out.println(autumn.ordinal());


        //从反编译可以看出 values方法，返回 Season2[]
        //含有定义的所有枚举对象
        Season2[] values = Season2.values();
        System.out.println("===遍历取出枚举对象(增强for)====");
        for (Season2 season: values) {//增强for循环
            System.out.println(season);
        }


        //valueOf：将字符串转换成枚举对象，要求字符串必须•为已有的常量名，否则报异常
        //执行流程
        //1. 根据你输入的 "AUTUMN" 到 Season2的枚举对象去查找
        //2. 如果找到了，就返回，如果没有找到，就报错
        Season2 autumn1 = Season2.valueOf("AUTUMN");//若输入Season2 autumn1 = Season2.valueOf("HSP");会报错
        System.out.println("autumn1=" + autumn1);
        System.out.println(autumn == autumn1);



        //compareTo：比较两个枚举常量，比较的就是编号
        //老韩解读
        //1. 就是把 Season2.AUTUMN 枚举对象的编号 和 Season2.SUMMER枚举对象的编号比较
        //2. 看看结果
        /*
        public final int compareTo(E o) {

            return self.ordinal - other.ordinal;
        }
        Season2.AUTUMN的编号[2] - Season2.SUMMER的编号[3]
         */
        System.out.println(Season2.AUTUMN.compareTo(Season2.SUMMER));



        //补充了一个增强for
//        int[] nums = {1, 2, 9};
//        //普通的for循环
//        System.out.println("=====普通的for=====");
//        for (int i = 0; i < nums.length; i++) {
//            System.out.println(nums[i]);
//        }
//        System.out.println("=====增强的for=====");
//        //执行流程是 依次从nums数组中取出数据，赋给i, 如果取出完毕，则退出for
//        for(int i : nums) {
//            System.out.println("i=" + i);
//        }
    }
}

输出结果：
AUTUMN
2
===遍历取出枚举对象(增强for)====
Season{name='春天', desc='温暖'}
Season{name='冬天', desc='寒冷'}
Season{name='秋天', desc='凉爽'}
Season{name='夏天', desc='炎热'}
autumn1=Season{name='秋天', desc='凉爽'}
true
-1
```



#### 11.3.7 enum课堂练习

![img](https://img-blog.csdnimg.cn/img_convert/ec923eace6c1ec420649ce951c3ac906.png)



```java
package com.hspedu.enum_;

/**
 * @author 韩顺平
 * @version 1.0
 */
public class EnumExercise02 {
    public static void main(String[] args) {
        //获取到所有的枚举对象， 即数组
        Week[] weeks = Week.values();
        //遍历，使用增强for
        System.out.println("===所有星期的信息如下===");
        for (Week week : weeks) {
            System.out.println(week);
        }
    }
}

/*
声明Week枚举类，其中包含星期一至星期日的定义；
MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY;
使用values 返回所有的枚举数组, 并遍历 , 输出左图效果

 */

enum Week   {//不能在继承其他类，它之前已经继承
    //定义Week的枚举对象
    MONDAY("星期一"), TUESDAY("星期二"), WEDNESDAY("星期三"), THURSDAY("星期四"),
    FRIDAY("星期五"), SATURDAY("星期六"), SUNDAY("星期日");
    private String name;

    private Week(String name) {//构造器
        this.name = name;
    }

    @Override
    public String toString() {
        return name;
    }
}

```



![img](https://img-blog.csdnimg.cn/img_convert/70124122a887e38d2ad4d9481fb764b2.png)

```java
package com.hspedu.enum_;


public class EnumDetail {
    public static void main(String[] args) {
        Music.CLASSICMUSIC.playing();
    }
}
class A {

}

//1.使用enum关键字后，就不能再继承其它类了，因为enum会隐式继承Enum，而Java是单继承机制
//enum Season3 extends A {
//
//}
//2.enum实现的枚举类，仍然是一个类，所以还是可以实现接口的.
interface IPlaying {
    public void playing();
}
enum Music implements IPlaying {
    CLASSICMUSIC;
    @Override
    public void playing() {
        System.out.println("播放好听的音乐...");
    }
}
```



### 11.4 注解

#### 11.4.1 注解的理解

![img](https://img-blog.csdnimg.cn/img_convert/00bbcc6959f387f704ee769f4093ac3e.png)



#### 11.4.2 基本的 Annotation 介绍

![img](https://img-blog.csdnimg.cn/img_convert/d62883e2508c5f32d9b9a8f7c96b9c56.png)



#### 11.4.3 基本的 Annotation 应用案例

![img](https://img-blog.csdnimg.cn/img_convert/4525ea238572f5b8154ca8080a3a280e.png)

```java
package com.hspedu.annotation_;
public class Override_ {
    public static void main(String[] args) {

    }
}
class Father{//父类

    public void fly(){
        int i = 0;
        System.out.println("Father fly...");
    }
    public void say(){}

}

class Son extends Father {//子类
    //老韩解读
    //1. @Override 注解放在fly方法上，表示子类的fly方法时重写了父类的fly
    //2. 这里如果没有写 @Override 还是重写了父类fly
    //3. 如果你写了@Override注解，编译器就会去检查该方法是否真的重写了父类的
    //   方法，如果的确重写了，则编译通过，如果没有构成重写，则编译错误
    //4. 看看 @Override的定义
    //   解读： 如果发现 @interface 表示一个 注解类
    /*
        @Target(ElementType.METHOD)
        @Retention(RetentionPolicy.SOURCE)
        public @interface Override {
        }
     */
    @Override   //说明
    public void fly() {
        System.out.println("Son fly....");
    }
    @Override
    public void say() {}
}
```







![img](https://img-blog.csdnimg.cn/img_convert/c52a0e84f218af5a7a063b47729aaab3.png)

![img](https://img-blog.csdnimg.cn/img_convert/18a0897a703b8ac74d9fc37402ec25e3.png)

```java
package com.hspedu.annotation_;
public class Deprecated_ {
    public static void main(String[] args) {
        A a = new A();
        a.hi();
        System.out.println(a.n1);
    }
}

//老韩解读
//1. @Deprecated 修饰某个元素, 表示该元素已经过时
//2. 即不在推荐使用，但是仍然可以使用
//3. 查看 @Deprecated 注解类的源码
//4. 可以修饰方法，类，字段, 包, 参数  等等
//5. @Deprecated 可以做版本升级过渡使用
/*
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(value={CONSTRUCTOR, FIELD, LOCAL_VARIABLE, METHOD, PACKAGE, PARAMETER, TYPE})
public @interface Deprecated {
}
 */
@Deprecated
class A {
    @Deprecated
    public int n1 = 10;
    @Deprecated
    public void hi(){

    }
}

```



#### 11.4.4

![img](https://img-blog.csdnimg.cn/img_convert/3255a036dbd472372d1f9c2e754a22c3.png)

```java
package com.hspedu.annotation_;

import java.util.ArrayList;
import java.util.List;

@SuppressWarnings({"rawtypes", "unchecked", "unused"})
public class SuppressWarnings_ {

    //老韩解读
    //1. 当我们不希望看到这些警告的时候，可以使用 SuppressWarnings注解来抑制警告信息
    //2. 在{""} 中，可以写入你希望抑制(不显示)警告信息
    //3. 可以指定的警告类型有
    //          all，抑制所有警告
    //          boxing，抑制与封装/拆装作业相关的警告
    //        //cast，抑制与强制转型作业相关的警告
    //        //dep-ann，抑制与淘汰注释相关的警告
    //        //deprecation，抑制与淘汰的相关警告
    //        //fallthrough，抑制与switch陈述式中遗漏break相关的警告
    //        //finally，抑制与未传回finally区块相关的警告
    //        //hiding，抑制与隐藏变数的区域变数相关的警告
    //        //incomplete-switch，抑制与switch陈述式(enum case)中遗漏项目相关的警告
    //        //javadoc，抑制与javadoc相关的警告
    //        //nls，抑制与非nls字串文字相关的警告
    //        //null，抑制与空值分析相关的警告
    //        //rawtypes，抑制与使用raw类型相关的警告
    //        //resource，抑制与使用Closeable类型的资源相关的警告
    //        //restriction，抑制与使用不建议或禁止参照相关的警告
    //        //serial，抑制与可序列化的类别遗漏serialVersionUID栏位相关的警告
    //        //static-access，抑制与静态存取不正确相关的警告
    //        //static-method，抑制与可能宣告为static的方法相关的警告
    //        //super，抑制与置换方法相关但不含super呼叫的警告
    //        //synthetic-access，抑制与内部类别的存取未最佳化相关的警告
    //        //sync-override，抑制因为置换同步方法而遗漏同步化的警告
    //        //unchecked，抑制与未检查的作业相关的警告
    //        //unqualified-field-access，抑制与栏位存取不合格相关的警告
    //        //unused，抑制与未用的程式码及停用的程式码相关的警告
    //4. 关于SuppressWarnings 作用范围是和你放置的位置相关
    //   比如 @SuppressWarnings放置在 main方法，那么抑制警告的范围就是 main
    //   通常我们可以放置具体的语句, 方法, 类.
    //5.  看看 @SuppressWarnings 源码
    //(1) 放置的位置就是 TYPE, FIELD, METHOD, PARAMETER, CONSTRUCTOR, LOCAL_VARIABLE
    //(2) 该注解类有数组 String[] values() 设置一个数组比如 {"rawtypes", "unchecked", "unused"}
    /*
        @Target({TYPE, FIELD, METHOD, PARAMETER, CONSTRUCTOR, LOCAL_VARIABLE})
            @Retention(RetentionPolicy.SOURCE)
            public @interface SuppressWarnings {

                String[] value();
        }
     */
    public static void main(String[] args) {
        List list = new ArrayList();
        list.add("jack");
        list.add("tom");
        list.add("mary");
        int i;
        System.out.println(list.get(1));

    }

    public void f1() {
//        @SuppressWarnings({"rawtypes"})
        List list = new ArrayList();


        list.add("jack");
        list.add("tom");
        list.add("mary");
//        @SuppressWarnings({"unused"})
        int i;
        System.out.println(list.get(1));
    }
}

```

![img](https://img-blog.csdnimg.cn/img_convert/31e43c647f8b503a3987da0bc61c29f9.png)



#### 11.4.5 JDK的元Annotation（元注解 ，了解）

![img](https://img-blog.csdnimg.cn/img_convert/ac162d9f73d6b08ce43a050d76abc5bb.png)

@Retention

![img](https://img-blog.csdnimg.cn/img_convert/9cb1e9e4efd9f4791c161a2ca6c343b9.png)



![img](https://img-blog.csdnimg.cn/img_convert/4e7429678994b9ba9b116cecbf2e6aa3.png)



@Target

![img](https://img-blog.csdnimg.cn/img_convert/02e7b902fb8309ca518e4d597a11f74c.png)

![img](https://img-blog.csdnimg.cn/img_convert/8326b824c263ceda32025e090cd48575.png)

@Documented

![img](https://img-blog.csdnimg.cn/img_convert/ab2e04d0383c80464b95b7b967c7e9c2.png)

![img](https://img-blog.csdnimg.cn/img_convert/ab2e04d0383c80464b95b7b967c7e9c2.png)

@Inherited 注解

![img](https://img-blog.csdnimg.cn/img_convert/bc95e1836f484367dfc462e608908209.png)







### 11.5 第十章作业







## 第 12 章 异常-Exception

### 12.1 看个实际的问题和一段代码

![img](https://img-blog.csdnimg.cn/img_convert/323ea0a84d5ff61ad9329c217bde8df6.png)

### 12.2 解决方案-异常捕获

对异常进行捕获，保证程序可以继续运行.

看老师的代码演示 try-catch

```java
package com.hspedu.exception_;

public class Exception01 {
    public static void main(String[] args)  {
        int num1 = 10;
        int num2 = 0;//Scanner();

        //老韩解读
        //1. num1 / num2 => 10 / 0
        //2. 当执行到 num1 / num2 因为 num2 = 0, 程序就会出现(抛出)异常 ArithmeticException
        //3. 当抛出异常后，程序就退出，崩溃了 , 下面的代码就不在执行
        //4. 大家想想这样的程序好吗? 不好，不应该出现了一个不算致命的问题，就导致整个系统崩溃
        //5. java 设计者，提供了一个叫 异常处理机制来解决该问题
//        int res = num1 / num2;
        //如果程序员，认为一段代码可能出现异常/问题，可以使用try-catch异常处理机制来解决
        //从而保证程序的健壮性
        //将该代码块->选中->快捷键 ctrl + alt + t -> 选中 try-catch
        //6. 如果进行异常处理，那么即使出现了异常，程序可以继续执行
        try {
            int res = num1 / num2;
        } catch (Exception e) {
            //e.printStackTrace();
            System.out.println("出现异常的原因=" + e.getMessage());//输出异常信息
        }

        System.out.println("程序继续运行....");

    }
}

```



### 12.3 异常的介绍

![img](https://img-blog.csdnimg.cn/img_convert/172cddc4af127935891cebd01ee644d8.png)



### 12.4 异常体系图一览

#### 12.4.1 异常体系图

![img](https://img-blog.csdnimg.cn/img_convert/13a5583f6b916a86a6c02aa9102a8d92.png)



#### 12.4.2 异常体系图的小结

![img](https://img-blog.csdnimg.cn/img_convert/4321375ff3d534308e999314225cec7a.png)



### 12.5 常见的运行时异常

![img](https://img-blog.csdnimg.cn/img_convert/22375107d8f923534427d2fc0b2c24fa.png)

#### 12.5.1 NullPointerException 空指针异常

![img](https://img-blog.csdnimg.cn/img_convert/f38356765b729852d54136b7442b0323.png)

```java
package com.hspedu.exception_;

public class NullPointerException_ {
    public static void main(String[] args) {

        String name = null;//异常处
        System.out.println(name.length());
    }
}
```



#### 12.5.2 ArithmeticException 数学运算异常

![img](https://img-blog.csdnimg.cn/img_convert/4899045247daa2277d4530c5e2d2d2c5.png)







#### 12.5.3 ArrayIndexOutOfBoundsException 数组下标越界异常

![img](https://img-blog.csdnimg.cn/img_convert/6d999b2946c46a3ea6b576589664e4e8.png)



```java
package com.hspedu.exception_;

public class ArrayIndexOutOfBoundsException_ {
    public static void main(String[] args) {
        int[] arr = {1,2,4};
        for (int i = 0; i <= arr.length; i++) {//异常处
            System.out.println(arr[i]);
        }
    }
}

```



#### 12.5.4 ClassCastException 类型转换异常

![img](https://img-blog.csdnimg.cn/img_convert/a3c92df1d08cad3183cffc53c36d306d.png)

```java
package com.hspedu.exception_;

public class ClassCastException_ {
    public static void main(String[] args) {
        A b = new B(); //向上转型
        B b2 = (B)b;//向下转型，这里是OK
        C c2 = (C)b;//这里抛出ClassCastException，B和C没有关系
    }
}
class A {}
class B extends A {}
class C extends A {}


```



#### 12.5.5 NumberFormatException 数字格式不正确异常

![img](https://img-blog.csdnimg.cn/img_convert/d9df866ac272498c523a504107e8833f.png)

```java
package com.hspedu.exception_;

public class NumberFormatException_ {
    public static void main(String[] args) {
        String name = "韩顺平教育";
        //将String 转成 int
        int num = Integer.parseInt(name);//抛出NumberFormatException
        System.out.println(num);//1234
    }
}

```



### 12.6 编译异常

#### 12.6.1 介绍

![img](https://img-blog.csdnimg.cn/img_convert/35ce57ec83a58f94d45d0dca8b6258af.png)

#### 12.6.2 常见的编译异常

![img](https://img-blog.csdnimg.cn/img_convert/8d264e331092b389abb36d9bf7aa958b.png)



#### 12.6.3 案例说明

![img](https://img-blog.csdnimg.cn/img_convert/9c9307a5a476657af0c0f3afb5e5b062.png)

```java
package com.hspedu.exception_;

import java.io.FileInputStream;
import java.io.IOException;


public class Exception02 {
    public static void main(String[] args) {

        try {
            FileInputStream fis;
            fis = new FileInputStream("d:\\aa.jpg");
            int len;
            while ((len = fis.read()) != -1) {
                System.out.println(len);
            }
            fis.close();
        } catch (IOException e) {
            e.printStackTrace();
        }

    }
}

```



#### 12.6.4 异常课堂练习

看看下面代码是否正确，为什么？ 课堂练习 4 个题

![img](https://img-blog.csdnimg.cn/img_convert/4d1e26b219172396c696166e3af27ce3.png)



### 12.7 异常处理

#### 12.8.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/34783c09942bd50ea6ca211690a536a0.png)

#### 12.8.2 异常处理的方式

![img](https://img-blog.csdnimg.cn/img_convert/6dbca94b037fa11422f9d2ce4dd4bf8a.png)



#### 12.8.3 示意图

![img](https://img-blog.csdnimg.cn/img_convert/574338b952b678d36f27ec8c8c3bfee8.png)

![img](https://img-blog.csdnimg.cn/img_convert/386955868c8c4a5076feaea761b10c2c.png)



### 12.8 try-catch 异常处理

#### 12.8.1 try-catch 方式处理异常说明 TryCatch01.java

![img](https://img-blog.csdnimg.cn/img_convert/6b6d485fbef3fe39c5c60b379a55d093.png)



#### 12.8.2 try-catch 方式处理异常-快速入门

```java
public static void main(String[] args) {
    int num1 = 10; 
    int num2 = 0; 
    try {
        int res = num1 / num2;
    } catch (Exception e) {
        System.out.println(e.getMessage());
    }
}

```



#### 12.8.3 try-catch 方式处理异常-注意事项 TryCatchDetail.java

![img](https://img-blog.csdnimg.cn/img_convert/f04a47fffe68e3365a460ff7140c18e3.png)

```java
package com.hspedu.try_;


public class TryCatchDetail {
    public static void main(String[] args) {

        //ctrl + atl + t
        //老韩解读
        //1. 如果异常发生了，则异常发生后面的代码不会执行，直接进入到catch块
        //2. 如果异常没有发生，则顺序执行try的代码块，不会进入到catch
        //3. 如果希望不管是否发生异常，都执行某段代码(比如关闭连接，释放资源等)则使用如下代码- finally
        try {
            String str = "韩顺平";
            int a = Integer.parseInt(str);
            System.out.println("数字：" + a);
        } catch (NumberFormatException e) {
            System.out.println("异常信息=" + e.getMessage());
        } finally {
            System.out.println("finally代码块被执行...");
        }

        System.out.println("程序继续...");

    }
}

```



![img](https://img-blog.csdnimg.cn/img_convert/3ce013bfcab858b5063bfef608689ef0.png)

```java
package com.hspedu.try_;

public class TryCatchDetail02 {
    public static void main(String[] args) {

        //老韩解读
        //1.如果try代码块有可能有多个异常
        //2.可以使用多个catch 分别捕获不同的异常，相应处理
        //3.要求子类异常写在前面，父类异常写在后面
        try {
            Person person = new Person();
            //person = null;
            System.out.println(person.getName());//NullPointerException
            int n1 = 10;
            int n2 = 0;
            int res = n1 / n2;//ArithmeticException
        } catch (NullPointerException e) {
            System.out.println("空指针异常=" + e.getMessage());
        } catch (ArithmeticException e) {
            System.out.println("算术异常=" + e.getMessage());
        } catch (Exception e) {
            System.out.println(e.getMessage());
        } finally {
        }


    }
}

class Person {
    private String name = "jack";

    public String getName() {
        return name;
    }
}

```



![img](https://img-blog.csdnimg.cn/img_convert/d0b54281892514892fb1ae985ca475a6.png)

```java
package com.hspedu.try_;

public class TryCatchDetail03 {
    public static void main(String[] args) {

        /*
        可以进行 try-finally 配合使用, 这种用法相当于没有捕获异常，
        因此程序会直接崩掉/退出。应用场景，就是执行一段代码，不管是否发生异常，
        都必须执行某个业务逻辑
         */
        try{
            int n1 = 10;
            int n2 = 0;
            System.out.println(n1 / n2);
        }finally {
            System.out.println("执行了finally..");
        }
        System.out.println("程序继续执行..");

    }

}

```



#### 12.8.4 异常处理的课堂练习

题 1 TryCatchExercise01.java

![img](https://img-blog.csdnimg.cn/img_convert/393b2109cd82f4b83cc3d1f3cc9bcd6d.png)

没有给数组具体的值，三个全为null。



题 2 TryCatchExercise02.java

![img](https://img-blog.csdnimg.cn/img_convert/36443e73772ac63d23fa41c6691deaee.png)



题 3 TryCatchExercise03.java

![img](https://img-blog.csdnimg.cn/img_convert/2a8b793101e78894415491848237b152.png)



finally无return



#### 12.8.5 try-catch-finally 执行顺序小结

![img](https://img-blog.csdnimg.cn/img_convert/22df4c6f94420eef40cfa9475e6e6446.png)





#### 12.8.6 课后练习题: TryCatchExercise04.java

```java
package com.hspedu.try_;

import java.util.Scanner;


public class TryCatchExercise04 {
    public static void main(String[] args) {

        //如果用户输入的不是一个整数，就提示他反复输入，直到输入一个整数为止
        //思路
        //1. 创建Scanner对象
        //2. 使用无限循环，去接收一个输入
        //3. 然后将该输入的值，转成一个int
        //4. 如果在转换时，抛出异常，说明输入的内容不是一个可以转成int的内容
        //5. 如果没有抛出异常，则break 该循环
        Scanner scanner = new Scanner(System.in);
        int num = 0;
        String inputStr = "";
        while (true) {

            System.out.println("请输入一个整数:"); //
            inputStr = scanner.next();
            try {
                num = Integer.parseInt(inputStr); //这里是可能抛出异常
                break;
            } catch (NumberFormatException e) {
                System.out.println("你输入的不是一个整数:");
            }
        }

        System.out.println("你输入的值是=" + num);
    }
}

```







### 12.9 throws 异常处理

#### 12.9.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/bbd1ee7a31f8047957ca5bc48893d203.png)

#### 12.9.2 快速入门案例

![img](https://img-blog.csdnimg.cn/img_convert/ce1bb53784777d36effe625eb71370f0.png)

```java
package com.hspedu.throws_;

import java.io.FileInputStream;
import java.io.FileNotFoundException;

public class Throws01 {
    public static void main(String[] args) {

    }

    public void f2() throws FileNotFoundException,NullPointerException,ArithmeticException {
        //创建了一个文件流对象
        //老韩解读:
        //1. 这里的异常是一个FileNotFoundException 编译异常
        //2. 使用前面讲过的 try-catch-finally
        //3. 使用throws ,抛出异常, 让调用f2方法的调用者(方法)处理
        //4. throws后面的异常类型可以是方法中产生的异常类型，也可以是它的父类 public void f2() throws Exception{}
        //5. throws 关键字后也可以是 异常列表, 即可以抛出多个异常
        FileInputStream fis = new FileInputStream("d://aa.txt");

    }
}

```



#### 12.9.3 注意事项和使用细节 ThrowsDetail.java

![img](https://img-blog.csdnimg.cn/img_convert/0980dec1aff8e3eee8008e84e989d66d.png)

```java
package com.hspedu.throws_;

import java.io.FileInputStream;
import java.io.FileNotFoundException;

public class ThrowsDetail {
    public static void main(String[] args) {
        f2();
    }

    public static void f2() /*throws ArithmeticException*/ {
        //1.对于编译异常，程序中必须处理，比如 try-catch 或者 throws
        //2.对于运行时异常，程序中如果没有处理，默认就是throws的方式处理
        //eg：public static void f1() throws FileNotFoundException{}

        int n1 = 10;
        int n2 = 0;
        double res = n1 / n2;
    }

    public static void f1()  {
        //这里大家思考问题 调用f3() 报错
        //老韩解读
        //1、因为f3() 方法抛出的是一个编译异常
        //2、即这时，就要f1() 必须处理这个编译异常
        //3、在f1() 中，要么 try-catch-finally包住f3() ,或者继续throws 这个编译异常即public static void f1() throws FileNotFoundException {}
        f3(); // 抛出异常
    }
    public static void f3() throws FileNotFoundException {
        FileInputStream fis = new FileInputStream("d://aa.txt");
    }

    
    public static void f4() {
        //老韩解读:
        //1. 在f4()中调用方法f5() 是OK
        //2. 原因是f5() 抛出的是运行异常
        //3. 而java中，并不要求程序员显示处理,因为有默认处理机制f4()后面会自动加
        f5();
    }
    public static void f5() throws ArithmeticException {

    }
}

class Father { //父类
    public void method() throws RuntimeException {
    }
}

class Son extends Father {//子类
    //3. 子类重写父类的方法时，对抛出异常的规定:子类重写的方法，
    //   所抛出的异常类型要么和父类抛出的异常一致，要么为父类抛出的异常类型的子类型
    //4. 在throws 过程中，如果有方法 try-catch , 就相当于处理异常，就可以不必throws
    @Override
    public void method() throws ArithmeticException {
    }
}


```





### 12.10 自定义异常

#### 12.10.1 基本概念

![img](https://img-blog.csdnimg.cn/img_convert/73c5036b5f0c3ca0eaad7943d4873deb.png)



#### 12.10.2 自定义异常的步骤

![img](https://img-blog.csdnimg.cn/img_convert/a39b720769cd37c0fd5dd703e0c3c9dd.png)

#### 12.10.3 自定义异常的应用实例 CustomException.java

![img](https://img-blog.csdnimg.cn/img_convert/1a29d58d67323725b1ffd9d7f0ab8148.png)

```java
package com.hspedu.customexception_;


public class CustomException {
    public static void main(String[] args) /*throws AgeException*/ {

        int age = 180;
        //要求范围在 18 – 120 之间，否则抛出一个自定义异常
        if(!(age >= 18 && age <= 120)) {
            //这里我们可以通过构造器，设置信息
            throw new AgeException("年龄需要在 18~120之间");//抛给调用者main
        }
        System.out.println("你的年龄范围正确.");
    }
}
//自定义一个异常
//老韩解读
//1. 一般情况下，我们自定义异常是继承 RuntimeException
//2. 即把自定义异常做成 运行时异常，好处时，我们可以使用默认的处理机制
//3. 即比较方便
class AgeException extends RuntimeException {
    public AgeException(String message) {//构造器
        super(message);
    }
}

```



### 12.11 throw 和 throws 的区别

#### 12.11.1 一览表

![img](https://img-blog.csdnimg.cn/img_convert/4689c7c11c2afc2f4582ceb0f07c69ec.png)

#### 12.11.2 测试题-下面的测试输出什么 ThrowException.java 2min

![img](https://img-blog.csdnimg.cn/img_convert/909fae3cc371f20b446655d7caf08669.png)

throw new RuntimeException 扔出异常给主方法的catch 输出“制造异常;

### 12.12 本章作业

![img](https://img-blog.csdnimg.cn/img_convert/689555ba431b59497145808c2cc59e85.png)

![img](https://img-blog.csdnimg.cn/img_convert/c6fe7190ea43db6a05342c4d45b5381c.png)

参数配置

```java
package com.hspedu.homework;

public class Homework01 {
    public static void main(String[] args) {
        /*
        编写应用程序EcmDef.java，接收命令行的两个参数(整数)，计算两数相除。
计算两个数相除，要求使用方法 cal(int n1, int n2)
对数据格式不正确(NumberFormatException)、缺少命令行参数(ArrayIndexOutOfBoundsException)、除0 进行异常处理(ArithmeticException)。
         */

        try {

            //先验证输入的参数的个数是否正确 两个参数
            if(args.length != 2) {
                throw new ArrayIndexOutOfBoundsException("参数个数不对");
            }

            //先把接收到的参数，转成整数
            int n1 = Integer.parseInt(args[0]);
            int n2 = Integer.parseInt(args[1]);

            double res = cal(n1, n2);//该方法可能抛出ArithmeticException
            System.out.println("计算结果是=" + res);

        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println(e.getMessage());
        } catch (NumberFormatException e) {
            System.out.println("参数格式不正确，需要输出整数");
        } catch (ArithmeticException e) {
            System.out.println("出现了除0的异常");
        }


    }
    //编写cal方法，就是两个数的商
    public static double cal(int n1, int n2) {
        return n1 / n2;
    }
}

```





![img](https://img-blog.csdnimg.cn/img_convert/cb7c6a7e5ec4024dd2df54fc081017d0.png)

上面是字符串，下面要int错误





![img](https://img-blog.csdnimg.cn/img_convert/c692958a2d8270d7cb7ee6adcec543d1.png)





![img](https://img-blog.csdnimg.cn/img_convert/c70c12f8185ccfdf723ab9018c021518.png)





## 第 13 章常用类

### 13.1 包装类

#### 13.1.1 包装类的分类 WrapperType.java

1. 针对八种基本数据类型相应的引用类型—包装类

2. 有了类的特点，就可以调用类中的方法。

3. 如图:

   ![img](https://img-blog.csdnimg.cn/img_convert/d9481b6d313a8c99246db755851b689f.png)

   ![img](https://img-blog.csdnimg.cn/img_convert/869513aeedffc38cd3128336f9250219.png)

   

   ![img](https://img-blog.csdnimg.cn/img_convert/324e2eb9e8299896d5c5f3dd5b67f2fa.png)

   



![img](https://img-blog.csdnimg.cn/img_convert/ad492735df9e013ccaec31173098f45d.png)





#### 13.1.2 包装类和基本数据的转换

![img](https://img-blog.csdnimg.cn/img_convert/b2b066c41112e0d08d1bc98b958e53d7.png)

#### 13.1.3 案例演示 Integer01.java



```java
package com.hspedu.wrapper;

public class Integer01 {
    public static void main(String[] args) {
        //演示int <--> Integer 的装箱和拆箱
        //jdk5前是手动装箱和拆箱
        //手动装箱 int->Integer
        int n1 = 100;
        Integer integer = new Integer(n1);
        //或
        Integer integer1 = Integer.valueOf(n1);

        //手动拆箱
        //Integer -> int
        int i = integer.intValue();

        //jdk5后，就可以自动装箱和自动拆箱
        int n2 = 200;
        //自动装箱 int->Integer
        Integer integer2 = n2; //底层使用的是 Integer.valueOf(n2)
        //自动拆箱 Integer->int
        int n3 = integer2; //底层仍然使用的是 intValue()方法
    }
}

```





#### 13.1.4 课堂测试题 WrapperExercise01.java 2min

![img](https://img-blog.csdnimg.cn/img_convert/98f88ffa7a859374a3408442d88ffc35.png)

double精度更高，输出1.0



#### 13.1.5 包装类型和String 类型的相互转换 WrapperVSString.java

![img](https://img-blog.csdnimg.cn/img_convert/46c4f582971d8ca2ef93ba9e90b4c1db.png)

```java
package com.hspedu.wrapper;

public class WrapperVSString {
    public static void main(String[] args) {
        //包装类(Integer)->String
        Integer i = 100;//自动装箱
        //方式1
        String str1 = i + "";
        //方式2
        String str2 = i.toString();
        //方式3
        String str3 = String.valueOf(i);

        //String -> 包装类(Integer)
        String str4 = "12345";
        Integer i2 = Integer.parseInt(str4);//使用到自动装箱
        Integer i3 = new Integer(str4);//构造器

        System.out.println("ok~~");

    }
}

```





#### 13.1.6 Integer 类和Character 类的常用方法

![img](https://img-blog.csdnimg.cn/img_convert/1e86098f10c992bbc92d253a38fb8b55.png)



#### 13.1.7 Integer 类面试题

![img](https://img-blog.csdnimg.cn/img_convert/d3188c780db7dc64851b7317748c7907.png)



结果

![img](https://img-blog.csdnimg.cn/img_convert/ae291e3eb9e9818b1a8886ce3e0dd185.png)



![img](https://img-blog.csdnimg.cn/img_convert/3f97f1cf6d88e00b4fe4187b1a6bc35b.png)



结果

![img](https://img-blog.csdnimg.cn/img_convert/c88911bd308cc9055a881f7eaa5f07cb.png)



### 13.2 String 类

#### 13.2.1 String 类的理解和创建对象

![img](https://img-blog.csdnimg.cn/img_convert/74984f0875f390379ca0306fbd1d23f6.png)

![img](https://img-blog.csdnimg.cn/img_convert/dc4d61e2535a87851a20cc50a2346e53.png)

```java
package com.hspedu.string_;

public class String01 {
    public static void main(String[] args) {
        //1.String 对象用于保存字符串，也就是一组字符序列
        //2. "jack" 字符串常量, 双引号括起的字符序列
        //3. 字符串的字符使用Unicode字符编码，一个字符(不区分字母还是汉字)占两个字节
        //4. String 类有很多构造器，构造器的重载
        //   常用的有 String  s1 = new String(); //
        //String  s2 = new String(String original);
        //String  s3 = new String(char[] a);
        //String  s4 =  new String(char[] a,int startIndex,int count)
        //String s5 = new String(byte[] b)
        //5. String 类实现了接口 Serializable【String 可以串行化:可以在网络传输】
        //                 接口 Comparable [String 对象可以比较大小]
        //6. String 是final 类，不能被其他的类继承
        //7. String 有属性 private final char value[]; 用于存放字符串内容
        //8. 一定要注意：value 是一个final类型， 不可以修改(需要功力)：即value不能指向
        //   新的地址（地址不可改变），但是单个字符内容是可以变化

        String name = "jack";
        name = "tom";
        final char[] value = {'a','b','c'};
        char[] v2 = {'t','o','m'};
        value[0] = 'H';
        //value = v2; 不可以修改 value地址 去掉final后可以

    }
}

```



#### 13.2.2 创建String 对象的两种方式

![img](https://img-blog.csdnimg.cn/img_convert/fa03ad533839c5fb5ca531f27f48a322.png)

#### 13.2.3 两种创建String 对象的区别

![img](https://img-blog.csdnimg.cn/img_convert/5c0583ab0e0aae4672b4caedb5dbc232.png)



![img](https://img-blog.csdnimg.cn/img_convert/7eb7c6bd27f0d5f5b130413441445fa8.png)



#### 13.2.4 课堂测试题 StringExercise01.java

![img](https://img-blog.csdnimg.cn/img_convert/5e7414c9a5a9190e8f944322465368d2.png)



![img](https://img-blog.csdnimg.cn/img_convert/3f60944155ac93e5de5b5ac35391eac4.png)





![img](https://img-blog.csdnimg.cn/img_convert/b933e003161cb7015b147421179e6f22.png)



![img](https://img-blog.csdnimg.cn/img_convert/f5a0a2e6c69d7e6c1d80a5beef171ad6.png)

![img](https://img-blog.csdnimg.cn/img_convert/3a9db26ac19163e7dd36d6955e9b3965.png)

b并没有指向常量池，只是b中的value指向常量池，b与a的地址并不相同





![img](https://img-blog.csdnimg.cn/img_convert/5bf5e29fc91c95d051803806e5145e81.png)



![img](https://img-blog.csdnimg.cn/img_convert/ccc063b48efee3ba40f8f8d6ea204f04.png)







### 13.3 字符串的特性

#### 13.3.1 说明 StringExercise06.java

![img](https://img-blog.csdnimg.cn/img_convert/c23597ca3f740f7ca3a2990c78e9ea1f.png)



#### 13.3.2 面试题

![img](https://img-blog.csdnimg.cn/img_convert/46fc872881fadd337250c8daf636f2f7.png)



![img](https://img-blog.csdnimg.cn/img_convert/15fe60f498f9898b7b39f74b93621676.png)

![img](https://img-blog.csdnimg.cn/img_convert/ae4c8c2c666bd91f107ea46abe0052a0.png)



```java
package com.hspedu.string_;

public class StringExercise08 {
    public static void main(String[] args) {
        String a = "hello"; //创建 a对象
        String b = "abc";//创建 b对象
        //老韩解读
        //1. 先 创建一个 StringBuilder sb = StringBuilder()
        //2. 执行  sb.append("hello");追加
        //3. sb.append("abc");
        //4. String c= sb.toString()  相当于String c=new String("helloabc")创建一个堆
        //最后其实是 c 指向堆中的对象(String) value[] -> 池中 "helloabc"
        String c = a + b;
        String d = "helloabc";
        System.out.println(c == d);//真还是假? 是false
        String e = "hello" + "abc";//直接看池， e指向常量池
        System.out.println(d == e);//真还是假? 是true
    }
}

```





![img](https://img-blog.csdnimg.cn/img_convert/195ac8b4cf40a343ae7b798c285b235e.png)





![img](https://img-blog.csdnimg.cn/img_convert/33d6eeb81de1a7f7c4a849ea637db37c.png)

![img](https://img-blog.csdnimg.cn/img_convert/3c0f4208390fad883ee60f744d90b6a4.png)



### 13.4 String 类的常见方法

#### 13.4.1 说明

![img](https://img-blog.csdnimg.cn/img_convert/25856ed91cc22a3ad00acf67b1eebe30.png)

String拼接效率低



#### 13.4.2 String 类的常见方法一览

![img](https://img-blog.csdnimg.cn/img_convert/901da897d988db4e42ef48fbe961438b.png)

```java
package com.hspedu.string_;
public class StringMethod01 {
    public static void main(String[] args) {
        //1. equals 前面已经讲过了. 比较内容是否相同，区分大小写
        String str1 = "hello";
        String str2 = "Hello";
        System.out.println(str1.equals(str2));//

        // 2.equalsIgnoreCase 忽略大小写的判断内容是否相等
        String username = "johN";
        if ("john".equalsIgnoreCase(username)) {
            System.out.println("Success!");
        } else {
            System.out.println("Failure!");
        }
        // 3.length 获取字符的个数，字符串的长度
        System.out.println("韩顺平".length());
        // 4.indexOf 获取字符在字符串对象中第一次出现的索引，索引从0开始，如果找不到，返回-1
        String s1 = "wer@terwe@g";
        int index = s1.indexOf('@');
        System.out.println(index);// 3
        System.out.println("weIndex=" + s1.indexOf("we"));//0
        // 5.lastIndexOf 获取字符在字符串中最后一次出现的索引，索引从0开始，如果找不到，返回-1
        s1 = "wer@terwe@g@";
        index = s1.lastIndexOf('@');
        System.out.println(index);//11
        System.out.println("ter的位置=" + s1.lastIndexOf("ter"));//4
        // 6.substring 截取指定范围的子串
        String name = "hello,张三";
        //下面name.substring(6) 从索引6开始截取后面所有的内容 结果为张三
        System.out.println(name.substring(6));//截取后面的字符
        //name.substring(0,5)表示从索引0开始截取，截取到索引 5-1=4位置 hello
        System.out.println(name.substring(2,5));//llo

    }
}

```

![img](https://img-blog.csdnimg.cn/img_convert/bfe37e8853530b8f474481c222858719.png)



```java
package com.hspedu.string_;
public class StringMethod02 {
    public static void main(String[] args) {
        // 1.toUpperCase转换成大写
        String s = "heLLo";
        System.out.println(s.toUpperCase());//HELLO
        // 2.toLowerCase
        System.out.println(s.toLowerCase());//hello
        // 3.concat拼接字符串
        String s1 = "宝玉";
        s1 = s1.concat("林黛玉").concat("薛宝钗").concat("together");
        System.out.println(s1);//宝玉林黛玉薛宝钗together
        // 4.replace 替换字符串中的字符
        s1 = "宝玉 and 林黛玉 林黛玉 林黛玉";
        //在s1中，将 所有的 林黛玉 替换成薛宝钗
        s2=s1.replace("宝玉"，"jack");
        // 老韩解读: s1.replace() 方法执行后，返回的结果才是替换过的.即s2,若左边是s1,则s1改变
        // 注意对 s1没有任何影响
        String s11 = s1.replace("宝玉", "jack");
        System.out.println(s1);//宝玉 and 林黛玉 林黛玉 林黛玉
        System.out.println(s11);//jack and 林黛玉 林黛玉 林黛玉
        // 5.split 分割字符串, 对于某些分割字符，我们需要 转义比如 | \\等
        String poem = "锄禾日当午,汗滴禾下土,谁知盘中餐,粒粒皆辛苦";
        //老韩解读：
        // 1. 以 , 为标准对 poem 进行分割 , 返回一个数组
        // 2. 在对字符串进行分割时，如果有特殊字符，需要加入 转义符 \
        String[] split = poem.split(",");
        poem = "E:\\aaa\\bbb";
        split = poem.split("\\\\");
        System.out.println("==分割后内容===");
        for (int i = 0; i < split.length; i++) {
            System.out.println(split[i]);
        }
        // 6.toCharArray 转换成字符数组
        s = "happy";
        char[] chs = s.toCharArray();
        for (int i = 0; i < chs.length; i++) {
            System.out.println(chs[i]);
        }
        // 7.compareTo 比较两个字符串的大小，如果前者大，
        // 则返回正数，后者大，则返回负数，如果相等，返回0
        // 老韩解读
        // (1) 如果长度相同，并且每个字符也相同，就返回 0
        // (2) 如果长度相同或者不相同，但是在进行比较时，可以区分大小
        //     就返回 if (c1 != c2) {
        //                return c1 - c2;
        //            }
        // (3) 如果前面的部分都相同，就返回 str1.len - str2.len
        String a = "jcck";// len = 3
        String b = "jack";// len = 4
        System.out.println(a.compareTo(b)); // 返回值是 'c' - 'a' = 2的值
// 8.format 格式字符串
        /* 占位符有:
         * %s 字符串 %c 字符 %d 整型 %.2f 浮点型
         *
         */
        String name = "john";
        int age = 10;
        double score = 56.857;
        char gender = '男';
        //将所有的信息都拼接在一个字符串.
        String info =
                "我的姓名是" + name + "年龄是" + age + ",成绩是" + score + "性别是" + gender + "。希望大家喜欢我！";

        System.out.println(info);


        //老韩解读
        //1. %s , %d , %.2f %c 称为占位符
        //2. 这些占位符由后面变量来替换
        //3. %s 表示后面由 字符串来替换
        //4. %d 是整数来替换
        //5. %.2f 表示使用小数来替换，替换后，只会保留小数点两位, 并且进行四舍五入的处理
        //6. %c 使用char 类型来替换
        String formatStr = "我的姓名是%s 年龄是%d，成绩是%.2f 性别是%c.希望大家喜欢我！";

        String info2 = String.format(formatStr, name, age, score, gender);

        System.out.println("info2=" + info2);
    }
}

```





### 13.5 StringBuffer 类

#### 13.5.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/84187818338c15fb3a23a09050279c63.png)



```java
package com.hspedu.stringbuffer_;

public class StringBuffer01 {
    public static void main(String[] args) {
        //老韩解读
        //1. StringBuffer 的直接父类 是 AbstractStringBuilder
        //2. StringBuffer 实现了 Serializable(接口), 即StringBuffer的对象可以串行化
        //3. 在父类中  AbstractStringBuilder 有属性 char[] value,不是final
        //   该 value 数组存放 字符串内容，引出存放在堆中的
        //4. StringBuffer 是一个 final类，不能被继承
        //5. 因为StringBuffer 字符内容是存在 char[] value, 所有在变化(增加/删除)
        //   不用每次都更换地址(即不是每次创建新对象)， 所以效率高于 String

        StringBuffer stringBuffer = new StringBuffer("hello");
    }
}

```



#### 13.5.2 Sring VS StringBuffer

![img](https://img-blog.csdnimg.cn/img_convert/a531c0ce9d3e472b46c18faec5c5fe1a.png)

![img](https://img-blog.csdnimg.cn/img_convert/c0b7cf946793f499cf95bd90e30b6479.png)

不会每次都更新，再空间不够时扩展，即value重新指向新地址



#### 13.5.3 StringBUffer的构造器

![img](https://img-blog.csdnimg.cn/img_convert/a3fdf157edcee30305025a4a50c2aba9.png)



#### 13.5.4 String 和 StringBuffer 相互转换

![img](https://img-blog.csdnimg.cn/img_convert/96f78ba153d8ebdf58395722c8bca3fb.png)

```java
package com.hspedu.stringbuffer_;
public class StringAndStringBuffer {
    public static void main(String[] args) {

        //看 String——>StringBuffer
        String str = "hello tom";
        //方式1 使用构造器
        //注意： 返回的才是StringBuffer对象，对str 本身没有影响
        StringBuffer stringBuffer = new StringBuffer(str);
        //方式2 使用的是append方法
        StringBuffer stringBuffer1 = new StringBuffer();
        stringBuffer1 = stringBuffer1.append(str);

        //看看 StringBuffer ->String
        StringBuffer stringBuffer3 = new StringBuffer("韩顺平教育");
        //方式1 使用StringBuffer提供的 toString方法
        String s = stringBuffer3.toString();
        //方式2: 使用构造器来搞定
        String s1 = new String(stringBuffer3);

    }
}

```



#### 13.5.5 StringBuffer 类常见方法

![img](https://img-blog.csdnimg.cn/img_convert/a4a24694ae62a848f800be28e6866011.png)



```java
package com.hspedu.stringbuffer_;
public class StringBufferMethod {
    public static void main(String[] args) {

        StringBuffer s = new StringBuffer("hello");
        //增
        s.append(',');// "hello,"
        s.append("张三丰");//"hello,张三丰"
        s.append("赵敏").append(100).append(true).append(10.5);//"hello,张三丰赵敏100true10.5"
        System.out.println(s);//"hello,张三丰赵敏100true10.5"


        //删
        /*
         * 删除索引为>=start && <end 处的字符
         * 解读: 删除 11~14的字符 [11, 14)
         */
        s.delete(11, 14);
        System.out.println(s);//"hello,张三丰赵敏true10.5"
        //改
        //老韩解读，使用 周芷若 替换 索引9-11的字符 [9,11)
        s.replace(9, 11, "周芷若");
        System.out.println(s);//"hello,张三丰周芷若true10.5"
        //查找指定的子串在字符串第一次出现的索引，如果找不到返回-1
        int indexOf = s.indexOf("张三丰");
        System.out.println(indexOf);//6
        //插
        //老韩解读，在索引为9的位置插入 "赵敏",原来索引为9的内容自动后移
        s.insert(9, "赵敏");
        System.out.println(s);//"hello,张三丰赵敏周芷若true10.5"
        //长度
        System.out.println(s.length());//22
        System.out.println(s);

    }
}

```



#### 13.5.6 StringBuffer 类课堂测试题

![img](https://img-blog.csdnimg.cn/img_convert/70c67df9e373c499846f9a427df2f387.png)



![img](https://img-blog.csdnimg.cn/img_convert/755f0867b2c9aba11c8e269df5d40416.png)

super(null.length()+16)出现NullpointException



![img](https://img-blog.csdnimg.cn/img_convert/bc3976fe00a36c1a15ab231ab05e70a2.png)

```java
package com.hspedu.stringbuffer_;

import java.util.Scanner;
public class StringBufferExercise02 {
    public static void main(String[] args) {
        /*
        输入商品名称和商品价格，要求打印效果示例, 使用前面学习的方法完成：
        商品名 商品价格
        手机  123,564.59  //比如 价格 3,456,789.88

        要求：价格的小数点前面每三位用逗号隔开, 在输出。

        思路分析
        1. 定义一个Scanner 对象，接收用户输入的 价格(String)
        2. 希望使用到 StringBuffer的 insert ，需要将 String 转成 StringBuffer
        3. 然后使用相关方法进行字符串的处理
        代码实现

         */

        //new Scanner(System.in)
        String price = "8123564.59";
        StringBuffer sb = new StringBuffer(price);
        //先完成一个最简单的实现123,564.59
        //找到小数点的索引，然后在该位置的前3位，插入,即可
//        int i = sb.lastIndexOf(".");
//        sb = sb.insert(i - 3, ",");

        //上面的两步需要做一个循环处理,才是正确的
        for (int i = sb.lastIndexOf(".") - 3; i > 0; i -= 3) {
            sb = sb.insert(i, ",");
        }
        System.out.println(sb);//8,123,564.59


    }
}

```



### 13.6 StringBuilder 类

#### 13.6.1 基本介绍

![img](https://img-blog.csdnimg.cn/img_convert/296ba0ebcf4b4a799756e885e8c7dbd8.png)





#### 13.6.2 StringBuilder 常用方法

![img](https://img-blog.csdnimg.cn/img_convert/3b50a725063cfe88444d05ccd39c3faf.png)

```java
package com.hspedu.stringbuilder_;
public class StringBuilder01 {
    public static void main(String[] args) {
        //老韩解读
        //1. StringBuilder 继承 AbstractStringBuilder 类
        //2. 实现了 Serializable ,说明StringBuilder对象是可以串行化(对象可以网络传输,可以保存到文件)
        //3. StringBuilder 是final类, 不能被继承
        //4. StringBuilder 对象字符序列仍然是存放在其父类 AbstractStringBuilder的 char[] value;
        //   因此，字符序列是堆中
        //5. StringBuilder 的方法，没有做互斥的处理,即没有synchronized 关键字,因此在单线程的情况下使用
        //   StringBuilder
        StringBuilder stringBuilder = new StringBuilder();
    }
}

```



#### 13.6.3 String、StringBuffer 和 StringBuilder 的比较

![img](https://img-blog.csdnimg.cn/img_convert/1b3ee115f5938aded2298ac4e3dfafc2.png)

![img](https://img-blog.csdnimg.cn/img_convert/1700cabcce88a3201e5b53e23e7105a6.png)



```java
package com.hspedu.stringbuilder_;
public class StringVsStringBufferVsStringBuilder {
    public static void main(String[] args) {

        long startTime = 0L;
        long endTime = 0L;
        StringBuffer buffer = new StringBuffer("");

        startTime = System.currentTimeMillis();
        for (int i = 0; i < 80000; i++) {//StringBuffer 拼接 20000次
            buffer.append(String.valueOf(i));
        }
        endTime = System.currentTimeMillis();
        System.out.println("StringBuffer的执行时间：" + (endTime - startTime));





        StringBuilder builder = new StringBuilder("");
        startTime = System.currentTimeMillis();
        for (int i = 0; i < 80000; i++) {//StringBuilder 拼接 20000次
            builder.append(String.valueOf(i));
        }
        endTime = System.currentTimeMillis();
        System.out.println("StringBuilder的执行时间：" + (endTime - startTime));


        String text = "";
        startTime = System.currentTimeMillis();
        for (int i = 0; i < 80000; i++) {//String 拼接 20000
            text = text + i;
        }
        endTime = System.currentTimeMillis();
        System.out.println("String的执行时间：" + (endTime - startTime));

    }
}

```



#### 13.6.5 String、StringBuffer 和 StringBuilder 的选择

![img](https://img-blog.csdnimg.cn/img_convert/59abf1ff5363b46170f06d6a84a23416.png)





### 13.7 Math类

#### 13.7.1 基本介绍

Math 类包含用于执行基本数学运算的方法，如初等指数、对数、平方根和三角函数。

#### 13.7.2 方法一览(均为静态方法)

![img](https://img-blog.csdnimg.cn/img_convert/2803f31d0b111fd730b4665a09a22f73.png)



#### 13.7.3 Math 类常见方法应用案例



```java
package com.hspedu.math_;
public class MathMethod {
    public static void main(String[] args) {
        //看看Math常用的方法(静态方法)
        //1.abs 绝对值
        int abs = Math.abs(-9);
        System.out.println(abs);//9
        //2.pow 求幂
        double pow = Math.pow(2, 4);//2的4次方
        System.out.println(pow);//16
        //3.ceil 向上取整,返回>=该参数的最小整数(转成double);
        double ceil = Math.ceil(3.9);
        System.out.println(ceil);//4.0
        //4.floor 向下取整，返回<=该参数的最大整数(转成double)
        double floor = Math.floor(4.001);
        System.out.println(floor);//4.0
        //5.round 四舍五入  Math.floor(该参数+0.5)
        long round = Math.round(5.51);
        System.out.println(round);//6
        //6.sqrt 求开方
        double sqrt = Math.sqrt(9.0);
        System.out.println(sqrt);//3.0

        //7.random 求随机数
        //  random 返回的是 0 <= x < 1 之间的一个随机小数
        // 思考：请写出获取 a-b之间的一个随机整数,a,b均为整数 ，比如 a = 2, b=7
        //  即返回一个数 x  2 <= x <= 7
        // 老韩解读 Math.random() * (b-a) 返回的就是 0  <= 数 <= b-a
        // (1) (int)(a) <= x <= (int)(a + Math.random() * (b-a +1) )
        // (2) 使用具体的数给小伙伴介绍 a = 2  b = 7
        //  (int)(a + Math.random() * (b-a +1) ) = (int)( 2 + Math.random()*6)
        //  Math.random()*6 返回的是 0 <= x < 6 小数
        //  2 + Math.random()*6 返回的就是 2<= x < 8 小数
        //  (int)(2 + Math.random()*6) = 2 <= x <= 7
        // (3) 公式就是  (int)(a + Math.random() * (b-a +1) )
        for(int i = 0; i < 100; i++) {
            System.out.println((int)(2 +  Math.random() * (7 - 2 + 1)));
        }

        //max , min 返回最大值和最小值
        int min = Math.min(1, 9);
        int max = Math.max(45, 90);
        System.out.println("min=" + min);
        System.out.println("max=" + max);

    }
}

```







### 13.8 Arrays 类

#### 13.8.1 Arrays 类常见方法应用案例

![img](https://img-blog.csdnimg.cn/img_convert/c5a9a24ec6d31775460e80ff7417dde9.png)

![img](https://img-blog.csdnimg.cn/img_convert/8cd1e6fac2441653981b6875a4ee5712.png)

```java
package com.hspedu.arrays_;

import java.util.Arrays;
import java.util.Comparator;

public class ArraysMethod01 {
    public static void main(String[] args) {

        Integer[] integers = {1, 20, 90};
        //遍历数组
//        for(int i = 0; i < integers.length; i++) {
//            System.out.println(integers[i]);
//        }
        //直接使用Arrays.toString方法，显示数组
//        System.out.println(Arrays.toString(integers));//

        //演示 sort方法的使用

        Integer arr[] = {1, -1, 7, 0, 89};
        //进行排序
        //老韩解读
        //1. 可以直接使用冒泡排序 , 也可以直接使用Arrays提供的sort方法排序
        //2. 因为数组是引用类型，所以通过sort排序后，会直接影响到 实参 arr
        //3. sort重载的，也可以通过传入一个接口 Comparator 实现定制排序
        //4. 调用 定制排序 时，传入两个参数 (1) 排序的数组 arr
        //   (2) 实现了Comparator接口的匿名内部类 , 要求实现  compare方法
        //5. 先演示效果，再解释
        //6. 这里体现了接口编程的方式 , 看看源码，就明白
        //   源码分析
        //(1) Arrays.sort(arr, new Comparator()
        //(2) 最终到 TimSort类的
       // private static <T> void binarySort(T[] a, int lo, int hi, int start, Comparator<? super T> c)()
                                        
        //(3) 执行到 binarySort方法的代码, 会根据动态绑定机制 c.compare()执行我们传入的
        //    匿名内部类的 compare ()
        //     while (left < right) {
        //                int mid = (left + right) >>> 1;
        //                if (c.compare(pivot, a[mid]) < 0)
        //                    right = mid;
        //                else
        //                    left = mid + 1;
        //            }
        //(4) new Comparator() {
        //            @Override
        //            public int compare(Object o1, Object o2) {
        //                Integer i1 = (Integer) o1;
        //                Integer i2 = (Integer) o2;
        //                return i2 - i1;
        //            }
        //        }
        //(5) public int compare(Object o1, Object o2) 返回的值>0 还是 <0
        //    会影响整个排序结果, 这就充分体现了 接口编程+动态绑定+匿名内部类的综合使用
        //    将来的底层框架和源码的使用方式，会非常常见
        //Arrays.sort(arr); // 默认排序方法
        //定制排序
        Arrays.sort(arr, new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                Integer i1 = (Integer) o1;
                Integer i2 = (Integer) o2;
                return i2 - i1;
            }
        });
        System.out.println("===排序后===");
        System.out.println(Arrays.toString(arr));//



    }
}

```



```java
package com.hspedu.arrays_;

import java.util.Arrays;
import java.util.List;

public class ArraysMethod02 {
    public static void main(String[] args) {
        Integer[] arr = {1, 2, 90, 123, 567};
        // binarySearch 通过二分搜索法进行查找，要求必须排好
        // 老韩解读
        //1. 使用 binarySearch 二叉查找
        //2. 要求该数组是有序的. 如果该数组是无序的，不能使用binarySearch
        //3. 如果数组中不存在该元素，就返回 return -(low + 1);  // key not found.
        //若查找568  low值为5(567后面为第五个)  输出-6
        int index = Arrays.binarySearch(arr, 567);
        System.out.println("index=" + index);

        //copyOf 数组元素的复制
        // 老韩解读
        //1. 从 arr 数组中，拷贝 arr.length个元素到 newArr数组中
        //2. 如果拷贝的长度 > arr.length 就在新数组的后面 增加 null
        //3. 如果拷贝长度 < 0 就抛出异常NegativeArraySizeException
        //4. 该方法的底层使用的是 System.arraycopy()
        Integer[] newArr = Arrays.copyOf(arr, arr.length);
        System.out.println("==拷贝执行完毕后==");
        System.out.println(Arrays.toString(newArr));

        //ill 数组元素的填充
        Integer[] num = new Integer[]{9,3,2};
        //老韩解读
        //1. 使用 99 去填充 num数组，可以理解成是替换原理的元素
        Arrays.fill(num, 99);
        System.out.println("==num数组填充后==");
        System.out.println(Arrays.toString(num));

        //equals 比较两个数组元素内容是否完全一致
        Integer[] arr2 = {1, 2, 90, 123};
        //老韩解读
        //1. 如果arr 和 arr2 数组的元素一样，则方法true;
        //2. 如果不是完全一样，就返回 false
        boolean equals = Arrays.equals(arr, arr2);
        System.out.println("equals=" + equals);

        //asList 将一组值，转换成list
        //老韩解读
        //1. asList方法，会将 (2,3,4,5,6,1)数据转成一个List集合
        //2. 返回的 asList 编译类型 List(接口)
        //3. asList 运行类型 java.util.Arrays#ArrayList, 是Arrays类的
        //   静态内部类 private static class ArrayList<E> extends AbstractList<E>
        //              implements RandomAccess, java.io.Serializable
        List asList = Arrays.asList(2,3,4,5,6,1);
        System.out.println("asList=" + asList);
        System.out.println("asList的运行类型" + asList.getClass());



    }
}

package com.hspedu.arrays_;

import java.util.Arrays;
import java.util.Comparator;

public class ArraysSortCustom {
    public static void main(String[] args) {

        int[] arr = {1, -1, 8, 0, 20};
        //bubble01(arr);

        bubble02(arr, new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                int i1 = (Integer) o1;
                int i2 = (Integer) o2;
                return i2 - i1;// return i2 - i1;
            }
        });

        System.out.println("==定制排序后的情况==");
        System.out.println(Arrays.toString(arr));

    }

    //使用冒泡完成排序
    public static void bubble01(int[] arr) {
        int temp = 0;
        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = 0; j < arr.length - 1 - i; j++) {
                //从小到大
                if (arr[j] > arr[j + 1]) {
                    temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    //结合冒泡 + 定制
    public static void bubble02(int[] arr, Comparator c) {
        int temp = 0;
        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = 0; j < arr.length - 1 - i; j++) {
                //数组排序由 c.compare(arr[j], arr[j + 1])返回的值决定
                if (c.compare(arr[j], arr[j + 1]) > 0) {
                    temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
}

```



#### 13.8.2 Arrays类课堂练习

![img](https://img-blog.csdnimg.cn/img_convert/84d28a8e5caac44da24040c847a6a501.png)

```java
package com.hspedu.arrays_;


import java.util.Arrays;
import java.util.Comparator;

public class ArrayExercise {
    public static void main(String[] args) {
        /*
        案例：自定义Book类，里面包含name和price，按price排序(从大到小)。
        要求使用两种方式排序 , 有一个 Book[] books = 4本书对象.

        使用前面学习过的传递 实现Comparator接口匿名内部类，也称为定制排序。
        [同学们完成这个即可 10min  ],
        可以按照 price (1)从大到小 (2)从小到大 (3) 按照书名长度从大到小

         */

        Book[] books = new Book[4];
        books[0] = new Book("红楼梦", 100);
        books[1] = new Book("金瓶梅新", 90);
        books[2] = new Book("青年文摘20年", 5);
        books[3] = new Book("java从入门到放弃~", 300);

        //(1)price从大到小

//        Arrays.sort(books, new Comparator() {
//            //这里是对Book数组排序，因此  o1 和 o2 就是Book对象
//            @Override
//            public int compare(Object o1, Object o2) {
//                Book book1 = (Book) o1;
//                Book book2 = (Book) o2;
//                double priceVal = book2.getPrice() - book1.getPrice();
//                //这里老师进行了一个转换
//                //如果发现返回结果和我们输出的不一致，就修改一下返回的 1 和 -1
//                if(priceVal > 0) {
//                    return  1;
//                } else  if(priceVal < 0) {
//                    return -1;
//                } else {
//                    return 0;
//                }
//            }
//        });

        //(2)price从小到大
//        Arrays.sort(books, new Comparator() {
//            //这里是对Book数组排序，因此  o1 和 o2 就是Book对象
//            @Override
//            public int compare(Object o1, Object o2) {
//                Book book1 = (Book) o1;
//                Book book2 = (Book) o2;
//                double priceVal = book2.getPrice() - book1.getPrice();
//                //这里老师进行了一个转换
//                //如果发现返回结果和我们输出的不一致，就修改一下返回的 1 和 -1
//                if(priceVal > 0) {
//                    return  -1;
//                } else  if(priceVal < 0) {
//                    return 1;
//                } else {
//                    return 0;
//                }
//            }
//        });

        //(3)按照书名长度从大到小

        Arrays.sort(books, new Comparator() {
            //这里是对Book数组排序，因此  o1 和 o2 就是Book对象
            @Override
            public int compare(Object o1, Object o2) {
                Book book1 = (Book) o1;
                Book book2 = (Book) o2;
                //要求按照书名的长度来进行排序
                return book2.getName().length() - book1.getName().length();
            }
        });


        System.out.println(Arrays.toString(books));

    }
}

class Book {
    private String name;
    private double price;

    public Book(String name, double price) {
        this.name = name;
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return "Book{" +
                "name='" + name + '\'' +
                ", price=" + price +
                '}';
    }
}

```





### 13.9 System类

#### 13.9.1 System 类常见方法和案例

![img](https://img-blog.csdnimg.cn/img_convert/6c85284e2a7823ede99693e2796d9766.png)

```java
package com.hspedu.system_;

import java.util.Arrays;
public class System_ {
    public static void main(String[] args) {

        //exit 退出当前程序

//        System.out.println("ok1");
//        //老韩解读
//        //1. exit(0) 表示程序退出
//        //2. 0 表示一个状态 , 正常的状态
//        System.exit(0);//
//        System.out.println("ok2");

        //arraycopy ：复制数组元素，比较适合底层调用，
        // 一般使用Arrays.copyOf完成复制数组

        int[] src={1,2,3};
        int[] dest = new int[3];// dest 当前是 {0,0,0}

        //老韩解读
        //1. 主要是搞清楚这五个参数的含义
        //2.
        //     源数组
        //     * @param      src      the source array.
        //     srcPos： 从源数组的哪个索引位置开始拷贝
        //     * @param      srcPos   starting position in the source array.
        //     dest : 目标数组，即把源数组的数据拷贝到哪个数组
        //     * @param      dest     the destination array.
        //     destPos: 把源数组的数据拷贝到 目标数组的哪个索引
        //     * @param      destPos  starting position in the destination data.
        //     length: 从源数组拷贝多少个数据到目标数组
        //     * @param      length   the number of array elements to be copied.
        System.arraycopy(src, 0, dest, 0, src.length);
        // int[] src={1,2,3};
        System.out.println("dest=" + Arrays.toString(dest));//[1, 2, 3]

        //currentTimeMillens:返回当前时间距离1970-1-1 的毫秒数
        // 老韩解读:
        System.out.println(System.currentTimeMillis());


    }
}

```





### 13.10 BigInteger 和 BigDecimal 类

#### 13.10.1 BigInteger 和BigDecimal 介绍

![img](https://img-blog.csdnimg.cn/img_convert/9b06f0ed2d6dfc16b6d57086ba4eb9e4.png)

#### 13.10.2 BigInteger 和BigDecimal 常见方法

![img](https://img-blog.csdnimg.cn/img_convert/56d248884f91795ccb084ad534024092.png)

```java
package com.hspedu.bignum;

import java.math.BigInteger;
public class BigInteger_ {
    public static void main(String[] args) {

        //当我们编程中，需要处理很大的整数，long 不够用
        //可以使用BigInteger的类来搞定
//        long l = 23788888899999999999999999999l;
//        System.out.println("l=" + l);

        BigInteger bigInteger = new BigInteger("23788888899999999999999999999");
        BigInteger bigInteger2 = new BigInteger("10099999999999999999999999999999999999999999999999999999999999999999999999999999999");
        System.out.println(bigInteger);
        //老韩解读
        //1. 在对 BigInteger 进行加减乘除的时候，需要使用对应的方法，不能直接进行 + - * /
        //2. 可以创建一个 要操作的 BigInteger 然后进行相应操作
        BigInteger add = bigInteger.add(bigInteger2);
        System.out.println(add);//
        BigInteger subtract = bigInteger.subtract(bigInteger2);
        System.out.println(subtract);//减
        BigInteger multiply = bigInteger.multiply(bigInteger2);
        System.out.println(multiply);//乘
        BigInteger divide = bigInteger.divide(bigInteger2);
        System.out.println(divide);//除


    }
}

```



```java
package com.hspedu.bignum;

import java.math.BigDecimal;
public class BigDecimal_ {
    public static void main(String[] args) {
        //当我们需要保存一个精度很高的数时，double 不够用
        //可以是 BigDecimal
//        double d = 1999.11111111111999999999999977788d;
//        System.out.println(d);
        BigDecimal bigDecimal = new BigDecimal("1999.11");
        BigDecimal bigDecimal2 = new BigDecimal("3");
        System.out.println(bigDecimal);

        //老韩解读
        //1. 如果对 BigDecimal进行运算，比如加减乘除，需要使用对应的方法
        //2. 创建一个需要操作的 BigDecimal 然后调用相应的方法即可
        System.out.println(bigDecimal.add(bigDecimal2));
        System.out.println(bigDecimal.subtract(bigDecimal2));
        System.out.println(bigDecimal.multiply(bigDecimal2));
        //System.out.println(bigDecimal.divide(bigDecimal2));//可能抛出异常ArithmeticException
        //在调用divide 方法时，指定精度即可. BigDecimal.ROUND_CEILING
        //如果有无限循环小数，就会保留 分子 的精度
        System.out.println(bigDecimal.divide(bigDecimal2, BigDecimal.ROUND_CEILING));
    }
}

```





### 13.11 日期类

#### 13.11.1 第一代日期类

![img](https://img-blog.csdnimg.cn/img_convert/923a911164e0480191770e0f164270fb.png)



说明一下diagram IDEA properties 的含义

为只有getSalary添加变成Salary类

```java
package com.hspedu.date_;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
public class Date01 {
    public static void main(String[] args) throws ParseException {

        //老韩解读
        //1. 获取当前系统时间
        //2. 这里的Date 类是在java.util包
        //3. 默认输出的日期格式是国外的方式, 因此通常需要对格式进行转换
        Date d1 = new Date(); //获取当前系统时间
        System.out.println("当前日期=" + d1);
        Date d2 = new Date(9234567); //通过指定毫秒数得到时间
        System.out.println("d2=" + d2); //获取某个时间对应的毫秒数
//

        //老韩解读
        //1. 创建 SimpleDateFormat对象，可以指定相应的格式
        //2. 这里的格式使用的字母是规定好，不能乱写

        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 hh:mm:ss E");
        String format = sdf.format(d1); // format:将日期转换成指定格式的字符串
        System.out.println("当前日期=" + format);

        //老韩解读
        //1. 可以把一个格式化的String 转成对应的 Date
        //2. 得到Date 仍然在输出时，还是按照国外的形式，如果希望指定格式输出，需要转换
        //3. 在把String -> Date ， 使用的 sdf 格式需要和你给的String的格式一样，否则会抛出转换异常
        String s = "1996年01月01日 10:20:30 星期一";
        Date parse = sdf.parse(s);
        System.out.println("parse=" + sdf.format(parse));

    }
}

```





#### 13.11.2 第二代日期类

![img](https://img-blog.csdnimg.cn/img_convert/88d69f58750cf8811ddc131891642f24.png)

```java
package com.hspedu.date_;

import java.util.Calendar;
public class Calendar_ {
    public static void main(String[] args) {
        //老韩解读
        //1. Calendar是一个抽象类， 并且构造器是private
        //2. 可以通过 getInstance() 来获取实例
        //3. 提供大量的方法和字段提供给程序员
        //4. Calendar没有提供对应的格式化的类，因此需要程序员自己组合来输出(灵活)
        //5. 如果我们需要按照 24小时进制来获取时间， Calendar.HOUR ==改成=> Calendar.HOUR_OF_DAY
        Calendar c = Calendar.getInstance(); //创建日历类对象//比较简单，自由
        System.out.println("c=" + c);
        //2.获取日历对象的某个日历字段
        System.out.println("年：" + c.get(Calendar.YEAR));
        // 这里为什么要 + 1, 因为Calendar 返回月时候，是按照 0 开始编号
        System.out.println("月：" + (c.get(Calendar.MONTH) + 1));
        System.out.println("日：" + c.get(Calendar.DAY_OF_MONTH));
        System.out.println("小时：" + c.get(Calendar.HOUR));
        System.out.println("分钟：" + c.get(Calendar.MINUTE));
        System.out.println("秒：" + c.get(Calendar.SECOND));
        //Calender 没有专门的格式化方法，所以需要程序员自己来组合显示
        System.out.println(c.get(Calendar.YEAR) + "-" + (c.get(Calendar.MONTH) + 1) + "-" + c.get(Calendar.DAY_OF_MONTH) +
                " " + c.get(Calendar.HOUR_OF_DAY) + ":" + c.get(Calendar.MINUTE) + ":" + c.get(Calendar.SECOND) );

    }
}

```



#### 13.11.3 第三代日期类

![img](https://img-blog.csdnimg.cn/img_convert/e69a616bc3e851d920e31ba262b3db6a.png)

![img](https://img-blog.csdnimg.cn/img_convert/09c494019c47a72a079f6bbfec26f529.png)

![img](https://img-blog.csdnimg.cn/img_convert/011b6419d4db486e04340cd51577e1aa.png)

第三代日期类更多方法

![img](https://img-blog.csdnimg.cn/img_convert/d99ef2a0db4d1ae8e873ee9321dde3dd.png)



```java
package com.hspedu.date_;

import java.time.Instant;
import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;
import java.time.format.DateTimeFormatter;
import java.util.ArrayList;
import java.util.Collection;
public class LocalDate_ {
    public static void main(String[] args) {
        //第三代日期
        //老韩解读
        //1. 使用now() 返回表示当前日期时间的 对象
        LocalDateTime ldt = LocalDateTime.now(); //LocalDate.now();//LocalTime.now()
        System.out.println(ldt);

        //2. 使用DateTimeFormatter 对象来进行格式化
        // 创建 DateTimeFormatter对象
        DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
        String format = dateTimeFormatter.format(ldt);
        System.out.println("格式化的日期=" + format);

        System.out.println("年=" + ldt.getYear());
        System.out.println("月=" + ldt.getMonth());
        System.out.println("月=" + ldt.getMonthValue());
        System.out.println("日=" + ldt.getDayOfMonth());
        System.out.println("时=" + ldt.getHour());
        System.out.println("分=" + ldt.getMinute());
        System.out.println("秒=" + ldt.getSecond());

        LocalDate now = LocalDate.now(); //可以获取年月日
        LocalTime now2 = LocalTime.now();//获取到时分秒


        //提供 plus 和 minus方法可以对当前时间进行加或者减
        //看看890天后，是什么时候 把 年月日-时分秒
        LocalDateTime localDateTime = ldt.plusDays(890);
        System.out.println("890天后=" + dateTimeFormatter.format(localDateTime));

        //看看在 3456分钟前是什么时候，把 年月日-时分秒输出
        LocalDateTime localDateTime2 = ldt.minusMinutes(3456);
        System.out.println("3456分钟前 日期=" + dateTimeFormatter.format(localDateTime2));

    }
}
结果：
2022-04-01T08:49:26.268
格式化的日期=2022-04-01 08:49:26
年=2022
月=APRIL
月=4
日=1
时=8
分=49
秒=26
890天后=2024-09-07 08:49:26
3456分钟前 日期=2022-03-29 23:13:26


```





#### 13.11.5 Instant 时间戳

![img](https://img-blog.csdnimg.cn/img_convert/2b4079dd676a1196e4fa27dc59b4114b.png)

```java
package com.hspedu.date_;

import java.time.Instant;
import java.util.Date;
public class Instant_ {
    public static void main(String[] args) {

        //1.通过 静态方法 now() 获取表示当前时间戳的对象
        Instant now = Instant.now();
        System.out.println(now);
        //2. 通过 from 可以把 Instant转成 Date
        Date date = Date.from(now);
        //3. 通过 date的toInstant() 可以把 date 转成Instant对象
        Instant instant = date.toInstant();

    }
}

```





#### 13.11.6 本章作业

![img](https://img-blog.csdnimg.cn/img_convert/a8f2939387d432a5378ce86aeb4b3313.png)

```java
package com.hspedu.homework;
public class Homework01 {
    public static void main(String[] args) {
        //测试
        String str = "abcdef";
        System.out.println("===交换前===");
        System.out.println(str);
        try {
            str = reverse(str, 1, 4);
        } catch (Exception e) {
            System.out.println(e.getMessage());
            return;
        }
        System.out.println("===交换后===");
        System.out.println(str);
    }

    /**
     * (1) 将字符串中指定部分进行反转。比如将"abcdef"反转为"aedcbf"
     * (2) 编写方法 public static String reverse(String  str, int start , int end) 搞定
     * 思路分析
     * (1) 先把方法定义确定
     * (2) 把 String 转成 char[] ，因为char[] 的元素是可以交换的
     * (3) 画出分析示意图
     * (4) 代码实现
     */
    public static String reverse(String str, int start, int end) {


        //对输入的参数做一个验证
        //老韩重要的编程技巧分享!!!
        //(1) 写出正确的情况
        //(2) 然后取反即可
        //(3) 这样写，你的思路就不乱
        if(!(str != null && start >= 0 && end > start && end < str.length())) {
            throw new RuntimeException("参数不正确");
        }

        char[] chars = str.toCharArray();
        char temp = ' '; //交换辅助变量
        for (int i = start, j = end; i < j; i++, j--) {
            temp = chars[i];
            chars[i] = chars[j];
            chars[j] = temp;
        }
        //使用chars 重新构建一个String 返回即可
        return new String(chars);

    }
}

```





![img](https://img-blog.csdnimg.cn/img_convert/ab41c3f50324a33d489f8bcebf5f1bab.png)

```java
package com.hspedu.homework;
public class Homework02 {
    public static void main(String[] args) {

        String name = "abc";
        String pwd = "123456";
        String email = "ti@i@sohu.com";

        try {
            userRegister(name,pwd,email);
            System.out.println("恭喜你，注册成功~");
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }

    }

    /**
     * 输入用户名、密码、邮箱，如果信息录入正确，则提示注册成功，否则生成异常对象
     * 要求：
     * (1) 用户名长度为2或3或4
     * (2) 密码的长度为6，要求全是数字  isDigital
     * (3) 邮箱中包含@和.   并且@在.的前面
     * <p>
     * 思路分析
     * (1) 先编写方法 userRegister(String name, String pwd, String email) {}
     * (2) 针对 输入的内容进行校核，如果发现有问题，就抛出异常，给出提示
     * (3) 单独的写一个方法，判断 密码是否全部是数字字符 boolean
     */
    public static void userRegister(String name, String pwd, String email) {

        //再加入一些校验
        if(!(name != null && pwd != null && email != null)) {
            throw  new RuntimeException("参数不能为null");
        }

        //过关
        //第一关
        int userLength = name.length();
        if (!(userLength >= 2 && userLength <= 4)) {
            throw new RuntimeException("用户名长度为2或3或4");
        }

        //第二关
        if (!(pwd.length() == 6 && isDigital(pwd))) {
            throw new RuntimeException("密码的长度为6，要求全是数字");
        }

        //第三关
        int i = email.indexOf('@');
        int j = email.indexOf('.');
        if (!(i > 0 && j > i)) {
            throw new RuntimeException("邮箱中包含@和.   并且@在.的前面");
        }


    }

    //单独的写一个方法，判断 密码是否全部是数字字符 boolean
    public static boolean isDigital(String str) {
        char[] chars = str.toCharArray();
        for (int i = 0; i < chars.length; i++) {
            if (chars[i] < '0' || chars[i] > '9') {//ASCII码对应大小
                return false;
            }
        }
        return true;
    }

}

```



![img](https://img-blog.csdnimg.cn/img_convert/ea6f7eff3690a64e20eb416f2237e476.png)

```java
package com.hspedu.homework;
public class Homework03 {
    public static void main(String[] args) {
        String name = "Willian Jefferson Clinton";
        printName(name);
    }

    /**
     * 编写方法: 完成输出格式要求的字符串
     * 编写java程序，输入形式为： Han shun Ping的人名，以Ping,Han .S的形式打印
     *       出来    。其中.S是中间单词的首字母
     * 思路分析
     * (1) 对输入的字符串进行 分割split(" ")
     * (2) 对得到的String[] 进行格式化String.format（）
     * (3) 对输入的字符串进行校验即可
     */
    public static void printName(String str) {

        if(str == null) {
            System.out.println("str 不能为空");
            return;
        }

        String[] names = str.split(" ");//split 分割字符串
        if(names.length != 3) {
            System.out.println("输入的字符串格式不对");
            return;
        }
        //名字排序，toUpperCase()为大写，charAt(0)只要第一个字母
        String format = String.format("%s,%s .%c", names[2], names[0], names[1].toUpperCase().charAt(0));
        System.out.println(format);
    }
}

```



![img](https://img-blog.csdnimg.cn/img_convert/b79451d5bc86ce20ea8e957806734751.png)

```java
package com.hspedu.homework;

public class Homework04 {
    public static void main(String[] args) {
            String str = "abcHsp U 1234";
            countStr(str);
    }

    /**
     * 输入字符串，判断里面有多少个大写字母，多少个小写字母，多少个数字
     * 思路分析
     * (1) 遍历字符串，如果 char 在 '0'~'9' 就是一个数字
     * (2) 如果 char 在 'a'~'z' 就是一个小写字母
     * (3) 如果 char 在 'A'~'Z' 就是一个大写字母
     * (4) 使用三个变量来记录 统计结果
     */
    public static void countStr(String str) {
        if (str == null) {
            System.out.println("输入不能为 null");
            return;
        }
        int strLen = str.length();
        int numCount = 0;
        int lowerCount = 0;
        int upperCount = 0;
        int otherCount = 0;
        for (int i = 0; i < strLen; i++) {
            if(str.charAt(i) >= '0' && str.charAt(i) <= '9') //字符串不能通过str[]这样取，要通过str.charAt(i)来取
                numCount++;
            } else if(str.charAt(i) >= 'a' && str.charAt(i) <= 'z') {
                lowerCount++;
            } else if(str.charAt(i) >= 'A' && str.charAt(i) <= 'Z') {
                upperCount++;
            } else {
                otherCount++;
            }
        }

        System.out.println("数字有 " + numCount);
        System.out.println("小写字母有 " + lowerCount);
        System.out.println("大写字母有 " + upperCount);
        System.out.println("其他字符有 " + otherCount);
    }
}

```





![img](https://img-blog.csdnimg.cn/img_convert/3b59b25306117e9533cfce3eb0dfb244.png)



a.equals(b),父类Animal中equals没有重写，还是比较对象地址