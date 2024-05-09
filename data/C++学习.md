# C++ 学习

面向过程编程（POP）

​	以过程为中心的编程范式

面向对象编程（OOP）

​	以对象为核心的编程范式

​	对象是类的实例

## C++ 应用领域

![image-20230828142615631](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230828142615631.png)

### 编译型语言和解释型语言

![image-20230828142842114](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230828142842114.png)

`写好的代码为.cpp文件——> 编译目标代码 .obj文件 ——> 链接库文件 ——>  .exe可执行代码 ——>运行`

## 配置C++ 开发环境

开发环境的安装，下载Visual Studio，选择Community 2022

### Visual Studio

***

[Visual Studio: IDE and Code Editor for Software Developers and Teams (microsoft.com)](https://visualstudio.microsoft.com/)

![image-20230828143958245](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230828143958245.png)

![image-20230828144135659](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230828144135659.png)

针对不同的开发需求，选择桌面C++开发

安装完成之后，进入登录界面，可以直接跳过；

选择主题，启动VS

### 创建新项目

点击创建新项目，选择`空项目`

![image-20230828144353607](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230828144353607.png)

`自定义项目名称`

![image-20230828144448780](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230828144448780.png)

创建完成，会打开`解决方案资源管理器`

在`源文件`中创建新文件，可以在`工具`中选择字体和颜色

**写一段简单的代码**

```c++
#include<iostream> //预处理命令 引入<iostream>头文件

int main() //主函数
{
	std::cout << "hello world" << std::endl; //函数体
}
```

点击![image-20230828144827190](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230828144827190.png)

会弹出调试台，按任意键推出

![image-20230828144914412](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230828144914412.png)

## 3 数据处理

### 3.1.1 变量名

*   名称只能使用字母字符、数字和下划线；

*   名称的第一个字符不能是数字

*   区分大小写

*   不能使用关键字

*   长度没有限制

*   以两个下划线打头或者下划线和大写字母打头的名称被保留给实现使用

### 3.1.2 整型

基本整型：char short int long (c++ long long )

### 3.1.3 整型short int long 和 long long

*   **一个字节byte 8位 bit**

*   char 字符 8位 `1个字节`

*   short 至少16位  `2个字节`

*   int至少与short一样长  `4个字节`

*   long至少32位，且至少与int一样长 `4个字节`

*   long long 至少64位，且至少与long一样长 `8个字节`

*   `sizeof()`求内存空间

### 3.1.4 无符号类型

无符号类型 增大变量能够存储的最大值。

如：short -32768\~32768

无符号：0\~65535

### 3.1.8 char类型：字符和小整数

**占一个字节**

存储字符 能够表示计算机系统中的所有基本符号——所有的`字母、数字、标点符号`

也可以将它用作比short更小的整型

**signed char 和 unsigned char**

char在默认情况下既不是`没有符号，也不是有符号`

```c++
char fodo;          // may be signed, may be unsigned
unsigned char bar;  // definitely unsigned
signed char snark;  // definitely signed
```

unsigned char类型表示范围为 0——255

signed char类型表示范围 -128——127

**C风格字符串**

`char cha1[] = "hello  world";`

**c++风格字符串**

包含一个头文件#include

`string str = "hello world";`

#### wchar\_t (宽字符类型)

程序需要处理的字符集可能无法使一个8位的字节表示

​	1.将char定义为一个16位的字节

​	2.char表示基本字符集，wchar\_t宽字符类型表示拓展字符集

cin和cout将输入和输出看做是char，不适用处理wchar\_t类型，wcin和wcout用于处理wchar\_t流

#### char16\_t和char32\_t

两者为无符号，长度为16和32

c++11使用前缀u表示char16\_t,使用前缀U表示char32\_t

```c++
char16_t ch1 = u'q'; // basic character in 16-bit form
char32_t ch2 = U'\U0000222B'; // universal character name in 32-bit form
```

### 3.2const限定符

常量的符号名称

使用const后常量被初始化，值被固定，编译器将不允许修改常量的值

const type name \= value;

### 3.3 浮点数 (实型)

表示小数部分的数字

浮点类型分为两种

​	1.单精度float `占用内存：4个字节`

​	2.双精度double `占用内存：8个字节`

浮点数的表达方式

1.小数点

2.E表示法(适合非常大和非常小的数)**科学计数法**

​	3.45E6：表示3.45与1000000相乘的结果；

​	E6表示是10的6次方

![image-20230830190450637](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230830190450637.png)

#### 3.3.2 浮点类型

1.float 2.double 3. long double

```c++
#include <iostream>
using namespace std;
int main()
{
	cout.setf(ios_base::fixed, ios_base::floatfield);
	float tub = 10.0 / 3.0;
	double mint = 10.0 / 3.0;
	const float million = 1.0e6;
	cout << "tub = " << tub;
	cout << ", a million tubs = " << million * tub;
	cout << ",\n and ten million tubs = ";
	cout << 10 * million * tub << endl;

	cout << "mint = " << mint << " and a million mints = ";
	cout << million * mint << endl;
	return 0;
	cin.get();
	

}
```

```c++
tub = 3.333333, a million tubs = 3333333.250000,
and ten million tubs = 33333332.000000
mint = 3.333333 and a million mints = 3333333.333333
```

**显示小数通常显示六位**

cout会删除结尾的0，调用cout.self()将覆盖这种行为

**浮点常量**

在默认情况下

8.24和2.4E8属于double类型

float类型使用f或F后缀

long double类型 使用l或者L后缀

```c++
1.234f        // a float constant
2.45E20F      // a float constant
2.345324E28   // a double constant
2.2L          // a long double constant
```

#### 3.3.4 浮点数的优缺点

1表示整数之间的值

2有缩放因子，表示范围大

3运算速度比整数运算慢，精度将降低

`C++对于float，只能保证6位有效位`

### 3.4.4 类型转换

类型根据需求选择不同类型

C++自动执行很多类型转换：

*   将算数类型的值赋给另一种算数类型的变量，c++会进行转换

*   表达式中包含不同的类型

*   参数传递给函数、

##### 1 初始化和赋值进行的转换

​	![image-20230830194910203](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230830194910203.png)

将0赋给bool变量，将被转换为false；

非零值将被转换为true；

##### 2 以{}方式初始化进行的转换

使用{}称为列表初始化，初始化常用语给复杂的数据类型提供列表，对类型转换的要求更严格，列表初始化不允许`缩窄` ，变量的类型可能无法表示赋给它的值

##### 3 表达式中的转换

自动转换：

​	c++将bool、char、unsigend char、singed char和short值转换为int

这些转换被称为“`整型提升`”

将不同类型进行算数运算时，int和float相加时，较小的类型将会转换为较大的类型

1.  操作数的类型是 long double 则转换为long double

2.  又一个操作数类型是double ，则转换为double

3.  又一个操作数是float，则转化为float

4.  如果一个操作数的类型是整型，执行整型提升

![image-20230831131857535](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230831131857535.png)

##### 4 整型级别的顺序

有符号整型级别：

从高到低  ： long long 、long、int、shot、和signed char

无符号整型级别排列顺序与有符号整型相同

类型char、signed char 和unsigned char的级别相同

类型bool的级别最低

##### 5 强制类型转换

```c++
(long) thorn   // returns a type long conversion of thorn
long (thorn)   // returns a type long conversion of thorn
```

第一种C语言 第二种c++

static\_cast<>用于将值的数据类型转换

```c++
static_cast<long> (thorn) // returns a type long conversion of thorn
```

```C++
#include <iostream>
using namespace std;
int main()
{
	int auks, bats, coots;
	auks = 19.99 + 11.99;

	bats = (int)19.99 + (int)11.99;
	coots = int(19.99) + int(11.99);
	cout << "auks = " << auks << ", bats + " << bats;
	cout << ",coots = " << coots << endl;

	char ch = 'Z';
	cout << "the code for " << ch << " is ";
	cout << int(ch) << endl;
	cout << "Yes the code is ";
	cout << static_cast<int>(ch) << endl;
	cin.get();
	return 0;	

}
```

![image-20230831133249179](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230831133249179.png)

19.99+11.99 \= 31.98 将其赋给int，被截断为31；

在进行加法运算之前使用强制类型转换，这两个值将被截断为19和11 相加为30；

### 3.4.5 C++中的auto声明

C++11新增一个工具，让编译器根据初始化值的类型推断变量的类型。

```c++
auto n = 100;      // n is int
auto x = 1.5;      // x is double
auto y = 1.3e12L;  // y is long double
```

### 3.5 总结

​	c++基本类型分两组：

​		一组由存储为整数的值组成

​		一组为存储为浮点格式的值组成

**整型**从小到大：

bool 、char、 signed char、 unsigned char、 short、 unsigned short、int、unsigned int、long、unsigned long、long long 、unsigned long long

**浮点**类型：

float、double、long double

通常float使用32位 double使用64位 long double使用80-120

## 4 复合类型

### 4.1 数组

**创建数组**

1.存储元素中的值的类型

2.数组名

3.数组中的元素数

```c++
typename arryName [arrySize]
```

c++中数组下标开始从0编号

#### 4.1.2 数组初始化规则

```c
int cards[4] = {3, 6, 8, 10}; // okay
int hand[4];                  // okay
hand[4] = {5, 6, 7, 9};       // not allowed
hand = cards;                 // not allowed
```

#### 4.1.3 c++11数组初始化方法

使用大括号初始化

舒适化数组，可省略（\=）

```c++
double earnings[4] {1.2e4, 1.6e4, 1.1e4, 1.7e4}; // okay with C++11
```

可不在大括号内包含任何东西，将所有元素设置为0

```c++
unsigned int counts[10] = {};   // all elements set to 0
float balances[100] {};         // all elements set to 0
```

### 4.2 字符串

C++处理字符串有两种

1.C语言风格字符串

2.基于String类库

存储连续字节可以将字符存储在**char数组**中，c风格字符串的重要性质：**以空字符结尾**

字符串常量：

```c++
char bird[11] = "Mr. Cheeps";    // the \0 is understood
char fish[] = "Bubbles";         // let the compiler count
```

字符串常量（使用双引号）不能域字符常量（使用单引号）互换

字符常量‘S’是字符串编码的简写表示，但是“S”表示两个字符S和\0组成的字符串；

#### 4.2.2 在数组中使用字符串

将字符串存储在数组中

1.将数组初始化为字符串常量

2.将键盘或文件输入读入到数组中

#### 4.2.3 字符串输入

```c++
#include <iostream>
int main()
{
    using namespace std;
    const int ArSize = 20;
    char name[ArSize];
    char dessert[ArSize];

    cout << "Enter your name:\n";
    cin >> name;
    cout << "Enter your favorite dessert:\n";
    cin >> dessert;
    cout << "I have some delicious " << dessert;
    cout << " for you, " << name << ".\n";
    return 0;
}
```

输出会产生bug ，还没有对输入甜点的提示做出反应，程序就会把它显示出来，立即显示最后一行

![image-20230831190155443](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230831190155443.png)

**cin使用`空白来确定字符串的结束位置`，cin在获取字符数组输入时只取得一个单词**

cin将该字符串放到数组中，并自动在结尾添加空字符

在输入Alistair作为第一个字符串，放入到name数组中，将Dreeb留在传输队列中，当cin在输入队列中搜索用户的甜点时，会发现Dreeb，因此将cin读取Dreeb，将其放入dessert数组中

#### 4.2.4 每次读取一行字符串输入

输入完整的字符串，读取并存储完整的字符串，采用另一种字符串读取方法。

采用`面向行`而不是面向单词的方法：

面向行的类成员函数：

​	1、`getline()`和`get()`，两个函数读取一行输入，直到到达换行符 ，`getline()`会**丢弃换行符**，`get()`会**保留换行符在输入序列**

    cin.getline(name,20);

`cin.getline()`该函数有两个参数

第一个**参数存储行的数组的名称**，第二个参数是**要读取的字符数**。

每次读取一行。通过**换行符**确定行尾，但不保存换行符。在存储字符串时，用**空字符**来替换换行符。![image-20230901132949928](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230901132949928.png)

​	2、面向行的输入：`get()`

```c++
cin.get(name, ArSize);
cin.get(dessert,AreSize);//产生问题
```

`get()`的成员函数，与`getline()`接受的参数相同，解释的参数的方式也相同，并且都读取到行尾，`get()``并不在读取并丢弃换行符`，而是将其留在**输入队列中**。

连续两次调用get()，第一次调用后，换行符将留在输入队列中，第二次调用时看到的第一个字符便是换行符。因此`get()`认为到达行尾。

**变体**：

`get()`变体，使用不带任何参数的`cin.get()`调用可读取下一个字符（即使是换行符），因此可以用它来处理`换行符`，为读取下一行输入做好准备。

```c++
cin.get(name, ArSize);      // read first line
cin.get();                  // read newline
cin.get(dessert, Arsize);   // read second line
```

​	另一种方式使用`get()`将两个类成员函数拼接起来

```c++
cin.get(name, ArSize).get(); // concatenate member functions
```

#### 4.2.5 混合输入字符串和数字

```c++
#include <iostream>
int main()
{
    using namespace std;
    cout << "What year was your house built?\n";
    int year;
    cin >> year;
    cout << "What is its street address?\n";
    char address[80];
    cin.getline(address, 80);
    cout << "Year built: " << year << endl;
    cout << "Address: " << address << endl;
    cout << "Done!\n";
    return 0;
}
```

```c++
What year was your house built?
1966
What is its street address?
Year built: 1966
Address:
Done!
```

输出：没有输入地址的机会，cin读取年份，将回车键生成的换行符留在了输入队列中。`cin.getline()`得到换行符，将认为是一个空行，将空行赋给address数组。

解决：在读取地址之前先读取并丢弃换行符

1.使用没有参数的get()和使用接受一个char参数get()

### 4.3 string 类

要使用string类，必须在程序中包含头文件string。

string类位于名称空间std中，因此必须提供一条using编译指令。

或使用std::string来引用

使用string对象的方式与使用字符数组相同

1.  使用c风格字符串初始化string对象

2.  使用cin来键盘输入存储到string对象中

3.  使用cout显示string对象

4.  使用数组表示法访问存储在string对象的字符

string对象和字符数组之间的主要区别：将string对象声明为简单变量

    string str1;              // create an empty string object
    string str2 = "panther";  // create an initialized string

类设计让程序能自动处理string的大小

#### 4.3.2 赋值、拼接、附加

​	使用string类，不能将数组赋值给另一个数组，但是可以将string对象赋值给另一个string对象

```c++
#include <iostream>
#include<string>
using namespace std;
int main()
{
    string str1, str2;
    string str3 = "我是你爸爸";
    cout << "确定一下字符串变量谁是爸爸" << endl;
    str1 = str3;
    cout << "str1 :" << str1 << ",str3 :" << str3 << endl;
    cout << "请输入一个名称：";
    cin >> str2;
    cout << "str2是什么： " << str2 << endl;
    str1 = str2;
    cout << "再次确定你的身份： " << endl;
    cout << "str1 : " << str1 << ",str2 :" << str2 << ",str3: " << str3 << endl;
    cin.get();
    cin.get();
    return 0;
}
```

![image-20230901161320307](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote@master/data/image-20230901161320307.png)

#### 4.3.3 String类的其他操作

使用函数strcat()将字符串附加到字符数组末尾

```c++
strcpy(charr1, charr2);  // copy charr2 to charr1
strcat(charr1, charr2);  // append contents of charr2 to char1
```

## 4 程序流程结构

顺序、选择、循环

### 1.选择结构

作用：执行满足条件的语句

if语句的三种形式

*   单行

*   多行

*   多条件

```c++
if (count > 600)
{
	cout << "恭喜！" << endl;
}
else
{
	cout << "未考上一本大学" << endl;
}
```

多条件的if语句：

```c++
if (count > 600)
{
	cout << "恭喜考上一本大学！" << endl;
}
else if(500<count<600)
{
	cout << "考上二本大学" << endl;
}
else if (400<count < 500)
{
	cout << "考上三本大学" << endl;
}
else
{
	cout << "为考上大学" << endl;
}
```

嵌套if语句

```c++
if (count > 600)
{	
	if (count > 700) {
		cout << "考上清华" << endl;
	}
	else
	{
		cout << "恭喜考上一本大学！" << endl;
	}
	
}
```

```c++
#include<iostream>
#include<string>
using namespace std;
int main() 
{		
	// 选择结构 单行if语句
	int Ascore = 0,Bscore = 0,Cscore=0;
	cout << "用户请输入A成绩：" << endl;
	cin >> Ascore;
	cout << "用户请输入B成绩：" << endl;
	cin >> Bscore;
	cout << "用户请输入C成绩：" << endl;
	cin >> Cscore;

	cout << "A的成绩是：" << Ascore << endl;
	cout << "B的成绩是：" << Bscore << endl;
	cout << "C的成绩是：" << Cscore << endl;
	// 判断谁的成绩更好
	if (Ascore > Bscore)
	{
		if (Ascore > Cscore)
		{
			cout << "A的成绩最好：" << Ascore << endl;
		}
		else
		{
			cout << "C的成绩最好：" << Cscore << endl;
		}
	}
	else
	{
		if (Bscore > Cscore)
		{
			cout << "B的成绩最好：" << Bscore << endl;
		}
		else
		{
			cout << "C的成绩最好：" << Cscore << endl;
		}
	}

	cin.get();
}
```

#### **2.三目运算符**

```c++
c = ( a > b ? a : b );
```

c++中返回的值是变量，可以继续赋值

#### 3.Switch 语句

```c++
switch(表达式)
{
case 结果1:执行语句;break;
case 结果2:执行语句;break;
case 结果3:执行语句;break;
case 结果4:执行语句;break;

default:执行语句;break;
}
```

```c++
#include<iostream>
#include<string>
using namespace std;
int main() 
{		

	cout << "请对电影评分：" << endl;
	int score = 0;
	cin >> score;
	cout << "您评价的分数是：" << score << endl;

	switch (score)
	{
	case 10:
		cout << "经典" << endl;
		break;
	case 9:
		cout << "经典" << endl;
		break;
	case 8:
		cout << "不错" << endl;
		break;
	case 7:
		cout << "不错" << endl;
		break;
	case 6:
		cout << "一般" << endl;
		break;
	case 5:
		cout << "一般" << endl;
		break;
	default:
		cout << "烂片" << endl;
		break;
	}

	cin.get();
}
```

if与switch的区别

switch缺点：判断只能是整型或者字符型，不能是一个区间

switch优点:    结构清晰，执行效率高

### 2.循环结构

#### while 循环

` while (循环条件){循环语句}`

猜测随机数字

```c++
#include <iostream>
#include <string>           // make string class available
#include <cstring>          // C-style string library
using namespace std;        
int main()
{
    //添加随机种子 防止随机数字都一样
    srand((unsigned int)time(NULL));
   //生成一个随机数
	int num = rand() % 100 + 1;
	//cout << num << endl;
	// 输入猜测的数字
	cout << "输入你要猜测的数字" << endl;
	int val = 0;
	while (1)
	{
		cin >> val;
		if (val > num)
		{
			cout << "输入的数字太大" << endl;
		}
		else if (val < num)
		{
			cout << "输入的数字太小" << endl;
		}
		else
		{
			cout << "恭喜猜测数字正确！！！" << "正确数字为:" << val << endl;
			//猜对 推出循环 break 推出当前循环
			break;
		}
		
	}
	

}
```

#### do...while 循环语句

`do{循环语句} while(循环条件)；`

```c++
	int num = 0;
	do
	{
		cout << num << endl;
		num++;
	} while (num < 10);
	system("pause");
```

案例：水仙花数

```c++
#include <iostream>
#include <string>           // make string class available
#include <cstring>          // C-style string library
#include<ctime>
using namespace std;        
int main()
{
	int num=100;

	do
	{	
		int a, b, c;
		a = num / 100;
		b = num / 10%10;
		c = num % 10;
		if (num == a * a * a + b * b * b + c * c * c)
		{
			cout << "该数为水仙花数：" << num << endl;
		}
		num++;
	} while (num < 1000);

}
```

#### for 循环

作用：满足循环条件，执行循环语句

语法：`for(起始表达式；条件表达式；末尾循环体){循环语句；}`

示例：

```c++
	for(int j = 0;j<10;j++)
	{ 
		for (int i = 0; i < 10; i++)
	{
		cout << "* ";
	}
		cout << endl;
}
```

乘法口诀表：

```c++
#include <iostream>
using namespace std;        
int main()
{

	for (int i = 1; i <=9; i++)
	{
		for (int j = 1; j <= i; j++)
		{
			cout << j << " x " << i << " = " << i * j <<" ";
		}
		cout << endl;
	}

	
	system("pause");
}
```

### 3. 跳转语句

1.break语句

​	跳出选择结构或者循环结构

break使用的时机：

*   出现在switch条件语句中，作用是终止case并跳出switch

*   循环。跳出当前的循环语句

*   嵌套循环，跳出最近的内层循环语句

```c++
#include<iostream>
#include<string>
using namespace std;
int main()
{
	cout << "选择副本难度：" << endl;
	cout << "副本难度1" << endl;
	cout << "副本难度2" << endl;
	cout << "副本难度3" << endl;

	int sle = 0;
	cin >> sle;

	switch (sle)
	{
	case 1:
		cout << "您选择的是难度1" << endl;
		break;
	case 2:
		cout << "您选择的是难度2" << endl;
		break;
	case 3:
		cout << "您选择的是难度3" << endl;
		break;
	default:
		cout << "输入错误！" << endl;
		break;
	}
	system("pause");
}
```

2.continue 语句

​	作用：在循环语句中，跳过本次循环中余下尚文执行的语句，继续执行下一次循环

`continue不会使整个循环终止`

```c++
#include<iostream>
#include<string>
using namespace std;
int main()
{
	//continue
	for (int i = 0; i <= 100; i++) {
		if (i % 2 == 0)
		{
			continue;
		}
		cout << i << endl;
	}
	system("pause");
}
```

3.goto语句

​	作用：可以无条件跳转语句

​	语法: `goto 标记;`

​	解释：如果标记的名称存在，执行到goto语句，会跳转到标记的位置

```c++
#include<iostream>
#include<string>
using namespace std;
int main()
{
	//goto
	cout << "1.xxxxx" << endl;
	cout << "2.xxxxx" << endl;

	goto FLAG;
	cout << "3.xxxxx" << endl;
	cout << "4.xxxxx" << endl;
	FLAG:
	cout << "5.xxxxx" << endl;
	
	system("pause");
}
```

## 5 数组

所谓数组就是一个集合，里面存放相同类型的数据元素

**特点1**：数组中的每个元素都是相同的数据类型

**特点2**：数组是由连续的内岑位置组成的

### 5.1 一维数组的定义

1.`数据类型  数组名[ 数组长度 ];`

2.`数据类型  数组名[ 数组长度 ]= { 值1, 值2,...};`

3.`数据类型  数组名[ ] = {值1, 值2, ....};`

```c++
#include<iostream>
#include<string>
using namespace std;
int main()
{
	
	/*int arr[5];
	arr[0] = 10;
	arr[1] = 10;
	arr[2] = 10;
	arr[3] = 10;
	arr[4] = 10;
	
	cout << arr[0] << endl;*/
	//初始化没有全部填写，会用0来填补
	/*int arr2[10] = { 1, 2, 3, 4, 5, 6 };
	for (int i = 0; i < 10; i++) {
		cout << arr2[i] << endl;
	}*/

	int arr3[] = { 1, 2, 3, 4, 5, 6, 7 };
	for (int i = 0; i < 7; i++) {
		cout << arr3[i] << endl;
	}

	system("pause");
}
```

### 5.2 一维数组数组名

一维数组名称的用途

​	1.统计整个数组在内存中的长度

​		`sizeof(arr);` 	`sizeof(arr[0]);`

​	2.获取数组在内存中的首地址

```c++
int arr3[] = { 1, 2, 3, 4, 5, 6, 7 };

cout << sizeof(arr3) << endl;
cout << sizeof(arr3[0]) << endl;
cout << sizeof(arr3) / sizeof(arr3[0]) << endl;
cout << "数组元素地址:" <<(int)arr3<< endl;
//首地址和第一个元素的地址一致
cout << "第一个元素的地址：" << (int)&arr3[0] << endl;
cout << "第二个元素的地址：" << (int)&arr3[1] << endl;
//数组名是一个常量,不可以进行赋值操作
```

**案例1：**

找出最大值：

```c++
#include<iostream>

using namespace std;

int main()
{
	int arr[5] = { 300,350,200,400,250 };
	int max = 0;
	int index = 0;
	max = arr[0];
	for (int i = 0; i < 5; i++)
	{		
		if (arr[i] > max) 
		{	
			max = arr[i];
			index = i;
		}	
	}
	cout << "数值最大的是：" <<max<<"下标为："<<index << endl;
	system("pause");
}
```

**案例2：**

数组元素逆位

```c++
#include<iostream>

using namespace std;

int main()
{
	int arr[] = { 1,2,3,4,5 };
	int start = 0;//其实元素下标
	int end = sizeof(arr) / sizeof(arr[0]) - 1;
	int temp;

	cout << "原始数组为：" << endl;
	for (int i = 0; i < 5; i++)
	{
		cout << arr[i] << " ";
	}

	while (start < end) 
	{	
		//实现元素互换
		temp = arr[start];
		arr[start] = arr[end];
		arr[end] = temp;
		//下标更新
		start++;
		end--;
	}
		
	cout << "转换后的数组" << endl;
	for (int i = 0; i < 5; i++)
	{
		cout << arr[i] << " ";
	}
	system("pause");
}
```

**冒泡排序**

作用：最常见的排序算法，对数组内的元素进行排序

​	1.比较相邻元素，如果第一个比第二个大，就交换

​	2.对每一对相邻的元素做同样的工作，执行完毕后，找到一个最大值

​	3.重复以上步骤，每次比较次数－1，直到不需要比较

```c++
#include<iostream>

using namespace std;

int main()
{
	int arr[] = { 24, 34,23,12,45,62,13,53,25,1, 0,2,5,20};
	int length = sizeof(arr) / sizeof(arr[0]);
	int temp = 0;
	//打印原始数组
	cout << "原始数组：" << endl;
	for (int i = 0; i < length; i++)
	{
		cout << arr[i] << " ";
	}
	//共需要排序的轮数 9-8轮 
	for (int i = 0; i < length - 1; i++)
	{	//对比次数 每轮对比次 数= 元素个数-排序轮数-1
		for (int j = 0; j < length - 1-i; j++)
		{
			if (arr[j ] > arr[j+1])
			{
				temp = arr[j + 1];
				arr[j + 1] = arr[j];
				arr[j] = temp;
			}
		}
	}
	cout << endl;

	//打印转换后的数组
	cout << "转换后的数组" << endl;
	for (int i = 0; i < length; i++)
	{
		cout << arr[i] << " ";
	}
	cout << endl;
	system("pause");
}
```

0: 4 2 8 0 5    对比次数：4

1:  2 4 0  5 8  对比次数：3

2: 2 0 4 5  8  对比次数：2

3: 0 2 4 5 8  对比次数： 1

元素个数：5

对比轮数：5-1\=4

每轮对比次数：元素个数 - 对比轮数 - 1

### 5.3 二维数组

一维数组，多加一个维度。

二维数组定义的四种方式：

1.`数据类型	数组名[行数][列数];`

2.`数据类型	数组名[行数][列数] = {{数据1, 数据2}, {数据1, 数据2}};`

3.`数据类型	数组名[行数][列数]={1,2,3,4,5,6};`

4.`数据类型	数组名[][列数] = {1,2,3,4,5,6};`

#### 5.3.1 二维数组数组名

*   查看二维数组所占内存空间

*   获取二维数组地址

#### 打印杨辉三角

```c++
#include<iostream>
using namespace std;
int arr[55][55];
void printArr(int n)
{	//行数
	for (int i = 0; i < n; i++) {
		arr[i][0] = 1;
		arr[i][i] = 1;
	}
	//从第三行开始
	for (int i = 2; i < n; i++)
	{
		for (int j = 0; j < i; j++) {
			arr[i][j] = arr[i - 1][j - 1] + arr[i - 1][j];
		}
	}
	for (int i = 0; i < n; i++)
	{
		for (int j = 0; j <= i; j++)
		{
			cout << arr[i][j] << " ";
		}
		cout << endl;
	}

}

int main()
{
	int n;
	cin >> n;
	printArr(n);
	//cout << f[n][m] << endl;

	return 0;
}
```



## 6 函数



将一段经常使用的代码封装起来，减少重复代码

### 6.1 函数的定义

函数的定义主要分为5个步骤：

1.返回值类型 ： int

2.函数名  add

3.参数列表  int a，int b;

4.函数体语句  int sum\=a+b;

5.return表达式 return sum;

**语法：**

```c++
返回值类型 函数名 （参数列表）
{
	函数体
	return表达式
}
```

### 6.2 函数的调用

方法：函数名（参数）

函数定义里的小括号内城为形参，函数调用时传入的参数称为实参。

### 6.3 值传递

在函数调用时，实参将数值传入给形参

如果形参发生，并不会影响实参

函数不需要返回值，声明写void

`值传递，形参是改变不了实参的`

### 6.4 函数的常见样式

常见样式有4种：

1.  `无参无返`

2.  `有参无返`

3.  `无参有返`

4.  `有参有返`

示例：

```c++
//无参无返
void test()
{
cout<<"this is test"<<endl;
}
//有参无返
void test(int a)
{
	cout<<"this is test"<<a<<endl;
}
//无参有返
int test()
{
	cout<<"this is test"<<endl;
	return 100;
}
//有参有返
int test(int a)
{
	cout<<"this is test"<<a<<endl;
	return a;
}
```

### 6.5 函数的声明

作用：

`告诉编译器函数名称及如何调用函数，函数的实际主体可以单独定义。`

函数的声明可以多次，但是函数的定义只能有一次。

示例：

```c++
// 声明可以多次，定义只能一次 
// 声明
int max(int a , int b);
int max(int a , int b);
// 定义
int max(int a,int b)
{
	return a>b?a:b
}
int main()
{

}
```

提前告诉编译器函数的存在，可以利用函数的声明。

声明可以写多次，但是定义只能有一次。

### 6.6 函数的份文件编写

作用：让代码结构更加清晰

函数份文件编写4个步骤

*   创建后缀为.h的**头文件**

*   创建后缀名为.cpp的**源文件**

*   在**头文件**中写**函数的声明**

*   在**源文件**中写**函数的定义**

示例：

为了告诉编译器，源文件和头文件是相匹配的，需要在源文件中#include "swap"自定义的头文件，包括导入一些所需要的组件。

```c++
//swap.cpp源文件
#include"swap.h"
#include<iostream>
using namespace std;
void swap(int a, int b)
{
	int temp;
	temp = a;
	a = b;
	b = temp;

	cout << "a  = " << a << endl;
	cout << "b  = " << b << endl;
}
```

```c++
//swap.h 头文件
void swap(int a, int b);
```

在主函数中导入所需要的头文件。

```c++
//main主函数
#include<iostream>
#include"swap.h"
using namespace std;
int main()
{
	int a = 10;
	int b = 20;
	swap(a, b);
	system("pause");
	return 0;
}
```

## 7 指针

### 7.1 指针的基本概念

指针的作用：可以通过指针间接访问内存

*   内存编号从0开始记录，一般使用16进制数字表示

*   可以利用指针变量保存地址

`指针就是一个地址`

**示例：**

```c++
//1.如何定义指针
//2.如何使用指针
int a = 10;
// 定义指针的语法 数据类型 *指针变量;
int* p;
//让指针记录变量a 的地址 &取地址
p = &a;
cout << &a << endl;
cout << p << endl;
// 可以通过解引用的方式找到指针指向的内存
// 指针前加 * ，找到指针指向的内存中的数据
cout << *p << endl;
// *p 输出 10 
*p = 1000;
cout << a << endl;
cout << *p << endl;
//输出结果：a：1000，*p：1000
```

### 7.2 指针所占内存空间

指针也是一种数据类型，那么这种数据类型占用多少内存空间？

在32位操作系统占4个字节，在64位操作系统占8个字节。

**示例：**

```c++
cout << "sizeof int*:" << sizeof(int*) << endl;
cout << "sizeof int*:" << sizeof(float*) << endl;
cout << "sizeof int*:" << sizeof(double*) << endl;
cout << "sizeof int*:" << sizeof(char*) << endl;
//输出结果：8
```

### 7.3 空指针、野指针

**空指针**：指针变量指向内存编号为0的空间

**用途**：初始化指针变量

**注意**：空指针指向的内存是不可以访问的

**示例** ：

```c++
int*p=NULL;
```

**野指针**：指针变量指向非法的内存空间,是一种错误

**在程序中避免出现野指针**

**示例**：

```c++
int* p = (int*)0x1100;
```

`结论：空指针和野指针都不是我们申请的空间，因此不要访问。`

### 7.4 const修饰指针

const修饰指针的三种情况：

`1.const修饰指针：常量指针`

​	特点：指针的指向可以修改，但是指针指向的值不可以修改。

```c++
int a=10;
int b=10;
int *p=&a;
//常量指针
const int *p = &a;
```



`2.const修饰常量：指针常量`

​	特点：指针的指向不可以更改，指针指向的值可以改。

```c++
//指针常量
int* const p = &a;
//指向不可以改，指向的值可以改
```



`3.const即修饰指针，又修饰常量`

​	特点：指针的指向不可以更改，指针指向的值不可以更改

```c++
//const int* const p = &a;
```

技巧：

const 常量 * 指针

### 7.5 指针和数组

`作用：`利用指针访问数组中的元素

示例：

```c++
int main() {

	int arr[10] = { 1,2,3,4,5,6,7,8,9,10 };
	//利用指针
	int* p = arr;
	for (int i = 0; i < 10; i++) {
		cout << "利用指针访问第"<<i<<"个元素:" << *p << endl;
		p++;
	}
	system("pause");
	return 0;
}
```

`值传递`与`地址传递`

`地址传递`

```c++
void swap(int*p1,int*p2) {
	int temp = *p1;
	*p1 = *p2;
	*p2 = temp;

	cout << *p1 << endl;
	cout << *p2 << endl;
}
int main() {

	int a = 10;
	int b = 20;
	//地址传递
	swap(&a, &b);

	system("pause");
	return 0;
}
```

`值传递不会改变实参`

`地址传递会改变实参`

### 7.6 指针数组函数

案例描述：封装一个函数，利用冒泡排序，实现对整型数组的升序排序。

1.创建一个数组

2.创建函数，实现冒泡排序

3.打印排序后的数组

## 8 结构体

### 8.1 结构体基本概念

结构体属于用户`自定义的数据类型`，允许用户存储不同的数据类型。

### 8.2 结构体定义和使用

`语法：struct 结构体名 { 结构体成员列表 }；`

通过结构体创建变量的方式有三种：

1.struct student s1;

2.struct student s2 \= {...};

3.在定义结构体时顺便创建结构体变量。

```c++
#include<iostream>
using namespace std;
//1.创建学生的数据类型
//自定义的数据类型 ，一些类型集合组成的一个类型
// struct student{              }
struct student {
	//成员列表
	string name;
	int age;
	float score;
}s3;

int main() {
	// 1.struct student s1;
	struct student s1;
	s1.name = "张三";
	s1.age = 18;
	s1.score = 100;

	cout << "姓名:" << s1.name <<" 年龄:" << s1.age << " 成绩:" << s1.score << endl;

	//2. struct student = {...};
	struct student s2 = {"李四",18,100};
	cout << "姓名:" << s2.name << " 年龄:" << s2.age << " 成绩:" << s2.score << endl;
	//3. 在定义结构体时，定义结构体变量
	s3.name = "王二";
	s3.age = 19;
	s3.score = 100;
	cout << "姓名:" << s3.name << " 年龄:" << s3.age << " 成绩:" << s3.score << endl;
	system("pause");
	return 0;
}
```

`注意：`

`struct 关键字可以省略，在创建结构体变量的时候可以省略；`

`在结构体定义的时候 struct 不可以省略`

`结构体访问变量时，通过 “.” 来访问成员`

### 8.3 结构体数组

**作用**：将自定义的结构体放入到数组中方便维护

**语法**：`struct 结构体名 数组名{元素个数} = { {}，{}，{}，..., {} }；`

```c++
#include<iostream>
using namespace std;
#include<string>
//结构体数组
//1.定义结构体
struct student {
	string name;
	int age;
	float score;
};
int main() {
//2.创建结构体数组
	struct student stuArr[3] = { {"张三",19,100},{"李四",20,80},{"王二",20,70} };

//3.结构体数组中的元素赋值
	stuArr[2].name = "赵六";
	stuArr[2].age = 30;
	stuArr[2].score = 60;
//4.遍历结构体数组
	for (int i = 0; i < 3; i++) {
		cout << "姓名:" << stuArr[i].name << " ";
		cout << "年龄:" << stuArr[i].age << " ";
		cout << "分数:" << stuArr[i].score << " ";
		cout << endl;
	}
	system("pause");
	return 0;
}
```

### 8.4 结构体指针

**作用：通过指针访问结构体中的成员**

*   利用操作符`—>`可以通过结构体指针访问结构体属性

通过结构体指针，访问结构体中的属性，需要利用`—>`

```c++
#include<iostream>
#include<string>
using namespace std;
//定义学生结构体
struct student {
	string name;
	int age;
	float score;
};


int main() {
	//创建结构体变量
	struct student s = { "张三",18,90 };
	//通过指针指向结构体变量】
	 student* p = &s;
	//通过指针访问结构体变量中的数据
	 p->age = 20;
	 p->name = "李四";
	 p->score = 100;

	 cout << "姓名：" << p->name << " 年龄：" << p->age << " 成绩：" << p->score << endl;
	system("pause");
	return 0;
}
```

### 8.5 结构体嵌套结构体

作用：结构体中的成员可以是另一个结构体

例如：每个老师辅导一个学员，一个老师的结构体中，记录一个学生的结构体。

```c++
#include<iostream>
#include<string>
using namespace std;

struct student {
	string name;
	int age;
	float score;
};
struct teacher {
	int id;
	string name;
	int age;
	struct student stu;
};
int main() {

	teacher t;
	t.id = 100000;
	t.age = 70;
	t.name="张三";
	t.stu.age = 19;
	t.stu.name = "李四";
	t.stu.score = 100;

	system("pause");
	return 0;
}
```

`在结构体中可以定义另一个结构体作为成员，用来解决实际问题。`

### 8.6 结构体作函数参数

作用：将结构体作为参数向函数中传递

传递方式：

1.值传递

2.地址传递

示例：

```c++
#include<iostream>
using namespace std;
#include<string>

//定义学生结构体
struct student {
	string name;
	int age;
	float score;
};
//打印函数 值传递
//void printStudent(struct student s) {
//	cout << "子函数中" << "姓名" << s.name << s.age << s.score << endl;
//}
// 打印函数 地址传递

void printStudent(struct student *s) {
	cout << "地址传递参数" << "姓名：" << s->name << s->age << s->score << endl;
}

int main() {
	//结构体作为参数
	
	//将学生传入到一个参数中，打印身上的所有信息
	student stu;
	stu.name = "张三";
	stu.age = 18;
	stu.score = 100;

	//cout << stu.name << stu.age << stu.score << endl;
	//通过Print函数打印
	struct student* s = &stu;
	printStudent(s);

	cout << stu.name << stu.age << stu.score << endl;


	system("pause");
	return 0;
}
```

`值传递的过程中，形参发生改变，不会改变实参`

`地址传递过程中，形参发生改变，实参发生改变` **可以用来修改主函数的数据**

### 8.7 const使用场景

\*\*作用：\*\*const防止误操作

**示例：**

const使用场景

`在形参前加入 const`， 读取数据可行，加入const之后，一旦有修改的操作就会报错，可以防止误操作

```c++
void printStudent( const student *s) {
	cout << "地址传递参数" << "姓名：" << s->name << s->age << s->score << endl;
}
```

### 8.8 结构体案例

案例描述：

```c++
#include<iostream>
#include<string>
#include<ctime>
using namespace std;
//学生结构体
struct student {
	string sname;
	int  score;
};

struct Teacher {
	//姓名
	string tname;
	//学生数组
	struct student Arr[5];
};

//给老师和学生赋值的函数
void allocate(struct Teacher arr[],int length) {
	//老师开始赋值
	string nameSeed = "ABCDE";
	for (int i = 0; i < length; i++) {
		arr[i].tname = "Teacher_ ";
		arr[i].tname += nameSeed[i];
		for (int j = 0; j < 5; j++) {
			arr[i].Arr[j].sname = "Student_";
			arr[i].Arr[j].sname += nameSeed[j];
			//学生分数
			int random = rand() % 61 + 40;
			arr[i].Arr[j].score = random;
		}
	}

}
//打印所有信息函数
void printInfo(struct Teacher arr[], int length) {
	for (int i = 0; i < length; i++) {
		cout << "老师的姓名" << arr[i].tname <<endl;
		for (int j = 0; j < 5; j++) {
			cout << "\t学生的姓名:" << arr[i].Arr[j].sname << " ";
			cout << "\t学生的成绩:" << arr[i].Arr[j].score <<endl;
		}
	}
}

int main() {
	//随机数种子
	srand((unsigned int )time(NULL));
	//定义三名老师的数组
	Teacher tarr[3];
	int length = sizeof(tarr) / sizeof(tarr[0]);
	allocate(tarr,length);
	printInfo(tarr, length);

	system("pause");
	return 0;
}
```

### 8.8.2 案例二

```c
#include<iostream>
#include<string>
using namespace std;

//定义英雄结构体
struct Hero {
	string name;
	int age;
	string sex;
};
//冒泡排序实现年龄的排列
void bubbleSort(struct Hero Arr[], int length) {
	for (int i = 0; i < length - 1; i++) {
		for (int j = 0; j < length - 1 - i; j++) {
			if (Arr[j].age > Arr[j + 1].age) {
				struct Hero temp = Arr[j];
				Arr[j] = Arr[j + 1];
				Arr[j + 1] = temp;
			}
		}
	}
	cout << "排序后的：" << endl;
	for (int i = 0; i < length; i++) {
		cout << Arr[i].name << " ";
		cout << Arr[i].age << " ";
		cout << Arr[i].sex << endl;
	}
}

int main() {
	//创建结构体数组存放5名英雄
	Hero Arr[5] = {
		{"刘备",23,"男"},
		{"关羽",22,"男"},
		{"张飞",20,"男"},
		{"赵云",19,"男"},
		{"吕布",28,"男"}
	};
	//运行测试
	cout << "排序前：" << endl;
	for (int i = 0; i < sizeof(Arr) / sizeof(Arr[0]);i++) {
		cout << Arr[i].name << " ";
		cout << Arr[i].age << " ";
		cout << Arr[i].sex << endl;
	}
	//排序算法
	int length = sizeof(Arr) / sizeof(Arr[0]);
	bubbleSort(Arr, length);


	system("pause");
	return 0;
}
```

### 8 案例 通讯录管理系统

系统需求：

1.添加联系人 ，信息包括（姓名，性别，年龄，练习电话，家庭住址）最多1000；

2.显示联系人，显示联系人的信息

3.删除联系人，按照姓名删除指定联系人

4.查找联系人，按照姓名查找联系人

5.修改联系人，按照姓名重新修改联系人

6.清空联系人，清空通讯录所有信息

7.退出通讯录，退出当前通讯录

1.显示菜单功能

封装函数显示该界面，在main函数中调用该函数

```c++
void showMenu() {
	//1.显示菜单界面
	cout << "1.添加联系人" << endl;
	cout << "2.显示联系人" << endl;
	cout << "3.删除联系人" << endl;
	cout << "4.查找联系人" << endl;
	cout << "5.修改联系人" << endl;
	cout << "6.清空联系人" << endl;
	cout << "0.退出通讯录" << endl;
}
```

2.退出功能

根据不同的选择，进入不同的功能，可以选择Switch分支结构，将整个架构进行搭建。

选择 0 时候，退出通讯录功能。

3.添加联系人功能

​	1 设计联系人结构体

​	2 设计通讯录结构体

​	3 main函数中创建通讯录

​	4 封装添加联系人函数

​	5 测试添加联系人功能

```c++
struct People {
	string name;
	int sex;//1 男 2 女
	int age;
	string tel;
	string address;
};
```

```c++
struct Addressbooks {
	struct People personArray[1000];//通讯录中保存的联系人数组
	int size;//通讯录中的人员个数
};
```

添加联系人结构体设计

main函数中创建通讯录

```c++
void addPerson(Addressbooks *abs) {
	//判断通讯录是否已经满
	if (abs->size==MAX) {
		cout << "通讯录已满，无法添加！" << endl;
		return;
	}
	else
	{
		//添加具体联系
		string name;
		cout << "请输入联系人姓名:" << endl;
		cin >> name;
		abs->personArray[abs->size].name = name;
		
		//性别
		cout << "性别：" << endl;
		cout << "1 ----男" << endl;
		cout << "2 ----女" << endl;
		int sex = 0;
		while (true) {
			// 如果输入的是 1 或者 2可以退出循环，因为输入的正确值
			cin >> sex;
			if (sex == 1 || sex == 2)
					{
						abs->personArray[abs->size].sex = sex;
						break;
					}
			cout << "输入有误,重新输入！" << endl;
		}

		//年龄
		cout << "请输入年龄:" << endl;
		int age = 0;
		cin >> age;
		abs->personArray[abs->size].age = age;

		//电话
		cout << "请输入联系电话" << endl;
		string phone;
		cin >> phone;
		abs->personArray[abs->size].tel = phone;

		//家庭住址
		cout << "请输入家庭住址" << endl;
		string adr;
		cin >> adr;
		abs->personArray[abs->size].address = adr;

		//更新通讯录的人数
		abs->size++;

		cout << "添加成功!" << endl;

		system("pause");//请按任意键继续
		system("cls");//清屏操作
	}
}
```

2.显示联系人

功能描述：

显示通讯录中联系人信息

封装显示联系人函数

测试显示联系人功能

```c++
void showPerson(Addressbooks*abs) {
	//判断 人数是否为0，0提示记录为空
	//如果不为0，显示联系人信息
	if (abs->size == 0)
	{
		cout << "当前记录为空!" << endl;
	}
	else
	{
		for (int i = 0; i < abs->size; i++)
		{
			cout << "姓名:" << abs->personArray[i].name << "\t";
			cout << "性别:" <<( abs->personArray[i].sex==1?"男":"女") << "\t";
			cout << "年龄:" << abs->personArray[i].age << "\t";
			cout << "电话:" << abs->personArray[i].tel << "\t";
			cout << "住址:" << abs->personArray[i].address << endl;
		}
	}
	system("pause");
	system("cls");
}
```

3.删除联系人

功能描述：按照姓名删除指定联系人

实现步骤：

*   封装检测联系人是否存在

*   删除联系人函数

*   测试删除联系人功能

检测联系人是否存在函数：

```c++
int isExist(Addressbooks*abs, string name) {//参数一 通讯录 参数二 对比姓名
	//检测 原理 遍历通讯录中所有姓名
	for (int i = 0; i < abs->size; i++)
	{
		if (abs->personArray[i].name == name)
		{
			return i;
		}
		else
		{
			return -1;//如果遍历结束都没有找到 ，返回-1
		}
	}
}
```

实现删除功能：

将数组中的元素进行前移，数组长度减一的操作。

1.  查找联系人

功能描述：按照姓名查看指定联系人信息

封装查找联系人函数

测试查找指定联系人

```c
void findPerson(Addressbooks*abs) {
	cout << "请输入查找联系人：" << endl;
	string f_name;
	cin >> f_name;
	//判断是否存在
	int result = isExist(abs, f_name);
	if (result != -1)
	{
		cout << "姓名" << abs->personArray[result].name << "\t";
		cout << "性别" << abs->personArray[result].sex << "\t";
		cout << "年龄" << abs->personArray[result].age << "\t";
		cout << "电话" << abs->personArray[result].tel << "\t";
		cout << "住址" << abs->personArray[result].address << endl;
	}
	else
	{
		cout << "查无此人" << endl;
	}
	system("pause");
	system("cls");
}
```

5 修改联系人

按照姓名重新修改指定联系人

修改联系人实现步骤：

*   封装修改联系人函数

*   测试修改联系人功能

```c++
void modifyPerson(Addressbooks*abs) {
	cout << "输入修改联系人姓名" << endl;
	string e_name;
	cin >> e_name;

	int ret = isExist(abs, e_name);

	if (ret != -1)
	{
		//姓名
		string name;
		cout << "请输入姓名：" << endl;
		cin >> name;
		abs->personArray[ret].name = name;
		//性别
		cout << "请输入性别：" << endl;
		cout << "1 ----男" << endl;
		cout << "2 ----女" << endl;
		int sex = 0;
		while (true) {
			cin >> sex;
			if (sex == 1 || sex == 2)
			{	
			
				abs->personArray[ret].sex = sex;
				break;
			}
			else
			{
				cout << "输入有误" << endl;
			}
		}
		
		//年龄
		cout << "请输入年龄：" << endl;
		int age = 0;
		cin >> age;
		abs->personArray[ret].age = age;
		//电话
		cout << "请输入联系电话：" << endl;
		string tel;
		cin >> tel;
		abs->personArray[ret].tel = tel;
		//住址
		cout << "输入家庭住址：" << endl;
		string addr;
		cin >> addr;
		abs->personArray[ret].address = addr;


		cout << "修改成功" << endl;
	}
	else
	{
		cout << "查无此人！" << endl;
	}

	system("pause");
	system("cls");
}
```

6 清空联系人

清空通讯录中所有信息

封装清空联系人函数

测试清空联系人

实现思路：将通讯录中的所有联系人信息清除掉，只要通讯录记录的联系人数量为0

```c++
void cleanPerson(Addressbooks*abs) {
	
	abs->size = 0;
	cout << "通讯录已经清空" << endl;

	system("pause");
	system("cls");
}
```

## 9 C++ 核心编程

面向对象编程技术

**1.内存的分区模型**

*   代码区：存放函数的二进制代码，由操作系统进行管理

*   全局区：存放**全局变量**和静态**变量以及常量**

*   栈区：由编译器自动分配释放，函数的**参数值、局部变量**

*   堆区：由程序员分配和释放，结束后由操作系统回收

`内存分区的意义：`

不同区域存放的数据，赋予不同的生命周期，提供更灵活的编程。

**1 程序运行前**

代码区：存放CPU执行的机器指令

代码区是**共享**的，频繁执行的程序，只需要存放一份代码

代码区是**只读**的，防止程序意外修改它的指令

**代码区和全局区在程序运行前**

**全局区：**`全局变量、静态变量和常量`

特点：由操作系统释放

![image-20240219215107010](https://cdn.jsdelivr.net/gh/Faker-Lost/MyNote/data/202402192151134.png)

总结：

*   在c++程序运行之前分为全局区和代码区

*   代码区特点是共享和只读

*   全局区存放全局变量、静态变量、常量

*   常量区存放const就是的全局常量 和 字符串常量

**2 程序运行后**

**栈区**：编译器自动分配释放，存放函数的参数，局部变量等

`注意：不要返回局部变量的地址，栈开辟的数据由编译器自动释放。`

**堆区**：由程序员分配释放，程序结束后由操作系统回收。

在c++中利用`new`在堆区开辟内存

`new`将保存数据的地址传递出来，用`指针`进行接收

`指针本质局部变量，放在栈上，指针保存的数据是放在堆上`

```c++
int * func() {
	//利用new关键字

	int*p =  new int(10);
	return p;//返回地址

}
```

### 9.1 new操作符

c++中利用`new`在堆中开辟数据

堆中开辟的数据，由程序员手动开辟释放，程序结束后利用操作符`delete`

语法：`new 数据类型`

**注意：new 数据类型，在堆区创建数据，new返回的是该数据类型的指针，用指针能接受**

```c++
#include<iostream>
using namespace std;
int * func() {
	//利用new关键字 在堆创建整型的数据
	//new 返回的是该数据类型的指针，用 指针 接受
	int* p =  new int(10);
	return p; //返回指针

}
//在堆区开辟数组
void test() {
	//创建10整型数据的数组，在堆区
	int* arr = new int[10];
	for (int i = 0; i < 10; i++)
	{
		/**(arr+i) = i + 100;*/
		arr[i] = i + 100;
	}
	for (int i = 0; i < 10; i++) {
		cout << arr[i] << endl;
	}
	delete[] arr;//释放数组时，加[]
}

int main() {

	//int*p = func();

	//cout << *p << endl;
	//cout << *p << endl;
	//cout << *p << endl;
	////堆区的数据，由程序员分配和管理
	////释放 delete 关键字
	//delete p;
	//cout << *p << endl;
	test();

	system("pause");
	return 0;
}
```

### 9.2 引用

#### 9.2.1 引用的基本使用

作用：给变量起别名

语法：数据类型 &别名\=原名

```c++
int a = 10;
//引用
int& b = a;
b = 20;
cout << "a:" << a << endl;
cout <<"b:" << b << endl;
```

#### 9.2.2 引用的注意事项

*   引用必须声明引用的时候初始化

*   引用在初始化后，不可以改变

*   引用数据类型与原变量类型相同

```c++
	int a = 10;
	int c = 20;
	//引用
	int& b = a;
	b = c;//这是赋值操作，不是更改引用
	cout << "a:" << a << endl;
	cout <<"b:" << b << endl;
	cout << "c:" << c << endl;
```

**1 引用作为函数参数**

作用：函数传参时，可以利用引用的技术让形参修饰实参

`优点：可以简化指针修改实参`

```c++
//值传递 ，形参不会修饰实参
void swap01(int a,int b) {
	int t = a;
	a = b;
	b = t;

	cout << "swap a=" << a << endl;
	cout << "swap b=" << b << endl;
}
 
//地址传递，形参会修饰实参
void swap02(int*a,int*b) {
	int temp = *a;
	*a = *b;
	*b = temp;

}
//引用传递，形参会修饰实参
void swap03(int& a, int& b) {
	int temp = a;
	a = b;
	b = temp;
}

swap01(a, b);
swap02(&a, &b);
swap03(a, b);
```

> 总结：通过引用参数产生的效果同地址传递是一样的，引用的语法更加清楚。
>

**2 引用作为函数返回值**

**作用:引用可以作为函数的返回值存在的**

`注意：`

`不要返回局部变量引用,本质是野指针`

`可以返回函数的引用形参、类的成员、全局变量、静态变量`

用法：函数调用作为**左值**

```c++
int&  func() {
	int a = 10;//局部变量存放在栈 不可以返回局部变量
	return a;
}

int& func2() {//返回的是引用
	static int a = 10;//静态变量存放在全局区
	return a;
}

int main() {


	int& ref = func();
	int& ref2 = func2();
	cout << "ref:" << ref << endl;
	cout << "ref2:" << ref2 << endl;

	func2() = 1000;
	cout << "ref2:" << ref2 << endl;
	cout << "ref2:" << ref2 << endl;
	system("pause");
	return 0;
}
```

**函数返回的引用形参**：

> 作用：

```c++
int& func2(int&ra)//ra是a的别名
{
	ra++; //a++
	cout<<"ra的地址"<<&ra<<"ra="<<ra<<endl;// 4  
	return ra;
}

int main()
{
    int a = 3;
    int&b = func(a) ;//b是ra的别名
    cout<<"a的地址："<<&a<<"a= "<<a<<endl;//4
    coout<<"b的地址："<<&b<<"b="<<b<<endl;//4
}
```

**返回引用的函数是被引用的变量的别名**

```c++
int& func2(int&ra)//ra是a的别名
{
	ra++; //a++
	cout<<"ra的地址"<<&ra<<"ra="<<ra<<endl;// 4  
	return ra;
}

int main()
{
    int a = 3;
    int&b = func(a) ;//b是ra的别名
    cout<<"a的地址："<<&a<<"a= "<<a<<endl;//4
    coout<<"b的地址："<<&b<<"b="<<b<<endl;//4
    
    // func(a) = 10;//返回引用的函数是被引用的变量的别名
    //在实际开发时，不建议 函数返回 const int& func(int&ra)
    cout<<"a的地址："<<&a<<"a="<<a<<endl;//10
    cout<<"b的地址："<<&b<<"b="<<b<<endl;//10
}
```



**3 引用的本质**

本质：**指针常量**  `（const修饰指针，指针的指向不可以修改，指针指向的值可以更改）`

```c++
void func(int&ref) {
	ref = 100;
}
int main() {
	int a = 10;
	//自动转换为指针常量 int *const ref = &a;
	//指针常量指针指向不可以更改，也说明为什么引用不可以更改
	int& ref = a;

	ref = 20;//*ref = 20;

	cout << "a:" << a << endl;
	cout << "ref:" << ref << endl;

	system("pause");
	return 0;
}
```

`本质：指针常量`

**4 常量引用**

```c++
int a = 10;
//加上const int temp = 10; const int&ref = temp;
const int& ref = 10; //引用必须是合法的内存空间
//相当于：int temp = 8; const int&ref = temp;
//ref = 10; //const 不可以修改
```

1.常规用法：`const 修饰引用，防止形参改变实参`

2.地址传递中，调用函数，不可以传入**常量参数** ；

3.引用传递中，调用函数，不可以传入**常量参数**；

> 如果引用的数据对象类型不匹配，当引用为const是，c++将创建临时变量，让引用指向临时变量。

```c++
void show(const int&val) {
	//val = 1000；//在函数中修改形参，实参也会更改
	cout << val << endl;
}
int main()
{
 show(10);   
}
```

#### 9.2.3 各种形参的使用场景

**1）如果不需要在函数中修改实参**

- 实参很小，则按值传递
- 实参是数组，则使用const指针
- 实参是较大的结构，则使用const指针或const引用
- 数据实参是类，则使用const引用，传递类的标注方式是**引用传递**

**2）如果需要在函数中修改实参**

- 如果实参是内置数据类型，则使用指针。只要看到func(&a)，表示修改x
- 如果实参是数组，则只能使用指针
- 如果实参是结构体，使用指针或者引用
- 如果实参是类，则使用引用



### 9.3 函数提高

#### 1 函数默认参数

在c++中，函数的形参列表的形参是可以有默认值的。

`语法：返回值类型 函数名（参数=默认值）{}`

```c++
int func(int a,int b=20,int c=30) {//在函数中修改形参，实参也更改
	return a + b + c;
}
```

`注意事项：`

*   **某个位置有默认参数，从这位置后，从左到右必须有默认值**

*   如果**函数声明**有了默认参数，**函数的定义**就不能有默认参数了`（声明和定义只能有一个默认参数）`

*   **函数的默认参数，必须从右往左定义默认参数**

```c++
void func(int c,int a =10，int b =20);//函数声明

void func(int c,int a,int b)//函数定义
{
    cout<<a<<endl;
}


```



#### 2 函数占位参数

函数的形参列表中可以有占位参数，用来占位，调用函数时必须填补该位置。

`语法：返回值类型 函数名（数据类型）{}`

**占位参数，目前还用不到**

```C++
void func(int a, int)
{
  cout<<"this is function"<<endl;
}
```

#### 3 函数重载

作用：函数名可以相同，提高复用性

满足条件：

*   同一个==作用域==下

*   ==函数名称相同==

*   函数**==参数类型==**不同，或者**==个数不同==**或者**==顺序不同==**

注意：函数的返回值不可以作为函数重载的条件

```C++
void func()
{
  cout<<"func 的调用"<<endl;
}

void func(int a)
{
  cout<<"func 的调用"<<endl;
}

void func(double a)
{
  cout<<"func 的调用"<<endl;
}

void func(double a, int b)
{
  cout<<"func 的调用"<<endl;
}
```

#### 4 函数重载的注意事项

**函数重载的细节：**

- 使用重载函数时，如果数据类型不匹配，C++尝试使用类型转换与形参进行匹配，如果转换后有 多个函数能匹配上，编译将报错。
- 引用可以作为函数重载的条件，但是，调用重载函数的时候，如果实参是变量，编译器将形参类型的本身和类型引用视为同一特征

*   引用作为重载的条件，const int & a；

*   函数重载碰到默认参数，避免出现二义性；

*   const不能作为函数重载的特征

```C++
#include<iostream>
using namespace std;

//int func(int a, int b=10, int c=30)
//{
//	return a + b + c;
//}
void func(int&a)
{
	cout << "func(int&a)的调用" << endl;
}

void func(const int&a)
{
	cout << "func(const int&a)的调用" << endl;
}

void func2(int a=20)
{
	cout << "func2(int a=20)" << endl;
}

void func2(double a )
{
	cout << "func2(double a )" << endl;
}
int main()
{
	/*int a = 10;
	func(a);*/

	func2(10.0);

	system("pause");
	return 0;

  
```

#### 5 内联函数

在函数的声明和定义时：`inline void show();`

注意：

内联函数不能递归

内联函数节省时间，但是消耗内存；

```c++
inline void show(const short bh,const string message);

int main()
{
    {
        int bh = 3;
        string message = "sss"；
        cout<<""<<bh<<""<<message<<endl;
    }
    
     {
        int bh = 8;
        string message = "sss"；
        cout<<""<<bh<<""<<message<<endl;
    }
    
}
inline void show(const short bh,const string message)
{
    cout<<""<<endl;
}
```



## 10 类和对象

C++面向对象的三大特性：==封装==、==继承==、==多态==

万事万物皆可为对象，对象其本身有属性和行为

例如：

&#x20;       人类作为对象，属性有姓名 年龄  行为  走 跑 跳  吃饭

具有相同性质的对象，可以抽象为人类，人属于人类，车属于车类

### 10.1 封装

**封装的意义**

*   将属性和行为作为一个整体，表现生活中的事物

*   将属性和行为加以权限控制

#### 1 封装意义1

&#x20;     在设计类的时候，属性和行为写在一起，表现事物

`语法：class 类名 { 访问权限：属性  /  行为  };`

```C++
#include<iostream>
using namespace std;

const float PI = 3.14;

class Yuan
{
	//访问权限
public:
	//属性
	int m_r;
	//行为 获取圆周长
	double circulate()
	{
		return 2 * PI * m_r;
	}
};


int main()
{
	//实例化对象
	Yuan circle;
	circle.m_r = 10;
	cout << "周长：" << circle.circulate() << endl;


	system("pause");
	return 0;
}


```

```C++

#include<iostream>
using namespace std;
class Student
{
	//访问权限
public:
	//属性
	string s_name;
	int s_id;
	//行为 获取圆周长
	void show()
	{
		cout << "学生的姓名：" << s_name << endl;
		cout << "学生的学号：" << s_id << endl;
	}
};


int main()
{
	//实例化对象
	Student stu;
	stu.s_name = "李华";
	stu.s_id = 100;
	stu.show();



	system("pause");
	return 0;
}
```

类中的属性和行为统一称为 ==成员==&#x20;

**属性**：也称 ==成员属性==   ==成员变量==

**行为**：也称  ==成员函数==或==成员方法==

#### 2 封装意义2

​	类在设计时，可以把属性和行为放在不同的权限下，加以控制

**访问权限有三种：**

*   public 	公共权限 	成员 类内可以访问，类外可以访问

*   protected   保护权限         成员 类内可以访问，类外不可以访问

*   private       私有权限          成员 类内可以访问，类外不可以访问

```c++
#include<iostream>
using namespace std;
//访问权限 public protected private
//公共权限 public：		成员 类内可以访问，类外可以访问
//保护权限 protected：	成员 类内可以访问，类外不可以访问
//私有权限 private：	成员 类内可以访问，类外不可以访问
class Person
{
public:
	string p_name;
protected:
	string p_car;
private:
	int password;


public:
	void func() {
		p_name = "张三";
		p_car = "拖拉机";
		password = 100;
	}
};
int main()
{
	Person p1;
	p1.p_name = "李四";
	//p1.p_car = "benz";//保护权限，在类外访问不到
	//p1.password = 123;//私有权限，在类外访问不到
	p1.func();
	system("pause");
	return 0;
}
```

#### struct 和 class 的区别

**两者区别在于默认的访问权限不同**

区别：

*   struct默认是public 公共

*   class默认是private 私有

==注意：==

**struct类外访问，可以访问；**

**class类外访问，不可以访问；**

#### 3 成员属性设置为私有

**优点1**：将所有成员属性设置为私有，可以自己控制读写权限

**优点2**：对于写权限，可以检测数据的有效性

```c++
#include<iostream>
using namespace std;
#include<string>
//访问权限 public protected private
//公共权限 public：		成员 类内可以访问，类外可以访问
//保护权限 protected：	成员 类内可以访问，类外不可以访问
//私有权限 private：	成员 类内可以访问，类外不可以访问

//成员属性设置为私有 private 
// 1 可以自己控制读写的权限 2 检测数据有效性
class Person
{
public:
	void setName(string name)
	{
		p_name = name;
	}
	string getName()
	{
		return p_name;
	}
	//获取年龄 ，只读
	int getAge()
	{
		return p_age;
	}
	//只写idol
	void setIdol(string idol)
	{
		p_idol = idol;
	}


private:
	string p_name;//读写

	int p_age = 18;//只读

	string p_idol;//只写
};

int main()
{

	Person p;
	p.setName("张三");
	cout << "姓名：" << p.getName() << endl;

	//年龄设置
	cout << "年龄：" << p.getAge() << endl;

	//idol只写
	p.setIdol("李四");

	system("pause");
	return 0;
}
```

#### 4 设计案例1 ：设计立方体

设计立方体类，求出立方体的面积和体积，分别用全局函数和成员函数判断两个立方体是否相等。

```c++
#include<iostream>
using namespace std;
//立方体cube类
class Cube
{	
	//public 函数接口 设置获取，长宽高 
public:
	//设置长宽高
	void setl(int l) {
		m_l = l;
	}
	void setw(int w)
	{
		m_w = w;
	}
	void seth(int h)
	{
		m_h = h;
	}
	//获取长宽高
	int getl()
	{
		return m_l;
	}
	int getw()
	{
		return m_w;
	}
	int geth()
	{
		return m_h;
	}
	//行为 成员函数 求面积、体积
	int calculate_S()
	{
		return 2 * m_l * m_w + m_w * m_h + 2 * m_l * m_h;
	}
	int calculate_V()
	{
		return m_l * m_w * m_h;
	}

	bool isSamebyClass(Cube &c)
	{
		if (c.getl() == m_l && c.getw() == m_w && c.geth() == m_h)
		{
			return true;
		}
		else
		{
			return false;
		}
	}

	//属性 成员属性 长宽高
private:
	int m_l;

	int m_w;

	int m_h;
};

//利用全局函数判断
bool isSame(Cube& c1, Cube& c2)
{
	if (c1.getl() == c2.getl() && c1.getw() == c2.getw() && c1.geth() == c2.geth())
	{
		return true;
	}
	else
	{
		return false;
	}
}

int main()
{
	//实例化立方体类
	Cube c1;
	c1.seth(10);
	c1.setl(10);
	c1.setw(10);
	cout << "c1的长：" << c1.getl() << endl;
	cout << "c1的宽：" << c1.getw() << endl;
	cout << "c1的高：" << c1.geth() << endl;

	cout<<"c1的面积："<<c1.calculate_S()<<endl;
	cout << "c1的体积：" << c1.calculate_V() << endl;
	
	Cube c2;
	c2.seth(11);
	c2.setl(10);
	c2.setw(11);
	bool result = isSame(c1, c2);
	if (result == true)
	{
		cout << "c1和c2是相等的立方体" << endl;
	}
	else 
	{
		cout << "不相等" << endl;
	}


	bool  res = c2.isSamebyClass(c1);
	if (res == true)
	{
		cout << "c1和c2是相等的立方体" << endl;
	}
	else
	{
		cout << "c1和c2不相等" << endl;
	}

	system("pause");
	return 0;
}
```

#### 5 设计案例2 点和圆的关系

1.点到圆心的距离\=\=r

2.点到圆心的距离>r

3.点到圆心的距离\<r

4.点到圆心的距离

在`头文件`中对成员属性、成员函数进行声明

在创建`相应的源文件.cpp文件`，引入`头文件.h`保留具体成员函数

`头文件格式 circle.h`

```c++
#pragma once
#include<iostream>
#include"point.h"
using namespace std;

class Circle
	{
public:
	//设置半径
	void setR(int r);

	//获取半径
	int getR();

	//设置圆心
	void setCenter(Point center);

	//获取圆心
	Point  getCenter();

	private:
		int m_r;//半径
		Point m_Center;//类中 可以让另一个类作为本类中的成员
	};

```

`circle.cpp源文件`

```c++
#include"circle.h"
#include"point.h"

	//设置半径
	void Circle::setR(int r)
	{
		m_r = r;
	}
	//获取半径
	int Circle::getR()
	{
		return m_r;
	}
	//设置圆心
	void Circle::setCenter(Point center)
	{
		m_Center = center;
	}
	//获取圆心
	Point  Circle::getCenter()
	{
		return m_Center;
	}
```

在主函数中main 调用

```c++
int main()
{

	Circle c1;
	c1.setR(10);
	Point center;
	center.SetX(10);
	center.SetY(0);
	c1.setCenter(center);

	Point p1;
	p1.SetX(10);
	p1.SetY(11);

	isInCircle(c1, p1);

	system("pause");
	return 0;
}
```

### 10.2 对象

#### 1 对象的初始化和清理

*   生活中买的电子产品都会有出厂设置，某一天不用的时候也会删除一些自己的信息数据保证安全

*   C++的面向对象源自于生活，每个对象都会有初始设置以及对象销毁前清理数据的设置。

**构造函数**和**析构函数**

**编译器自动调用，编译器提供的构造函数和析构函数是空实现**

**构造函数语法**：`类名（）{}`

1.  构造函数，没有返回值，没有void

2.  函数名与类名相同

3.  构造函数可以有参数，因此可以发生重载

4.  程序在创建对象时候自动调用构造，无需手动调用且只调用一次

**析构函数：**`~类名（）{}`

1.  析构函数，没有返回值也不写void

2.  函数名称与类名相同，在名称前加上符合\~

3.  析构函数不可以有参数，因此不可以发生重载

4.  程序在对象销毁前会自动调用析构，无须受到调用，且只会调用一次

```c++
class Person
{
public:
	//1 构造函数
	Person()
	{
		cout << "Person构造函数的调用" << endl;
	}
	//2 析构函数 ，对象销毁前自动调用析构函数
	~Person()
	{
		cout << "Person析构函数的调用" << endl;
	}

};
```

##### 1 构造函数的分类及调用

`两种分类方式：`

​	按参数为：**有参构造**和**无参构造**

​	按类型为：**普通构造**和**拷贝构造**

**拷贝构造函数**语法：

```c
Person(const Person &p)
	{
		age = p.age;
		cout << "person的拷贝构造函数的调用" << endl;
	}
```

`注意事项 1 ：调用默认构造函数时，不要加（）`

```c++
Person p1(); //因为下面这行代码，编译器认为是一个函数的声明，不会认为再创建对象
//正确写法
Person p;
//在一个函数体内写一个函数的声明是允许的
```

三种**调用**方式：

​	1.**括号法**

​	`注意事项 1 ：调用默认构造函数时，不要加（）`

​	2.**显示法**

​	**匿名对象** 特点：当前行结束后，系统会立即回收匿名对象

​	3.**隐式转化法**

`	注意事项 2 ：不要利用拷贝构造函数，初始化匿名对象，编译器会认为Person（p3） ===Person p3;`对象声明

```c++
#include<iostream>

using namespace std;
//构造函数的分类及调用
//分类
// 参数：有参构造 无参构造(默认构造)
// 类型：普通构造 拷贝构造
class Person
{
	//构造函数
	//无参构造(默认构造函数)
public:
	Person()
	{
		cout << "person的无参构造函数的调用" << endl;
	}
	//有参构造
	Person(int a)
	{
		age = a;
		cout << "person的有参构造函数的调用" << endl;
	}
	int age;
	//拷贝构造函数
	Person(const Person &p)
	{
		age = p.age;
		cout << "person的拷贝构造函数的调用" << endl;
	}
	

	~Person()
	{
		cout << "person的析构函数的调用" << endl;
	}
};
void test01()
{
	//1.括号法
	Person p;//默认构造
	Person p2(10);
	//拷贝构造函数
	Person p3(p2);
	/*cout << "p2的年龄：" << p2.age << endl;
	cout << "p3的年龄：" << p3.age << endl;*/
	//2.显示法
	Person p1;
	Person p10 = Person(10);
	Person p11 = Person(p10);
    
    Person(10);//匿名对象 特点：当前行结束后，系统会立即回收匿名对象
    
    
	//3.隐式转换法
    Person p4 = 10; // Person p4 = Person(10);
	Person p5 = p4;	// Person p5 = Person(p4);
}



int main()
{
	test01();
	system("pause");
	return 0;
}
```

`注意事项 2 ：不要利用拷贝构造函数，初始化匿名对象，编译器会认为Person（p3） ===Person p3;`对象声明

##### 2 拷贝构造函数调用时机

C++中拷贝构造函数调用时机：

1.  使用一个`已经创建完毕的对象`来`初始化一个新对象`

2.  `值传递的方式`给函数参数传值

3.  以`值方式返回`局部的对象

```c++
#include<iostream>
using namespace std;
//方式1 ：使用一个已经创建完毕的对象来初始化一个新对象
class Person
{
public:
	//构造函数默认构造 无参构造
	Person()
	{
		cout << "Person默认构造函数调用" << endl;
	}
	
	//有参构造函数
	int m_age=18;
	Person(int age )
	{
		m_age = age;
		cout << "Person有参构造函数调用" << endl;
	}
	//拷贝构造函数
	Person(const Person &p) 
	{
		m_age = p.m_age;
		cout << "Person拷贝构造函数调用" << endl;
	}
	//析构函数
	~Person()
	{
		cout << "Person析构函数调用" << endl;
	}
};



//方式1 ：使用一个已经创建完毕的对象来初始化一个新对象

void test01()
{
	//Person p1(20);
	Person p1 = Person(20);//调用有参构造函数
	Person p2 = Person(p1);//调用拷贝构造函数
	cout << "p1的年龄：" << p1.m_age << endl;
	cout << "p2的年龄：" << p2.m_age << endl;
}

//方式2 ：以值传递的方式给函数参数传值

void doWork(Person p)
{
	p.m_age = 1000;
	cout << "年龄：" << p.m_age << endl;
}
void test02()
{
	Person p1;//默认构造函数
    //Person p = p1;隐式转换法：Person p = Perosn(p1);
	doWork(p1);
	//给一个函数值传递  相当于调用doWork函数
	

	cout << "初始年龄：" << p1.m_age << endl;
}

//3.值方式返回局部对象 
Person doWork02()
{
	Person p1;
	return p1;//Person p = Person(p1);
    //局部对象，函数结束后被释放，返回的p1创建新的对象，返回给test03
}

void test03()
{
	Person p = doWork02();
}
int main()
{
	test03();

	system("pause");
	return 0;
}
```

##### 3 构造函数的调用规则

默认情况下，c++编译器至少给一个类添加至少3个函数

1.  默认构造函数，（无参，函数体为空）

2.  默认析构函数（无参，函数体为空）

3.  默认拷贝构造函数，对属性进行`值拷贝`。

构造函数调用规则如下：

*   如果用户定义有参构造函数，c++不在提供默认无参构造，但是会提供默认拷贝

*   如果用户定义拷贝构造函数，c++不会提供其他构造函数

##### 4 深拷贝与浅拷贝

**经典面试问题，常见的一个坑**

**浅拷贝**：简单的赋值拷贝操作

**深拷贝**：在堆区重新申请内存空间，进行拷贝操作

`总结：如果属性有在堆区开辟的，一定要自己提供拷贝构造函数，防止浅拷贝带来的问题。`

浅拷贝出现的问题：堆区的内存重复释放



![](C++学习_md_files/1c2272d0-db8f-11ee-82c9-e319f2eeed19_20240306155659.jpeg?v=1\&type=image\&token=V1%3AFiqpqpj9nR6OyTWGKKBr11cBrj0ytmIaLNxrsVj1OJc)

解决办法：浅拷贝问题利用深拷贝进行解决，在堆区开辟新的内存

析构代码：如果堆区有内存，析构代码里将堆区的内存释放

##### 5 初始化列表

给类中的属性进行初始化操作。

语法：`构造函数（）：属性1（值1），属性2（值2），...{}`

```C++
#include<iostream>
using namespace std;
//初始化列表
class Person
{
public:
	//传统初始化
	/*Person(int a,int b,int c)
	{
		m_a = a;
		m_b = b;
		m_c = c;
	}*/
	//初始化列表
	Person(int a,int b,int c) :m_a(a), m_b(b), m_c(c)
	{
		
	}

	int m_a;
	int m_b;
	int m_c;

};
void test01()
{
	Person p(10,20,30);
	cout << "m_a:" << p.m_a << endl;
	cout << "m_b:" << p.m_b << endl;
	cout << "m_c:" << p.m_c << endl;
}


int main()
{

	test01();

	system("pause");
	return 0;
}
```

##### 6 类对象作为类成员

C++中==类中的成员==可以是==另一个类的对象==，我们称该成员为    ==对象成员。==

B类中有对象A作为成员，A为对象成员

那么创建B对象时，A与B的构造和析构顺序是谁先谁后？

```C++
#include<iostream>
using namespace std;
#include<string>
class Phone
{
public:
	
	Phone(string pName)
	{
		m_pname = pName;
		cout << "Phone的构造函数调用" << endl;
	}
	string m_pname;
	~Phone()
	{
		cout << "phone的析构函数调用" << endl;
	}
};
class Person
{
	//属性 姓名 手机
public:
	Person(string name,string  pname):m_name(name),m_phone(pname)
	{
		cout << "Person的构造函数调用" << endl;
		cout << "姓名：" <<name <<endl;
		cout << "手机：" << pname << endl;
	}
	~Person()
	{
		cout << "person析构函数" << endl;
	}

	string m_name;
	Phone m_phone;
};

void test()
{
	Person p("张三","苹果");
}
int main()
{

	test();


	system("pause");
	return 0;
}
```

`当其他类对象作为本类成员，构造时候先构造类对象，再构造自身，析构函数的顺序与构造相反`；

##### 7 静态成员

静态成员就是在成员变量和成员函数前加上关键字static，称为静态成员；

静态成员分类：

- 静态成员变量
  - 所有对象共享一份数据
  - 在编译阶段分配内存
  - 类内声明，类外初始化
- 静态成员函数
  - 所有对象共享同一个函数
  - 静态成员函数只能访问静态成员变量

```c++
#include<iostream>
using namespace std;


//静态成员变量
class Person
{
public:
	//所有对象共享同一个数据
	//编译阶段就分配了内存
	//类内声明，类外初始化
	static int m_a;
	//静态成员拥有访问权限
private:
	static int m_b;

};
//类外初始化
int Person::m_a = 100;
int Person::m_b = 200;
void test()
{
	Person p;
	cout << p.m_a << endl;//100

	Person p2;
	p2.m_a = 200;
	cout << p.m_a << endl;//200
}
void test02()
{
	//静态成员变量不属于某个对象，所有对象共享同一份数据
	//静态成员变量有两种访问方式
	//1. 通过对象进行访问
	/*Person p;
	cout << p.m_a << endl;*/
	//2. 通过类名进行访问
	cout << Person::m_a << endl;
	//cout << Person::m_b << endl; 类外访问不到私有成员变量
}
int main()
{
	test02();

	system("pause");
	return 0;
}
```

静态成员函数：

```c++
#include<iostream>
using namespace std;
//静态成员函数
//所有对象共享同一个函数
//静态成员函数只能访问静态成员变量
class Person
{
public:
	
	static void func()
	{	
		m_a = 200;	//静态成员函数访问静态成员变量
		//m_b = 10;	//静态成员函数 不可以访问 非静态成员函数
		cout << "static void func()调用" << endl;
	}
	int m_b;//非静态成员变量
	static int m_a;//静态成员变量
	//静态成员函数具有访问权限
private:
	static void func2()
	{
		cout << "static void func2()调用" << endl;
	}
};
int Person::m_a=100;

// 两种访问方式
void test01()
{
	//通过对象
	Person p;
	p.func();

	//p.func2();//私有作用域下静态成员函数，类外不可以被访问

	//通过类名
	Person::func();
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

### 10.3 C++对象模型和this指针

#### 1 成员变量和成员函数分开存储

在c++中，**成员变量** 和 **成员函数** 分来存储

**只有非静态成员变量才属于类的对象上**

**空对象占用内存空间：1**

原理：`c++编译器，给每个空对象分配一个字节空间，是为了区分空对象占内存的位置，每个空对象也应该有一个独一无二的内存地址。`

**不是空对象，按照数据类型分配内存空间**

**类中创建静态成员变量，内存空间保持不变，静态成员变量不属于类对象上**

- `非静态成员变量，属于类的对象上`
- 静态成员变量，不属于类的对象上
- 非静态成员变量，不属于类的对象上
- 静态成员变量，不属于类的对象上

```c++
#include<iostream>
using namespace std;
//成员变量 和 成员函数 分开存储
class Person {
	int m_a;//非静态   属于类的对象上
	static int m_b;//静态  不属于类的对象上

	void func() {//非静态成员函数 不属于类的对象上

	}
	static void func2() {//静态成员函数 不属于类的对象上

	}
};
int Person::m_b = 10;
void test() {
	Person p;
	//空对象占用的内存空间为：1
	//c++编译器，给每个空对象分配一个字节空间，是为了区分空对象占内存的位置

	cout << "size of p :" << sizeof(p) << endl;
}
void test02() {
	Person p;
	
	cout << "size of p :" << sizeof(p) << endl;
}
int main()
{
	test02();
	system("pause");
	return 0;
}
```

#### 2 this 指针概念



C++中成员变量和成员函数是分开存储的，每一个非静态成员函数只会诞生一份函数实例，也就是说多个同类型的对象会共用一块代码

问题：这一块代码是如何区分那个对象调用自己的呢？



C++通过提供特殊的对象指针，`this` 指针，解决上述问题，`this指针指向被调用的成员函数所属的对象`

this指针是隐含每一个`非静态成员函数`内的一种指针

this指针不需要定义，直接使用即可

**this指针的用途：**

1.当`形参和成员变量同名`时，可用`this`指针来区分

2.在`类的非静态成员函数中返回对象本身`，可使用`return *this`（this为指针，*this解引用，p1对象）

**`链式编程思想`**：

必须以引用的类型返回，`return*this`，返回对象本体

以`值的数据类型`返回，会调用 `拷贝构造函数`，会复制产生新的数据

```c++
#include<iostream>
using namespace std;
//1.解决名称冲突
//2.返回对象本身
class Person
{
public:
	//构造函数
	Person(int age)
	{
		//this指针指向被调用 成员函数 所属的 对象，this指向p1
		this->age = age;
	}
	//成员函数
	//Person& 为什么加&？以引用的返回类型
	//以值的方式返回，会调用拷贝构造函数，会复制出新的数据
	//以引用的类型返回，返回类型一直是p2
	Person& PersonAddPerson(Person &p)
	{
		this->age += p.age;
		//this指向p2的指针，而*this指向的是p2这个对象的本体
		return *this;
	}
	int age;
};

void test02()
{
	Person p1(10);
	Person p2(10);
	//链式编程思想
	p2.PersonAddPerson(p1).PersonAddPerson(p1).PersonAddPerson(p1);
	cout << "p2的age：" << p2.age << endl;
}

void test()
{
	Person p1 = Person(18);
	p1.age = 18;
	cout << "P1的age：" << p1.age << endl;
}

int main()
{
	test02();
	system("pause");
	return 0;
}
```

#### 3 空指针访问成员函数

C++中空指针可以调用成员函数，但是也要注意有没有用到this指针

如果用到this指针，需要加以判断保证代码的健壮性

```c++
#include<iostream>
using namespace std;

//空指针调用成员函数
class Person
{
public:
	void showClassName()
	{
		cout << "This is Person " << endl;
	}

	void showPersonAge()
	{
		//报错原因 传入指针为空 
		if (this == NULL)
		{
			return;
		}
		cout << "age=" << m_age << endl;
	}
	int m_age;
};

void test()
{
	Person* p = NULL;
	//p->showClassName();
	p->showPersonAge();

}


int main()
{
	test();
	system("pause");
	return 0;
}
```

#### 4 const修饰成员函数

**常函数：**

- **成员函数**后加`const`后我们称为这个函数为**常函数**
- **常函数**内不可以修改成员属性
- 成员属性声明时加关键字`mutable`后，在常函数中依然可以修改

**常对象：**

- **声明对象前**加const称该对象为**常对象** （实例化对象时加 const）
- **常对象**只能调用**常函数**

`this指针的本质：指针常量 指针的指向是不可以修改的，指针指向的值可以修改`

```c++
#include<iostream>
using namespace std;
//常函数 常对象
class Person {
public:
	// const Person* const this;在成员函数后加const   修饰的是this指针 
	void  showPerson()  const// 加入const 指针指向的值不可以修改 
	{	
		//this本质是指针常量 指向不可以修改 指向的值可以修改
		//this->m_a = 100;  this指针修饰 this本质是指针常量
		//this = NULL;      this指针是不可以修改指针的指向的
		this->m_b = 100;
	}
	void func()
	{

	}
	int m_a;
	mutable int m_b;//特殊变量，在常函数中，也可以修改这个值 mutable
};
void test()
{
	const Person p;
	//p.m_a = 100;//常对象，必须是可修改的左值
	p.m_b = 100;
	//常对象只能调用常函数
	p.showPerson();
	//p.func();//no 
}
int main()
{
	test();
	system("pause");
	return 0;
}
```

### 10.4 友元

public private 

private可以允许一些权限访问

在程序里，有些私有属性，也想让类外特殊的一些函数进行访问

**友元的目的就是让一个函数或者类访问另一个类中私有成员**



友元关键字：`friend`

友元的三种实现

1.全局函数做友元

2.类做友元

3.成员函数做友元



#### 1 全局函数做友元

**语法：**`friend void GoodGay(Building& building);`

```c++
#include<iostream>
using namespace std;
#include<string>
//建筑
class Building
{
	// GoodGay是Building好朋友 ，可以访问其中私有成员
	friend void GoodGay(Building& building);
public:
	Building()
	{
		m_sittingroom = "客厅";
		m_bedroom = "卧室";
	}


public:
	string m_sittingroom;
private:
	string m_bedroom;
};

void GoodGay(Building &building)
{
	cout << "访问" << building.m_sittingroom << endl;

	cout << "访问" << building.m_bedroom << endl;
}
void test()
{
	Building b1;
	GoodGay(b1);
}

int main()
{

	test();
	system("pause");
	return 0;
}
```

#### 2 类做友元

目的：让一个类访问领一个类的私有成员

`	friend	class GoodGay;`

```c++
#include<iostream>
using namespace std;

//类做友元
class Building;
class GoodGay
{
public:
	GoodGay();
	void vist();
		//参观函数

	Building* building;
};

class Building
{
	friend	class GoodGay;
public:
	Building();
public:
	string m_sittingroom;
private:
	string m_bedroom;
};
//类外写成员构造函数
Building::Building()
{
	m_sittingroom = "客厅";
	m_bedroom = "卧室";
}
GoodGay::GoodGay() {
	//创建一个建筑物
	building = new Building;
}
void GoodGay::vist()
{
	cout << "好基友类正在访问" << building->m_sittingroom << endl;
	cout << "好基友类正在访问" << building->m_bedroom << endl;
}
void test()
{
	GoodGay Boy;
	Boy.vist();
}

int main()
{

	test();
	system("pause");
	return 0;
}
```

#### 3 成员函数做友元

语法：`friend void GoodGay::visit();`

```c++
#include<iostream>
using namespace std;

class Building;
class GoodGay
{
public :
	GoodGay();
	void visit();//让visit访问 Building 中的私有的成员
	void visit2();//visit2 无法访问私有成员
	Building* build;
};
class Building {
	//成员函数作为本类的友元，可以访问私有成员
	friend void GoodGay::visit();
public:
	string m_sittingroom;
private:
	string m_bedroom;
public:
	Building();
};
//类外实现成员函数
Building::Building()//初始化构造函数
{
	m_sittingroom = "客厅";
	m_bedroom = "卧室";
}
GoodGay::GoodGay()
{
	build = new Building;//创建一个Building对象 指针指向堆区
}
void GoodGay::visit()
{
	cout << "好基友正在访问：" << build->m_sittingroom << endl;
	cout << "好基友正在访问：" << build->m_bedroom << endl;
}

void GoodGay::visit2()
{
	cout << "好基友正在访问：" << build->m_sittingroom << endl;
	//cout << "好基友正在访问：" << build->m_bedroom << endl;
}

void test()
{
	GoodGay g1;
	g1.visit();
	g1.visit2();
}


int main()
{
	test();

	system("pause");
	return 0;
}
```

### 10.5 运算符重载

运算符重新加载:对已有的运算符进行重新定义，赋予其另一种功能，以适应不同的数据类型。

#### 1 加号运算符重载

**作用**：实现两个`自定义数据类型`的运算

```c
//成员函数 实现两个对象相加属性后，返回新的对象
Person PersonAddPerson(Person &p){
	Person temp ;
    temp.m_a = this.m_a + p.m_a;
    temp.m_b = this.m_b + p.m_b;
    return temp;
}
//编译器起了一个通用名称 operator
Person operator+ (Person &p){
	Person temp ;
    temp.m_a = this.m_a + p.m_a;
    temp.m_b = this.m_b + p.m_b;
    return temp;
}
```

实现两个对象的相加：

`Person p3 = p1.operator+(p2);`

可以简化：

`Person p3 = p1 + p2;`

```c++
//通过全局函数重载+
Person operator+(Person &p1, Person &p2)
{
	Person temp;
	temp.m_a = p1.m_a + p2.m_b;
	temp.m_b = p1.m_b + p2.m_b;
	return temp;
}
```

函数调用：

`Person p3 = operator + (p1, p2);`

简化为：

`Person p3 = p1 + p2;`

**成员函数重载本质的调用：**

`Person p3 = p1.operator+(p2)`

**全局函数重载本质的调用：**

`Person p3 = operator+(p1,p2)`

**运算符重载，也可以发生函数重载**

```c++
Person p3 = p1 + 10;//Person + int
//函数重载的版本
Person operator+(Person &p1,int num)
{
	Person temp;
	temp.m_a = p1.m_a + num;
	temp.m_b = p1.m_b + num;
	return temp;
}
```

*`总结：`*

1.对于内置的数据类型的表达式运算符是不可以改变的的

2.不要滥用运算符重载

#### 2 左移运算符重载

`int a;`

`cout<<a ;`

```c++
Person p;
p.m_a =10;
p.m_b = 10;
cout<<p<<endl;
```



**作用：输出自定义的数据类型**

不能用`成员函数`重载`<<`运算符，因为无法实现`cout`在左侧

**利用全局函数重载<<运算符**

```c++
#include<iostream>
using namespace std;

//左移运算符重载
class Person
{
	friend ostream& operator<<(ostream& cout, Person& p);//友元
public:
	Person(int a ,int b)
	{
		m_a = a;
		m_b = b;
	}
private:
	int m_a;
	int m_b;
};
//ostream& 防止调用拷贝构造函数
ostream& operator<<(ostream &cout, Person &p)
{
	cout << "m_a = " << p.m_a << " m_b = " << p.m_b;

	return cout;
}

int main()
{

	Person p = Person(10,10);
	cout << p << endl;//链式编程思想 继续返回cout
	system("pause");
	return 0;
}
```

1.重载左移<<，输出对象

2.不能利用成员函数，利用全局函数

3.全局函数，cout是ostream数据类型



#### 3 递增运算符重载

作用：重载递增运算符，实现自己的整型数据

递增运算符  `++`

int a = 10;

cout<<++a; //输出 11

cout<<a; //输出 11



int b = 10；

cout<<b++;//输出 10；

cout<<b;  //输出 11

```c++
#include<iostream>
using namespace std;
//自定义整型
class MyInterger
{
	friend ostream& operator<<(ostream& cout, MyInterger myint);
public:
	MyInterger()
	{
		m_a = 0;
	}
	//重载前置++运算符 为什么返回& 为了一直对一个数据进行递增操作
	MyInterger& operator++()
	{
		m_a++;
		return *this;//返回自身
	}
	//重载后置++运算符 
	//void operator++(int) int 表示占位参数，可以用于区分前置和后置递增
	MyInterger operator++(int)
	{
		// 先返回结果 
		MyInterger temp = *this;//局部变量 用完销毁
		//后递增
		m_a++;
		//将记录的结果做返回
		return temp;
	}
private:
	int m_a;
};
// 重载<<运算符
ostream& operator<<(ostream& cout, MyInterger myint)
{
	cout << myint.m_a;

	return cout;
}

void test()
{
	MyInterger myint;
	cout << ++myint << endl;
	cout << myint << endl;
}

void test01()
{
	MyInterger myint;
	cout << myint++ << endl;
	cout << myint << endl;
}

int main()
{
	test01();
	system("pause");
	return 0;
}
```

总结：

`前置递增返回的是引用，后置递增返回值`

#### 4 赋值运算符的重载

c++编译器至少给一个类添加4个函数

1. 默认构造函数
2. 默认析构函数
3. 默认拷贝构造函数
4. 赋值运算符operator=

> 编译器提供的复制操作是浅拷贝，需要自己在堆区开辟新的空间

```c++
#include<iostream>
using namespace std;
class Person
{
public:
	Person(int age)
	{
		m_age = new int(age);
	}
	//堆区数据由程序员手动释放
	~Person()
	{
		if (m_age != NULL)
		{
			delete m_age;
			m_age = NULL;
		}
	}
	//返回引用
	Person& operator=(Person &p)
	{
		// 编译器提供的浅拷贝
		// m_age = p.m_age;

		//判断是否有属性在堆区，如果有先释放干净，然后再进行深拷贝
		if (m_age != NULL)
		{
			delete m_age;
			m_age = NULL;
		}
		//在堆区开辟空间
		m_age = new int(*p.m_age);
		return *this;
	}

	int* m_age;
};
void test()
{
	Person p1(10);
	Person p2(18);
	Person p3(30);
	//浅拷贝 堆区内存重复释放
	p3 = p2 = p1;

	cout << "p1的年龄:" << *p1.m_age << endl;
	cout << "p2的年龄:" << *p2.m_age << endl;
	cout << "p3的年龄:" << *p3.m_age << endl;
}
int main()
{
	
	test();
	
	system("pause");
	return 0;
}
```

#### 5 关系运算符重载

> 作用：重载关系运算符，可以让两个自定义类型对象进行对比操作

```c++
#include<iostream>
using namespace std;

class Person
{
public:
	Person(string name, int age)
	{
		m_name = name;
		m_age = age;
	}
	//重载关系运算符==
	bool operator==(Person &p)
	{
		if (this->m_name == p.m_name&&this->m_age==p.m_age)
		{
			return true;
		}
		else
		{
			return false;
		}
	}
	//重载关系运算符!=
	bool operator!=(Person& p)
	{
		if (this->m_name == p.m_name && this->m_age == p.m_age)
		{
			return false;
		}
		else
		{
			return true;
		}
	}

	string m_name;
	int m_age;
};

void test01()
{
	Person p1("Tom", 18);
	Person p2("Tom", 18);

	if (p1 == p2)
	{
		cout << "p1和p2是相等的" << endl;
	}
	else
	{
		cout << "p1和p2是不相等的" << endl;
	}
	//判断两人不相等
	if (p1 != p2)
	{
		cout << "p1和p2是不相等的" << endl;
	}
	else
	{
		cout << "p1和p2是相等的" << endl;
	}
}
int main()
{
	test01();
	system("pause");
	return 0;
}
```

#### 6 函数调用运算符重载

- 函数调用运算符（）也可以重载
- 由于重载后使用的方式非常像函数的调用，因此称为仿函数
- 仿函数没有固定写法，非常灵活

```c++
#include<iostream>
using namespace std;

// 函数调用运算符重载
class MyPrint {
public:
	void operator()(string test)
	{
		cout << test << endl;
	}

	int operator()(int a, int b)
	{
		int temp = a + b;
		return temp;
	}


};
void Myprint(string test)
{
	cout << test << endl;
}


void test()
{
	MyPrint print;
	Myprint("Hello");//函数调用
	print("Hello");	 //函数重载（） 仿函数
}
void test02()
{
	MyPrint mp;
	int sum = mp(10, 20);
	cout << sum << endl;

	//匿名函数对象 匿名对象重载（）
	cout << MyPrint()(10, 20) << endl;
}

int main()
{

	
	test02();
	system("pause");
	return 0;
}
```

### 10.6 继承

> 继承是面向对象三大特性之一

类和类之间存在特殊的关系 ：

动物：猫 狗

猫：加菲猫 布偶猫 

狗：哈士奇 京巴

`下级别的成员拥有上一级的共性，还有自己的特性`

`利用继承的技术，减少重复代码`

> **继承的好处：减少重复的代码**

**继承的语法：**

`class 子类 : 继承方式  父类 `  或  `class 派生类 : 继承方式 基类`

子类（派生类）中的成员，包含两大部分：

1.从父类（基类）继承过来了的

2.自己增加的成员

从基类继承过来的表现其共性，新增的成员体现了个性

#### 1 继承方式

继承的语法：`class 子类:继承方式 父类`

继承方式：

1.公共继承:public

2.保护继承:protect

3.私有继承:private

![image-20240313175128038](https://raw.githubusercontent.com/Faker-Lost/MyNote/main/data/image-20240313175128038.png)

1.在父类中 `private` ，全部`private都子类无法访问`

2.public继承：父类中`public`，子类中`public`；父类中`protected`，子类`protected`；

3.protected继承：父类中`public、protected`都变成`protected`，不可访问父类`private`；

4.private继承：父类中`public、protected`都变成p`rivate`，不可访问父类`private`；

#### 2 继承中对象模型

**问题：**从父类继承过来的成员，哪些属于子类对象中？

**答：**父类中所有的属性，非静态成员属性都会被子类继承下去

父类中私有的成员属性，被编译器隐藏，无法访问，但是确实被继承下去了

**总结：利用开发人员命令提示工具，查看对象模型**

> 1.跳转盘符 D： ;
>
> 2.跳转文件路径 cd 具体路径;
>
> 3.查看命令 ：cl /d1 reportSingleClassLayout 类名 文件名 ;	

#### 3 继承中的构造和析构顺序

Base的构造函数

Son的构造函数

Son的析构函数

Base的析构函数

**结论：继承中的构造和析构顺序如下**

1. 构造父类
2. 构造子类
3. 析构子类
4. 析构父类

#### 4 继承同名成员处理方式

**问题**：**当子类与父类出现同名的成员，如何通过子类对象，访问到子类或父类中同名的数据?**

**方法：**

- 访问子类同名成员，直接访问即可
- 访问父类同名成员，需要加作用域

**语法：通过子类对象访问父类中的同名成员，需要加作用域**

`子类.作用域::成员变量`

`cout << "b.m_a=" << s.Base::m_a << endl;`

```c++
void test()
{
	Son s;
	//调用子类成员
	cout << "s.m_a=" << s.m_a << endl;
	//调用子类成员函数
	s.func();
	Base b;
	//通过子类调用父类成员
	cout << "b.m_a=" << s.Base::m_a << endl;
	//通过子类调用父类中的同名成员函数
	s.Base::func();
}
//如果子类中出现父类同名成员函数，子类的同名成员函数会隐藏父类中
//所有的同名成员函数,如果调用需要加上作用域
s.Base::func(100);
```

> 总结：
>
> 1.子类对象可以直接访问子类中同名成员
>
> 2.子类对象加作用域可以访问父类同名成员
>
> 3.当子类与父类拥有同名成员函数，子类会隐藏父类同名成员函数，加作用域可以访问父类中同名函数

#### 5 继承同名静态成员处理方式

静态成员和非静态成员出现同名，处理方式一致

- 访问子类同名成员，直接访问即可
- 访问父类同名成员，需要加作用域

```c++
//通过对象访问
cout<<s.m_a<<endl;
cout<<s.Base::m_a<<endl;
//通过类名访问
cout<<Son::m_a<<endl;
cout<<Son::Base::m_a<<endl;
```

> 子类出现和父类同名静态成员函数，也会隐藏父类中所有同名成员函数
>
> 如果想访问父类中被隐藏的同名成员，需要加作用域

#### 6 多继承语法

c++中允许**一个类继承多个类**

`语法：class 子类:继承方式 父类1，继承方式2 父类2...`

***多继承可能引发父类中有同名成员出现，需要加作用域区分***

**c++实际开发中不建议使用多继承**

> 当父类中出现同名的成员，子类需要加作用域区分

```c++
	Son s1;
	cout << "sizeof(Son):" << sizeof(s1) << endl;
	cout << "Base1 m_a:" << s1.Base1::m_a << endl;
	cout << "Base2 m_a:" << s1.Base2::m_a << endl;
```

#### 6 菱形继承

**菱形继承概念**：

两个派生类继承同一个基类

有某个类同时继承两个派生类

这种继承称为**菱形继承**或称**钻石继承**

***导致问题：***

1.当菱形继承，两个父类拥有相同数据，需要加以作用域区分

2.子类所需数据，只有一份就可以，菱形继承导致数据有两份，资源浪费

> **解决方案：**
>
> **利用虚继承解决菱形继承的问题** **virtual**
>
> `语法:class 子类:virtual public 父类{};`
>
> 父类（Animal） 类称为 **虚基类**
>
> 虚继承之后，访问数据只有一个

```c++
#include<iostream>
using namespace std;

class Animal
{
public:
	int m_Age;
};

class Sheep :virtual public Animal
{

};

class Camel :virtual public Animal
{

};

class Yangtuo :public Camel, public Sheep
{

};

void test01()
{
	Yangtuo st;
	st.Sheep::m_Age = 18;
	st.Camel::m_Age = 28;
	cout << "st.Sheep.m_Age:" << st.Sheep::m_Age << endl;
	cout << "st.Camel.m_Age:" << st.Camel::m_Age << endl;
	cout << "st.m_Age:" << st.m_Age << endl;

	//数据有两份继承数据，导致资源浪费
}
int main()
{

		test01();
		system("pause");
		return 0;
}
```

### 10.7 多态

#### 1 多态的基本概念

多态是c++中三大特性之一

多态分为两类：

- 静态多态：***函数重载***和***运算符重载***属于**静态多态**，复用函数名
- 动态多态：***派生类***和***虚函数***实现运行时多态

> 静态多态和动态多态的区别：
>
> - **静态多态**的函数地址早绑定-**编译阶段确定函数地址**
>
> - **动态多态的函数地址晚绑定**-**运行阶段确定函数地址**
>
>   
>
>   **动态多态满足条件：**
>   1.有继承关系；2.子类要重新父类的虚函数；
>
> **重写的概念：**函数的返回值类型，函数名，参数列表 完全相同
>
> **动态多态的使用：**
>
> 1.**父类的指针或者引用指向子类的对象**

#### 2 多态的底层原理

**virtural **实现地址的晚绑定

**Animal：**函数加入**virtual**，会改变**类Animal**中的内部结构， 在内部中会有4个字节的指针：**vfptr（虚函数表指针）**，指针指向->指向**vftable（虚函数表）**，**虚函数表中存放Animal类中虚函数的地址**，*&Animal::speak()*;

**Cat:**Cat类继承Animal类中的虚函数指针与虚函数表，如果子类中发生**重写虚函数**，子类中的**虚函数表**会替换成子类的**虚函数地址**；

> 当父类的指针或者引用指向子类对象时，就会发生动态多态；
>
> Animal & animal = cat;
>
> animal.speak();

```c++
#include<iostream>
using namespace std;
//动物类
class Animal
{
    //动态多态
public:
    virtual void speak()//虚函数
    {
        cout << "动物在说话" << endl;
    }
};

//猫类继承动物类
class Cat :public Animal
{
public:
    virtual void speak()
    {
        cout << "小猫在说话" << endl;
    }
};
class Dog :public Animal
{
public:
    virtual void speak()
    {
        cout << "小狗在说话" << endl;
    }
};
//执行说话的函数
//地址早绑定，在编译阶段确定函数地址
//需要在运行阶段进行绑定,地址晚绑定
//现在是animal地址，都会访问animal
//  动态多态满足条件：
// 1.有继承关系；2.子类要重新父类的虚函数；
void doSpeak(Animal& animal)
{
    animal.speak();
}
int main() {
 
    Cat cat;
    doSpeak(cat);
    Dog dog;
    doSpeak(dog);

    return 0;
}
```

#### 3 多态案例——计算器类

分别使用普通和多态技术，设计实现操作运算的计算器

> 多态的优点：
>
> - 代码组织结构清晰
> - 可读性强
> - 利于前期和后期的拓展以及维护

```c++
#include<iostream>
using namespace std;
//实现计算器的基类
class AbstractCalculator
{
public:
	virtual int getResult()
	{
		return 0;
	}

	int m_a;
	int m_b;
};
//加法计算器类
class Add :public AbstractCalculator
{
public:
	virtual int getResult()
	{
		return m_a + m_b;
	}
};
//减法计算器类
class Sub :public AbstractCalculator
{
public:
	virtual int getResult()
	{
		return m_a - m_b;
	}
};
//乘法
class Mul :public AbstractCalculator
{
public:
	virtual int getResult()
	{
		return m_a * m_b;
	}
};
void test()
{
	//多态使用
	//父类的指针或者引用指向子类对象
	AbstractCalculator* abs;
	abs = new Add;
	abs->m_a = 100;
	abs->m_b = 100;

	cout << abs->m_a << " + " << abs->m_b << " = " << abs->getResult()<<endl;
	delete abs;

	abs = new Sub;
	abs->m_a = 100;
	abs->m_b = 100;
	cout << abs->m_a << " - " << abs->m_b << " = " << abs->getResult()<<endl;
	delete abs;

	abs = new Mul;
	abs->m_a = 100;
	abs->m_b = 100;
	cout << abs->m_a << " *" << abs->m_b << " = " << abs->getResult() << endl;
	delete abs;

}
int main()
{
	test();
	return 0;
}
```

#### 4 纯虚函数和抽象类

在多态中，通常父类中虚函数实现是毫无意义的，主要都是调用了父类重写的内容

因此可以将虚函数改写为**纯虚函数**

`纯虚函数写法：`

`virtual 返回值类型 函数名 (参数列表)=0；`

当类中出现的**纯虚函数**，这个类称为**抽象类**

> **抽象类特点：**
>
> - 无法实例化对象
> - 抽象类的子类必须重写抽象类中的纯虚函数，否则也属于抽象类

```c++
#include<iostream>
using namespace std;
//纯虚函数
class Base {//抽象类 无法实例化对象
public :
	//纯虚函数
	virtual void func() = 0;
};

//子类 必须重写抽象类纯虚函数 否则无法实例化
class Son:public Base {
public:
	//子类中必须重写父类中的纯虚函数
	virtual void func(){
		cout << "Son.func 的调用" << endl;
	}
};
void test()
{
	//Base* base = new Son;
	Son s1;
	Base& base = s1;
	base.func();
}

int main()
{
	test();
	return 0;
}
```

#### 5 多态案例二-制作饮品

```c++
#include<iostream>
using namespace std;

//多态案例2 制作饮品
class AbstractDrink {
public:
	//煮水
	virtual void Boil() = 0;

	//冲泡
	virtual void Brew() = 0;

	//Pour
	virtual void Pour() = 0;

	//加入
	virtual void AddSometing() = 0;

	//制作饮品
	void makeDrink()
	{
		Boil();
		Brew();
		Pour();
		AddSometing();

	}
};
//制作
class Coffee :public AbstractDrink
{
public:
	//煮水
	virtual void Boil()
	{
		cout << "煮水" << endl;
	}

	//冲泡
	virtual void Brew()
	{
		cout << "冲咖啡" << endl;
	}

	//Pour
	virtual void Pour() {
		cout << "倒入咖啡杯" << endl;
	}

	//加入
	virtual void AddSometing() {
		cout << "加入糖" << endl;
	}
};

//制作茶叶
class Tea : public AbstractDrink
{
public:
	//煮水
	virtual void Boil()
	{
		cout << "煮矿泉水" << endl;
	}

	//冲泡
	virtual void Brew()
	{
		cout << "冲茶叶" << endl;
	}

	//Pour
	virtual void Pour() {
		cout << "倒入水杯" << endl;
	}

	//加入
	virtual void AddSometing() {
		cout << "加入枸杞" << endl;
	}
};
void doWork(AbstractDrink *abs)
{
	abs->makeDrink();
}
void test01()
{
	//制作咖啡
	doWork(new Coffee);
	cout << "---------------" << endl;
	doWork(new Tea);
}

int main()
{
	test01();
	return 0;
}
```

####  6 虚析构和纯虚析构

多态使用时，如果子类中有属性开辟到堆区，那么父类指针在释放时无法调用子类的析构代码。

解决方式：将父类中的析构函数改为虚析构或者纯虚析构

虚析构和纯虚析构：

- 解决父类指针释放子类对象
- 都需要函数实现

应用场景：

- 如果是纯虚析构，该类属于抽象类，无法实例化对象

```c++
#include<iostream>
#include<string>
using namespace std;
//虚析构 和 纯虚析构
class Animal
{
public:
	Animal()
	{
		cout << "Animal 构造函数" << endl;
	}
	//虚析构
	/*virtual ~Animal()
	{
		cout << "Animal 析构函数" << endl;
	}*/
	//纯虚析构 需要代码实现  类内声明，类外初始化
	//有了纯虚析构，属于抽象类，无法实例化对象
	virtual ~Animal() = 0;
	//纯虚函数
	virtual void speak() = 0;
};
Animal:: ~Animal()
{
	cout << "Animal 纯虚析构函数" << endl;
}

class Cat : public Animal
{
public:
	Cat(string name) 
	{
		cout << "Cat构造函数调用" << endl;
		m_name = new string(name);
	}
	~Cat()
	{
		if (m_name != NULL)
		{
			cout << "Cat析构函数调用" << endl;
			delete m_name;
			m_name = NULL;
		}
	}

	virtual void speak()
	{
		cout << *m_name <<"小猫在说话" << endl;
	}

	string *m_name;
};

void test01()
{
	Animal* anl = new Cat("Tom");
	//父类指针不会调用子类中析构函数，导致子类中有堆区属性，出现内存泄露。
	//解决方案 ： 将 析构 改成为 虚析构，解决父类指针释放子类对象时不干净的问题。
	anl->speak();
	delete anl;
}
int main()
{
	test01();
	return 0;
}
```

> 总结：
>
> 1.虚析构或纯虚析构就是用来解决通过父类指针释放子类对象
>
> 2.如果子类中没有堆区数据，可以不写为虚析构或者纯虚析构
>
> 3.拥有纯虚析构函数的类属于抽象类

#### 7 多态案例3——电脑组装

```c++
#include<iostream>

using namespace std;

class CPU
{
public:
	virtual void caculate() = 0;
};

class VideoCard
{
public:
	virtual void display() = 0;
};

class MemoryCard
{
public:
	virtual void store() = 0;
};

class Computer
{
public:
	Computer(CPU*cpu, VideoCard*vc, MemoryCard*mc)
	{
		m_cpu = cpu;
		m_vc = vc;
		m_mc = mc;
	}

	void Work()
	{
		m_cpu->caculate();

		m_vc->display();

		m_mc->store();
	}
	//提供析构函数 释放三个
	~Computer()
	{
		if (m_cpu != NULL)
		{
			delete m_cpu;
			m_cpu = NULL;
		}
		if (m_vc != NULL)
		{
			delete m_vc;
			m_vc = NULL;
		}
		if (m_mc != NULL)
		{
			delete m_mc;
			m_mc = NULL;
		}
	}
private:
	CPU* m_cpu;
	VideoCard* m_vc;
	MemoryCard* m_mc;
};

//具体厂商
class IntelCPU :public CPU
{
public:
	virtual void caculate()
	{
		cout << "Intel CPU is working" << endl;
	}
};

class IntelVideoCard :public VideoCard
{
public:
	virtual void display()
	{
		cout << "Intel VideoCard is working" << endl;
	}
};

class IntelMemoryCard :public MemoryCard
{
public:
	virtual void store()
	{
		cout << "Intel MemoryCard is working" << endl;
	}
};
void test01()
{
	//父类指针指向子类对象
	CPU* intelCpu = new IntelCPU;

	VideoCard* intelCard = new IntelVideoCard;

	MemoryCard* intelMemory = new IntelMemoryCard;

	//创建第一台电脑
	Computer* cmp = new Computer(intelCpu, intelCard, intelMemory);
	cmp->Work();
	delete cmp;
}

int main()
{
	test01();
	return 0;
}
```

## 11 文件操作

包含头文件`<fstream>`

操作文件的三大类：

1.ofstream:写操作

2.ifstream:读操作

3.fstream:读写操作

### 11.1 文本文件

写文件步骤如下：

1.包含头文件：

​	`#include<fstream>`

2.创建流对象

​	`ofstream ofs;`

3.打开文件：

​	`ofs.open("文件路径",打开方式)；`

4.写数据：

​	`ofs<<"写入的数据";`

5.关闭文件：

​	`ofs.close();`

> 文件操作必须包含头文件；
>
> 读文件可以利用ofstream 或者fstream
>
> 打开文件时候需要指定操作文件的路径，以及打开方式
>
> 利用<<可以向文件中写数据
>
> 操作完毕，要关闭文件

#### 11.2 读文件

1.头文件

​	#include<fstream>

2.流对象

​	ifstream ifs;

3.打开文件

​	ifs.open("",打开方式);

4.读数据

​	四种方式读取

5.关闭文件

​	ifs.close();

```c++
#include<iostream>
#include<fstream>
#include<string>
using namespace std;

void test()
{
	//1 包含头文件<fstream>
	//2 创建流对象
	ofstream ofs;
	//读文件
	ifstream ifs;
	//3 打开文件
	ofs.open("test.txt", ios::out);
	//4 写数据
	ofs << "姓名：张三" << endl;
	ofs << "姓名：张三" << endl;
	ofs << "姓名：张三" << endl;
	//5 关闭文件
	ofs.close();
	//打开文件 打开方式 ios::in;
	ifs.open("test.txt", ios::in);
	if (!ifs.is_open())
	{
		cout << "文件打开失败" << endl;
		return;
	}
	/*char buf[1024] = { 0 };
	while (ifs >> buf)
	{
		cout << buf << endl;
	}*/
	/*char buf[1024] = { 0 };
	while (ifs.getline(buf,sizeof(buf)))
	{
		cout << buf << endl;
	}*/
	/*string buf;
	while (getline(ifs, buf))
	{
		cout << buf << endl;
	}*/
	//不推荐
	char c;
	while ((c = ifs.get()) != EOF)
	{
		cout << c;
	}

	ifs.close();
}
int main()
{
	test();
	return 0;
}

```

### 11.2 二进制文件

以二进制的方式对文件进行读写操作

打开方式指定为：ios::binary

#### 1 写文件

二进制写文件主要利用流对象调用成员函数`write`

函数原型：`ofstream& write(const char*buffer,int len);`

```c++
#include<iostream>
#include<fstream>
using namespace std;
class Person
{
public:
	char m_Name[64];
	int age;
};
int main()
{
	ofstream ofs;
	ofs.open("person.txt", ios::out | ios::binary);

	Person p = { "张三",18 };
	ofs.write((const char*)&p, sizeof(p));

	ofs.close();

	return 0;
}
```

#### 2 读文件

二进制读文件主要利用流对象调用成员函数 read

函数原型:`istream& read (char *buffer,int len);`

参数解释：字符指针buffer指向内存中的一段存储空间，len是读写的字符数

```c++
	ifstream ifs;
	ifs.open("person.txt", ios::in | ios::binary);
	//判断是否打开
	if (!ifs.is_open())
	{
		cout << "文件打开失败" << endl;
		return 0;
	}
	//读文件
	ifs.read((char*)& p,sizeof(p));
	cout << "姓名:" << p.m_Name << " 年龄：" << p.age << endl;
	ifs.close();

	return 0;
}
```

# C++提高篇

本阶段主要针对C++中泛型编程和STL技术

## 1 模版

模板的特点：

不能直接使用，只是一个框架

通用并不是万能的

### 1.1 函数模版

c++中另一种编程思想是`泛型编程`,主要利用技术是模版技术

c++提供两种模版机制：**函数模版和类模版**

函数模版的作用：

**建立一个通用函数，其返回值类型和形参类型可以不具体制定，用一个虚拟的类型来代表**

**语法：**

```c++
template<typename T>
函数声明定义
```

- template ——声明创建模版
- typename ——表明其后面的符号是一种数据类型，可以用class替换
- T——通用的数据类型，名称可以替换，通常为大写字母

```c++
#include<iostream>
using namespace std;

//函数模板
template<typename T>
void mySwap(T &a,T &b)
{
	T temp = a;
	a = b;
	b = temp;
}


int main()
{
	int a = 10, b = 20;
	//运用函数模板 
	//两种方法 1. 自动类型推导 2.显示指定类型
	//mySwap(a, b); 
	mySwap<int>(a, b);

	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
	return 0;
}
```

> 总结：
>
> 函数模板利用关键字template
>
> 使用函数模板有两种方式：自动类型推导，显示指定类型
>
> 模板的目的是提高复用性

### 1.2 函数模板注意事项

 注意事项：

- 自动类型推导，必须推导出一致的数据类型T，才可以使用
- 模板必须要确定T的数据类型吗，才可以使用

```c++
#include<iostream>
using namespace std;

//函数模板
template<class T>
void mySwap(T &a,T &b)
{
	T temp = a;
	a = b;
	b = temp;
}
//模板必须确定出T的数据类型，才可以使用
template<class T>
void func()
{
	cout << " sssssssss" << endl;
}
void test01()
{
	int a = 10;
	int b = 20;
	//char c = 'c'; 推导不出一致的数据类型
	mySwap(a, b);
	func<int>();
	cout << "a=" << a << endl;
	cout << "b=" << b << endl;
}

int main()
{
	test01();
	//运用函数模板 
	//两种方法 1. 自动类型推导 2.显示指定类型
	//mySwap(a, b); 
	return 0;
}
```

### 1.3 函数模板案例

```c++
#include<iostream>
using namespace std;
template<class T>
void mySwap(T &a, T&b)
{
	T temp = a;
	a = b;
	b = temp;
}
template<class T>
void mySort(T tmp[], int len)//选择排序
{
	for (int i = 0; i < len; i++)
	{
		int max = i;
		for (int j = i + 1; j < len; j++)
		{
			if (tmp[max] < tmp[j])
			{
				max = j;
			}
		}
		if (max != i)
		{
			mySwap(tmp[max], tmp[i]);
		}
	}
}

template<class T>
void myPrint(T arr[],int len)
{
	for (int i = 0; i < len; i++)
	{
		cout << arr[i] << " ";
	}
}

int main()
{
	int arr[] = { 1,2,3,4,5,6,7,8,9,0 };
	int len = sizeof(arr)/sizeof(int);
	/*char arr[] = "abcdefgh";
	int len = sizeof(arr)/sizeof(char);*/
	mySort(arr, len);
	myPrint(arr, len);
	return 0;
}
```

### 1.4 普通函数与函数模板的区别

普通函数与函数模板的区别：

- 普通函数调用时可以发生自动类型转换（隐式类型转换）
- 函数模板调用时，如果利用自动类型推导，不会发生隐式类型转换
- 如果利用显示指定类型的方式，可以发生隐式类型转换

> 总结：建议使用显示指定类型的方式，调用函数模板，因为可以自已确定通用类型T；

### 1.5 普通函数与函数模板的调用规则

- 如果函数模板和普通函数都可以实现，优先调用普通函数
- 可以通过空模板参数列表来强制调用函数模板

`myPrint< >(a,b);`强制转换

- 函数模板也可以发生重载

- 如果函数模板可以产生更好的匹配，优先调用函数模板

### 1.6 模板的局限性

模板的通用性并不是万能的

例如：如果传入的是一个数组，无法实现

```c++
template<class T>
void f(T a, T b)
{
	a = b;
}
```

因此 C++提供了模板的重载，可以为这些特定的数据类型提供具体的模板

模板并不是万能，有些特定的数据类型，需要具体方式做特殊实现

```c++
//利用具体的Person版本实现代码，具体实现
template<> bool myCompare(Person &p1, Person &p2)
{
	if(p1.m_Name == p2.m_Name)
	return true;
	else
	return false;
}
```

### 1.7 类模板

```c++
#include<iostream>
#include<string>
using namespace std;
//类模板
template<class NameType,class AgeType>
class Person
{
public:
	Person(NameType name, AgeType age)
	{
		this->m_name = name;
		this->m_age = age;
	}
	void showPerson()
	{
		cout << "m_name:" << this->m_name << endl;
		cout << "m_age:" << this->m_age << endl;
	}
	NameType  m_name;
	AgeType  m_age;
};
void test01()
{
	Person<string,int> p1 = Person<string,int>("孙悟空",19);
	p1.showPerson();
}
int main()
{
	test01();
	return 0;
}
```

总结：

类模板和函数模板语法相似，在声明模板template后面加类，此类为类模板。

### 1.8 类模板和函数模板的区别

主要区别有两点：

- 类模板没有自动类型推导的使用方式
- 类模板在模板参数列表中可以有默认参数

```c++
Person p("孙悟空",100)//错误
Person<string,int> p1 = Person<string,int>("孙悟空",19);

template<class NameType,class AgeType = int>//类模板中的类型参数
```

### 1.9 类模板的成员函数创建时机

类模板中的成员函数并不是一开始就创建的，在调用时才去创建；

### 1.10 类模板对象做函数参数

类模板实例化出的对象，向函数传参的方式

1. 指定传入的类型——直接显示对象的数据类型
2. 参数模版化——将对象中的参数变为模板进行传递
3. 整个类模板化——将这个对象类型模板化进行传递

```c++
#include<iostream>
#include<string>
using namespace std;
//类模板
template<class NameType,class AgeType>
class Person
{
public:
	Person(NameType name, AgeType age)
	{
		this->m_name = name;
		this->m_age = age;
	}
	void showPerson()
	{
		cout << "m_name:" << this->m_name << endl;
		cout << "m_age:" << this->m_age << endl;
	}
	NameType  m_name;
	AgeType  m_age;
};
//1 指定传入类型
void printPerson01(Person<string, int> &p)
{
	p.showPerson();
}
void test01()
{
	Person<string,int> p1("孙悟空",19);
	printPerson01(p1);
	//p1.showPerson();
}
//2 参数模板化 
template<class NameType,class AgeType>
void printPerson2(Person<NameType, AgeType> &p)
{
	p.showPerson();
	cout << "NameType的类型：" << typeid(NameType).name() << endl;
	cout << "AgeType的类型：" << typeid(AgeType).name() << endl;
}
//3 整个类模板化——将这个对象类型模板化进行传递
template<class T>
void printPerson03(T &p)
{
	p.showPerson();
	cout << "T 的数据类型：" << typeid(T).name() << endl;
}

void test03()
{
	Person<string, int> p3 = { "唐僧",19 };
	printPerson03(p3);
}

void test02()
{
	Person<string, int> p2("猪八戒", 100);
	printPerson2(p2);
}
int main()
{
	/*test02();
	test01();*/
	test03();
	return 0;
}
```

总结：

通过函数类模版创建的对象，有三种方式向函数中进行传参

使用比较广泛的是第一种：指定传入的类型

### 1.11 类模板与继承

当类模板碰到继承，需要注意以下几点：

1. 当子类继承的父类是一个类模板时，子类在声明的时候，要制定出父类中T 的类型
2. 如果不指定，编译器无法给子类分配内存
3. 如果想灵活指定出父类中T的类型，子类也需要变为类模板              

```c++
#include<iostream>
using namespace std;

template<class T>
class Base
{
public:
	Base()
	{

		cout << "Base 构造函数调用 ，m的数据类型：" << typeid(m).name() << endl;
	}
	~Base()
	{
		cout << "Base 析构函数调用" << endl;
	}
	T m;// char
};

class Son:public Base<int>
{

};
void test01()
{
	Son s1;
}
template<class T1,class T2>
class Son2 :public Base<T2>
{
public:
	Son2()
	{
		cout << "Son2 构造函数调用，T1的数据类型：" << typeid(T1).name() << endl;
		cout << "Son2 构造函数调用，T2的数据类型：" << typeid(T2).name() << endl;
	}
	~Son2()
	{
		cout << "Son2 析构函数调用" << endl;
	}
	T1 obj;// int 
};
void test02()
{
	Son2<int, char> s2;
}

int main()
{

	test02();
	return 0;
}
```

总结：

如果父类是类模板，子类需要指定父类中 T 的数据类型

### 1.12 类模板成员函数类外实现

学习：

能够掌握类模板中的成员函数类外实现

```c++
#include<iostream>
#include<string>
using namespace std;

template<class T1,class T2>
class Person
{
public:
	Person(T1 name, T2 age);
	/*{
		this->m_name = name;
		this->m_age = age;
	}*/
	void showPerson();
	/*{
		cout << "m_name:" << this->m_name << endl;
		cout << "m_age:" << this->m_age << endl;
	}*/
	T1 m_name;// char
	T2 m_age;
};
//构造函数类外实现
template<class T1, class T2>
Person<T1, T2>::Person(T1 name, T2 age)
{
	this->m_name = name;
	this->m_age = age;
}
//成员函数类外实现
template<class T1, class T2>
void Person<T1,T2>::showPerson()
{
	cout << "m_name:" << this->m_name << endl;
	cout << "m_age:" << this->m_age << endl;
}
void test01()
{
	Person<string,int> p("张三",19);
	p.showPerson();
}

int main()
{

	test01();
	return 0;
}
```

### 1.13 类模板分文件编写

主要包含两种方式：

1. 直接包含cpp源文件
2. 将声明和实现写到统一文件中，并更改后缀名为.hpp，类模板文件

将类模板与成员函数写到一起，并将后缀名改为.hpp

### 1.14 类模板与友元

掌握类模板配合友元函数的类内和类外实现

全局函数类内实现-直接在类内声明友元

全局函数类外实现-需要提前让编译器直到全局函数的存在

```c++
#include<iostream>
#include<string>
using namespace std;
//1.让编译器知道模板类
template<class T1,class T2>
class Person;
//2.全局函数类外函数模板实现，需要编译器提前知道这个函数的存在
template<class T1, class T2>
void showPerson(Person<T1, T2> p)
{
	cout << "姓名：" << p.m_name << endl;
	cout << "年龄：" << p.m_age << endl;
}

template<class T1,class T2>
class Person
{
	//普通函数声明,所以需要添加一个空模板参数列表
	//如果成员函数 类外实现，需要让编译器提前知道这个函数的存在
	friend void showPerson<>(Person<T1, T2> p);
	//全局函数类内实现
	/*friend void showPerson(Person<T1,T2> p)
	{
		cout << "姓名：" << p.m_name << endl;
		cout << "年龄：" << p.m_age << endl;
	}*/
public:


	Person(T1 name, T2 age)
	{
		this->m_name = name;
		this->m_age = age;
	}

private:
	T1 m_name;
	T2 m_age;
};


void test01()
{
	Person<string, int> p("孙悟空", 19);
	showPerson(p);
}

int main()
{
	test01();
	return 0;
}
```

总结：建议使用全局函数类内实现，用法简单，而且编译器可以直接识别

----------------------------案例待做-----------------------

## 2 STL库函数

STL 标准模板库（standard template libary）

STL广义上分：

1. 容器 container
2. 算法 algorithm
3. 迭代器 iterator

容器和算法通过迭代器进行无缝衔接

**STL六大组件：**

1. 容器：各种数据结构，vector、list、deque、set、map等
2. 算法：各种常用的算法，sort、find、copy、for_each
3. 迭代器：扮演容器与算法之间的胶合剂
4. 仿函数：行为类似函数，可作为算法的某种策略
5. 适配器：一种用来修饰容器或者仿函数或迭代器接口的东西
6. 空间适配器：负责空间的配置与管理

### 2.1 容器、算法、迭代器

**容器：**置物之所也

STL容器就是运用最广泛的一些数据结构实现出来

常用的数据结构：**数组、链表、数、栈、队列、集合、映射表等**

容器分为：**序列式容器**和**关联式容器**

**序列式容器：**强调值的排序，序列式容器中的每个元素均有固定的位置

**关联式容器：**二叉树结构，各元素之间没有严格的物理上的顺序关系



**算法：**问题之解法

有限的步骤，解决逻辑或数学上的问题

算法分为：**质变算法** 和 **非质变算法**

**质变算法：**运算过程中更改区间内的元素的内容。例如拷贝、替换、删除

**非质变算法：**不更改区间内元素的内容。例如查找、技术、遍历、寻找极值等等



**迭代器：**容器与算法之间的粘合剂

提供一种方法，使能够依序访问某个容器所含的各个元素，而又无需暴露该容器的内部表示方式

**每个容器又自己专属的迭代器**

### 2.2 容器 迭代器 

**1.vector 数组**

语法：vector

算法：for_each

迭代器:vector<int>::iterator

第一种迭代操作：常用

```c++
#include<vector>//包含头文件
int main()
{
    vector<int> arr; //创建vector
    
    arr.push_back(10); //插入元素
    arr.push_back(20);
	arr.push_back(30);
	arr.push_back(40);
    //迭代器访问vector中元素 迭代器相当于指向数组的指针
    for(vector<int>::iterator it = arr.begin();it!=arr.end;it++)//常见的操作
    {
        cout<<*it<<end;//解引用
    }
}
```

第二种迭代操作

```c++
//迭代器操作
vector<int>::iterator itBegin = arr.begin();//起始迭代器，指向容器第一个元素
vector<int>::iterator itEnd = arr.end();//结束迭代器，指向容器中最后一个元素的下一个位置
while (itBegin != itEnd)
	{
		cout << *itBegin << endl;
		itBegin++;
	}
```

第三种迭代操作:利用STL中提供的算法

```c++
#include<algorithm>
void myPrint(int val)
{
	cout << val << endl;
}
for_each(arr.begin(),arr.end(),myPrint);
```

### 2.3 Vector存放自定义数据类型

```c++
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;
class Person
{
public:
	  Person(string name,int age)
	  {
		  this->m_name = name;
		  this->m_age = age;
	  }
	string m_name;
	int m_age;
};
void test01()
{
	vector<Person> arr;
	Person p1("aa", 10);
	Person p2("bb", 10);
	Person p3("cc", 10);
	Person p4("dd", 10);
	Person p5("ee", 10);
	//向容器中插入数据
	arr.push_back(p1);
	arr.push_back(p2);
	arr.push_back(p3);
	arr.push_back(p4);
	arr.push_back(p5);

	//通过迭代器访问
	//vector<int>::iterator itBegin = arr.begin();//起始迭代器，指向容器第一个元素
	//vector<int>::iterator itEnd = arr.end();//结束迭代器，指向容器中最后一个元素的下一个位置
	//第一种遍历
	/*while (itBegin != itEnd)
	{
		cout << *itBegin << endl;
		itBegin++;
	}*/
	//第二种遍历
	for (vector<Person>::iterator it = arr.begin(); it != arr.end(); it++)
	{
		cout << "姓名：" << (*it).m_name << " 年龄：" << (*it).m_age << endl;
		cout << "姓名：" << it->m_name << "年龄：" << it->m_age << endl;
	}
	//第三种迭代 利用STL中提供的算法
	/*for_each(arr.begin(), arr.end(), myPrint);*/
}
void test02()
{
	vector<Person*> arr;//指针
	Person p1("aa", 10);
	Person p2("bb", 10);
	Person p3("cc", 10);
	Person p4("dd", 10);
	Person p5("ee", 10);
	//向容器中插入数据
	arr.push_back(&p1);
	arr.push_back(&p2);
	arr.push_back(&p3);
	arr.push_back(&p4);
	arr.push_back(&p5);

	for (vector<Person*>::iterator it = arr.begin(); it != arr.end(); it++)
	{
		cout << "姓名：" << (*it)->m_name << "年龄："<<(*it)->m_age << endl;
	}
}
int main()
{
	test02();
	return 0;
}
```

> 存放自定义数据类型
>
> vector<数据类型> name;
>
> (*it)是什么数据类型 ——> 看 <数据类型>

### 2.4 vector中嵌套容器

容器中嵌套容器

```c++
#include<vector>
#include<iostream>
#include<algorithm>
using namespace std;
int main()
{
    vector<vector<int>> v;
    vector<int>v1;
    vector<int>v2;
    vector<int>v3;
    vector<int>v4;
    //小容器中插入数据
    for (int i = 0; i < 4; i++)
    {
        v1.push_back(i + 1);
        v2.push_back(i + 2);
        v3.push_back(i + 3);
        v4.push_back(i + 4);
    }
    //向大容器中添加数据 
    v.push_back(v1);
    v.push_back(v2);
    v.push_back(v3);
    v.push_back(v4);
    //迭代 遍历所有数据
    for (vector<vector<int>>::iterator it = v.begin(); it != v.end(); it++)
    {
        //*it ----vector
        for (vector<int>::iterator v_it = (*it).begin(); (v_it) != (*it).end(); v_it++)
        {
            cout << *v_it << " ";
        }
        cout << endl;
    }
}
```

### 2.5 String 容器

string是c++风格的字符串，string 本质是一个类

string和char*的区别：

char*是指针

string是一个类，类内部封装了char*,管理字符串，另一个是char*的容器



