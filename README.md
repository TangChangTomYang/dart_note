Flutter 学习

# flutter 开发快捷键







# 一、Flutter介绍



## 1、Flutter是什么?

Flutter is Google's UI toolkit for building beautiful, natively compiled applications for mobile, web, and desktop from a single codebase.



**对上面话的总结**:

- Flutter 是一个UI SDK (Software Development Kit)

- 可以进行移动端(iOS、Android), web端(Beta), 桌面(techical preview), 跨平台解决方案. 

- 移动端目前已经很多公司在用,Google、阿里、腾讯

- 特别是阿里的咸鱼团队, 为Flutter做了很多的贡献

- Flutter它有一统大前端的野心, 并且它正在侵蚀iOS、Android 这些原生的开发.

  

## 2、Flutter 的特点

- Google 公司在国内做过很多宣讲, 其中多次提到Flutter的几个特点:
  - **美观**:
    - 使用flutter 内置的Material Design 和 Cupertino widget、丰富的motion API、平滑而自然的滑动效果和平台感知, 为用户带来全新体验. 
  - **快速**:
    - Flutter 的UI渲染性能很好, 在生产环境下, Flutter将代码编译成机器码执行, 并且充分利用GPU的图形加速能力, 因此使用Flutter开发的移动端应用, 即使在低配手机上也能实现每秒60帧的UI渲染能力. 
    - Flutter引擎使用C++代码编写, 包括高校的Skia 2D渲染引擎, Dart运行时和文本渲染库. 
  - **高校**:
    - Hot  Reload(热重载), 在前端已经不是什么新鲜的东西了, 但在移动端之前一直是没有的. 
  - **开放**:
    - Flutter 是开放的, 它是一个完全开源项目. 



## 3、跨平台解决方案历史

1、webView

2、ReactNative

3、Flutter

> flutter 出现到现在, 我个人一直非常的看好, 因为它有可能是很久依赖所期望的一种跨平台解决方案



**三种跨平台方案的对比**:

| 步骤\跨平台方案 | flutter on iOS/Android             | 原生Android                        | ReactNative                                     |
| --------------- | ---------------------------------- | ---------------------------------- | ----------------------------------------------- |
| 第一步          | 启动APP                            | 启动App                            | 启动App                                         |
| 第二步          | Flutter框架<br />(Dart)Skia(C/C++) | Android框架<br />(java)Skia(C/C++) | RN 框架<br />Android框架(java)<br />Skia(C/C++) |
| 第三步          | CPU/GPU                            | CPU/GPU                            | CPU/GPU                                         |



## 4、渲染引擎Skia

- Skia就是Flutter向GPU提供数据的途径
- Skia(全称 skia Graphics Library (SGL)), 是一个又C/C++ 编写的开源图形处理库. 
- 能在低端手机上呈现高质量的2D图形, 最初由Skia公司开发, 后来被Google 收购. 

- 应用于Android、Google Chrome、 Chrome OS 等当中
- 目前, Skia已然是 Android官方的图像渲染引擎了, 因此Flutter Android SDK 无需内嵌Skia 引擎就可以获得天然的Skia支撑
- 而对于iOS平台来说, 由于Skia是跨平台的, 因此它作为Flutter iOS渲染引擎被嵌入到Flutter的iOS SDK中, 替代了iOS闭源的Core Graphics/ CoreAnimation/CoreText, 这也正是Flutter iOS SDK打包的App 体积比Android要大一些的原因. 
- 底层渲染能力统一了, 上层开发接口和功能体验也就随即统一了, 开发者再也不用操心平台相关的渲染特性了. 也就是说, Skia保证了同一套代码调用在Android 和iOS平台上的渲染效果是完全一致的. 

  



# 二、flutter 环境搭建



环境搭建流程:

1、执行命令` flutter create helloFlutter` 创建flutter项目.

2、搭建flutter的环境的前提条件是下载 **Flutter SDK** , 如果是苹果电脑就下载 **MacOS 的Flutter SDK**, 如果是windows 电脑就下载 **windows Flutter SDK** .

3、Flutter SDK 下载完成后是一个压缩包, 下载完成后需要解压.

4、配置Flutter环境变量

5、配置Dart环境变量





> 环境搭建有点麻烦, 特别是android 环境的安装, 大家要耐心安装

## 1、操作系统的选择

- 学习阶段:
  - windows 和 macOS 都可以
- 开发阶段:
  - 一般使用macOS, 因为我们需要针对iOS进行调试, 通常方便起见使用macOS. 



## 2、安装 Flutter SDK 

- **Flutter SDK 下载地址 **

  - https://flutter.dev/docs/development/tools/sdk/releases

    - mac: https://flutter.dev/docs/development/tools/sdk/releases?tab=macos

  - 选择自己的操作系统和最新的稳定版本就可以了(stable 版本) 

  - 一般我的做法是下载完成解压后将`flutter` 目录直接拖进`/Users/edz/Library/`  目录中(即, 当前用户下的资源库).  

- **安装Flutter** 

  解压下载好的Flutter SDK, 在Windows 和macOS 都是一样的(选择一个自己想要安装的目录即可), 但是在macOS中, 我们通常会将flutter拖入到当前用户的资源库路径中`/Users/edz/Library` 

- **环境变量配置**(flutter 和 dart)

  - **macOS 环境变量配置**

    因为我们之后需要在命令终端执行Flutter的命令, 所以需要配置环境变量.macOS 或 linux环境需要编辑(`~/.bash_profile` 文件) 
  
    ```
    export FLUTTER_HOME=/Users/edz/Library/flutter
    export PATH=$PATH:$FLUTTER_HOME/bin
    export PATH=$PATH:$FLUTTER_HOME/bin/cache/dart-sdk/bin
    ```
  
    > 注意:
    >
    > 因为macOS 10.15.4 之后命令终端默认不在使用bash, 而是使用的是zsh, 在zsh 中配置环境变量和bash中是不一样了的.`zsh` 需要在`~/.zshrc` 文件中配置. zsh 中的`.zshrc` 文件与bash中的`.bash_profile` 文件功能与配置方式都一样, 只是文件名不同. 
  
  - **Window 环境变量配置**

    点击计算机图标 -- 属性 -- 高级系统设置 -- 高级 -- 环境变量,找到path, 在其中添加Flutter SDK目录下bin目录以及Dart的目录
  
  - **检查Flutter配置成功** 
  
    在终端执行`flutter --version` , 出现如下内容, 说明安装flutter 成功.
  
    ![](images/1592535699873.jpg) 
  
    

## 3、配置镜像

- flutter 项目会依赖一些东西, 在国内下载这些依赖会有一些慢, 所以我们可以将它的安装源换成国内的(也就是设置国内的镜像)

  - **macOS 或者Linux操作系统, 依然是编辑`~/.bash_profile` 文件** 

    ```
    export PUB_HOSTED_URL=https://pub.flutter-io.cn
    export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn 
    ```

  - **windows用户还是需要修改环境变量** 

    点击计算机图标 -- 属性 -- 高级系统设置 -- 高级 -- 环境变量

    新建变量 `PUB_HOSTED_URL`, 其值为`https://pub.flutter-io.cn`

    新建变量 `FLUTTER_STORAGE_BASE_URL`, 其值为`https://storage.flutter-io.cn` 
    
  
  > 注意: 
  >
  > 此镜像是临时镜像, 并不能保证一直可用, 大家可以参考**Using Flutter in China** 以获取有关镜像服务器的最新动态. 
  
  

## 4、配置iOS环境

如果想为Flutter 配置iOS开发环境, 需要在我们的电脑上安装Xcode( macOS环境), Xcode 安装完成后选择自己想用的iOS模拟器.

打开Xcode -> 左上角点击Xcode -> open Developer Tools -> Simulator

![](images/1592533608827.jpg) 

这个时候会打开一个默认的iOS 模拟器, 也可以在Hardware -> Device ->系统版本中选择自己想要的测试的模拟器

![](images/1592533871112.jpg) 

iOS 模拟器打开后我们就能看到下面的界面了

![](images/1592534000737.jpg)  

这时,我们执行如下命令:

```
flutter doctor
```

会看到如下信息:

![](images/1592551868602.jpg) 





## 5、配置Android环境

如果想为Flutter配置Adroid开发环境, 需要在我们的电脑上安装一个Android Studio. Android Studio 是Google 官方的android 应用开发工具.

- **Android Studio 的下载&安装 ** 

  官网地址: https://developer.android.com/studio/?utm_source=android-studio

  下载完成后, 双击即可.  具体安装流程百度一下.

- **创建Adroid 模拟器: ** 

  安装好后, 我们就可以去创建模拟器:

  选择 `Configure -> AVD Manager`

  ![](images/1592552478368.jpg) 

   

  **选择create virtual device** 

  ![](images/1592552543594.jpg) 

  

  **选择一个你想用的设备** ![](images/1592552620812.jpg)   

  **选择Android的版本** (一般现在主要兼容5.0以上, 目前最新的是10.0系统), 点击 download.

  

  下一个界面, 点解`accept next` 就可以了

  ![](images/1592553814434.jpg) 

  

  **接着下一步, 给自己的模拟器起一个名字** 

  ![](images/1592553875220.jpg) 

  

  **启动Android 模拟器** 
  
  ![](images/1592553924968.jpg) 

  

  这个时候, 我们执行一下如下命令;

  ```
  flutter doctor
  ```
  
  看到如下有两个可用的设备
  
  ![](images/1592554009629.jpg) 
  
  

## 5、开发工具及插件选择

- 官方推荐两个工具来开发flutter, `Android Studio` 和 `VSCode` 
- **`VSCode` 的优缺点:**  
  - VSCode是非常流行的前端开发工具, 非常好用.  VSCode最近有取代webStorm 作为前端开发的工具的趋势. 
  
  - VSCode 其实并不能称之为一个IDE, 它只是一个编辑器而已. 所有它非常的轻量级, 不会占用你非常大的内存消耗. 电脑配置不高的首选.并且你可以通过安装很多插件来满足自己开发的需求.
  
  - VSCode 没有很多Android Studio 包括的方便操作, 
  
    比如: 点击启动, 热更新点击等. 而且在某些情况下会出一些问题, 比如:  之前在使用的过程中, 有时候热更新不及时常常看不到效果, 必须重启. 还有在某些情况下没有代码提示, 不够灵活. 
- **`Android Studio` 的优缺点:** 
  
  - 对于进行过Android开发或者使用过WebStorm、IDEA、PHPStorm等的同学, 使用Android 肯定没有问题.  Android Studio 是一个集成开发环境, 不用说, 你需要的功能基本都有. 在VSCode上出现的问题在Android Studio上基本不会出现.  它的一个最大的缺点就是**重** 会占用电脑比较大的资源, 启动也比较慢. 电脑配置不高的话可能出现卡顿. 

**不管是VSCode还是Android 我们在开发Flutter时, 都需要安装两个插件`Flutter` 和`Dart` ** 

- 在VSCode 中直接在Extension 中搜索 `Flutter` 和 `Dart` 安装对应的插件即可. 
- 在Android Studio 中选择`Android Studio` 菜单, 打开偏好设置 , 在选择`Plugins` , 然后搜索 `Dart`  和 `Flutter`  安装对应的插件即可 . 



## 6、创建flutter 工程

到此为止的话, 我们的flutter开发环境就算是搭建完成了.

- **检查flutter 和 Dart 是否有安装成功** 

  ```
  打开 终端, 执行命令:
  flutter --version   
  dart --version
  如果正常显示版本信息, 那么就算安装成功完毕了. 
  ```

  > 我们也可以执行命令:` flutter doctor` 看看我们那些环境是搭建好了哪些没好

- **创建flutter 工程** 

  ```
  cd 目录 
  flutter create helloflutter  // 创建flutter项目
  // 注意, 我们在创建flutter工程时, 名称里面不能有特殊符号和大写
  ```

  > flutter 工程项目创建完成 后, 在终端上会提示:

  ![](images/Snip20200622_3.png) 

  

- 使用命令终端选择模拟器打开flutter 项目, 将我们的flutter运行在指定的模拟器上

  - 这时我们直接`cd  helloflutter`   &&  `flutter run` 一般会报错 (如果没有模拟器的情况下), 执行完命令后我们就可以在模拟器上看到我们的程序已经运行起来了, 如下图:

    ![](images/Snip20200622_5.png)  

- **使用android studio** 打开我们创建的flutter 项目

  - 选择打开已经存在的项目(选择刚才命令终端创建的hello-flutter目录即可)

  - 选择你要启动的设备, 点击 运行 按钮

    ![](images/1592794700061.jpg) 

  // 没完..

  



# 三、Flutter 之Dart介绍和安装

>  若干年后, 你会发现选错公司和选错行业的损失远比选错编程语言更大. 



## 1、认识Dart



Google为Flutter选择 了Dart是既定的事实, 无论你多么的想使用你熟悉 的语言, 比如: java, javaScript 等等来开发flutter, 至少目前是不可以的.



## 2、安装Dart

> 为什么还需要安装Dart呢?
>
> 事实上, 在安装Flutter SDK的时候, 它里面已经内置了Dart, 我们完全可以直接使用flutter去进行Dart的编写并且运行. 
>
> 但是如果你想单独的学习Dart, 并且运行自己的Dart代码, 最好去安装一个Dart SDK



### 1、下载Dart SDK

- 到Dart 的官网, 根据不同的操作系统下载对应的 Dart SDK 即可.

  > 官方网站: https://dart.dev/get-dart

  

### 2、安装Dart SDK

无论是什么操作系统, 安装方式都有2种:

- `通过工具安装`

- `直接下载 SDK, 配置环境变量`

- 通过工具安装

  - windows可以通过Chocolatey
  - macOS 可以通过homebrew

  > 具体的安装操作, 官方网站都有详细的解释

- 直接下载SDK, 配置环境变量

  - 下载地址: https://dart.dev/tools/sdk/archive
  - 我喜欢采用这种方式, 直接, 直观
  - 下载完成后, 将SDK的包放在你喜欢的地方, 根据路径配置环境变量即可.



## 3、VSCode 配置

### 1、VSCode 必要插件的安装

学习Dart 的过程中, 我使用 `VSCode` 作为编辑器

- 一方面编写代码非常的简单, 而且界面风格我也喜欢
- 另一方 面, 我可以在终端看到我编写代码的效果

使用VSCode编写Dart代码需要安装**Dart插件** , 目前我给这个VSCode装了4个插件

- **Dart插件**
- **Flutter插件**
- **Coder  Runner 插件** , 可以点击右上角的按钮让我快速运行代码
- **Atom One Dark Theme** 是我个人比较喜欢的一个主题

> Dart插件和Flutter 插件是为Flutter开发准备的, 是必须要安装的插件.
>
> Coder Runner插件让我们直接点击右上角的按钮即可快速的运行Dart代码, 否则的话我们每次都要使用命令 `dart  xxx.dart   参数1 参数2 ...` 来运行我们的dart 代码. 

 

### 2、VSCode 的使用介绍

Vscode是一个轻量的编译器，所以默认是通过打开文件夹的功能来打开对应的工程。而且下面会列举出最近打开的工程，方便打开用户打开最近打开的工程进行编辑和修改。



## 4、Hello World



接下来, 就可以步入正题了, 学习编程语言, 从祖传的hello world 开始. 

在VSCode 中新建一个`helloworld.dart`文件, 并编写下面的内容

```
main(List<String> args){
	print('hello world');
}
```

然后在终端执行`dart helloworld.dart`  命令, 就能看到 hello world 的结果了.



### 1、Hello world 程序的分析

1、Dart 语言的入口也是main函数, 并且必须显示的进行定义

2、Dart 的入口函数main是没有返回值的.

3、传递给 main函数的命令行参数是通过` List<String>` 完成的

- 从字面 值可以理解 `List` 是Dart 中的集合类型.
- 其中的每一个`String`都表示传递给main的一个参数

4、在Dart 中, 我们定义字符串可以使用单引号, 也可以使用双引号.

> 其实在Dart 中一种有三种方式可以定义字符串, 还有一种 是使用 `""" """` 3个双引号, 使用3个双引号定义的字符串就可以换行多行书写, 这时 单引号和双引号不具备的特点.

5、在Dart 中语句使用分号`;` 结尾,  有很多语言在语句结尾处并不需要分号`;` 比如: swift 和 javaScript , 但是在Dart 中语句结束需要使用`;` 结尾.



# 四、Dart 之变量,数据类型, 函数

## 1、定义变量

### 1、明确声明 (Explicit)

明确声明变量的方式如下: 

```
变量类型 变量名 = 赋值;
```

示例代码:

```
String name = 'zhangsan';
int age = 18;
double height = 1.88;
print(name);
print(age);
print(height);
```

> 注意: 
>
> 定义的变量可以修改值, 但是不能赋值其它类型

```
String content = 'hello dart';
content = 'hello world';
content = 111; // 错误, 将一个int 赋值给String 类型的变量是不允许的
```



### 2、类型推到 (type inference)

类型推到生命变量的方式, 格式如下:

```
var/ dynamic/ const/ final 变量名 = 赋值;
```



#### 1、var 的使用

var 的使用, 示例如下:

- runtimeType 是系统提供的,用于获取变量当前类型

```
var name = 'zhangsan';
print(name.runtimeType); // String
```

var 的错误用法

```
var age = 18; // var 定义的变量一旦赋值, 变量的类型就确定了
age = 'zhangsan';
```



#### 2、dynamic 的使用

如果确实希望这样做, 可以使用 dynamic 来声明变量:

- 但在开发中, 通常情况下不使用 dynamic, 因为类型的变化会带来潜在的危险. 

  ```
  dynamic name = 'zhangsan'; 
  print(name.runtimeType);      // String 
  
  name = 18;
  print(name.runtimeType);      // int 
  ```



#### 3、final & const 的使用

final 和 const 都是用于定义常量的, 也就是定义之后值都不可以修改

```
final name = 'zhangsan';
name = 'wangwu';  // 错误

const age = 18;
age = 20;			// 错误

//final 和 const 修饰的都是常量, 赋初值后就不能在改了
```



**final 和 const** 定义的常量的相同点与区别

- 相同点:

  - final 和 const 定义的都是常量, 一旦赋值后就不能改了.

- 不同点:

  - const 在定义常量时,  赋值的内容必须在编译期就定下来

  - final 在赋值时, 可以动态获取, 比如 赋值一个函数

    ```
    String getName() {
      return 'coderwhy';
    }
    
    main(List<String> args) {
      const myName2 = 'xiaohong'; // 错误
      final name2 = 'xiaofang';   // 错误
    
      // const myName1 = getName(); // 错误
      final name1 = getName();   // 正确, final 常量可以赋值函数
    } 
    ```



#### 4、final 和 const 小案例

- 首先, const定义的常量是不可以赋值为 DateTime.now() 的

- 其次, final一旦被赋值后就有确定的结果, 不会再次赋值

  ```
  // const time = DateTime.now(); 错误写法, const 只能赋值常量
  final time = DateTime.now();
  print(time);
  
  print('-----睡2秒--------');
  // 睡2秒
  sleep(Duration(seconds: 2));
  print(time);
   
   
  2020-06-22 14:17:43.601476
  -----睡2秒--------
  2020-06-22 14:17:43.601476
  ```

  

#### 5、const 放在赋值语句右边, 可以共享对象, 提高性能

```
class Person{
  const Person();
}

main(List<String> args) {
 
 final a = const Person();
 final b = const Person();
 print(identical(a,b)); //  identical 是用来判断两个 引用是否是同一个对象的
 

 final m = Person();
 final n = Person();
 print(identical(m,n)); 
}
```



## 2、数据类型

### 1、数字类型 

#### 1、Dart 中的数字类型(int 和 double)

在Dart 中, 对于数值来说, 我们不关心它是否有符号, 以及数据的宽度和精度等问题. 只要记着整数用`int` ,浮点数用`double` 就行了.  

不过, 要说明一下, 在Dart 中`int` 和 `double` 可以表示的范围不是固定的, 它取决于运行Dart 的平台. 

```
// 整形类型
int age = 18;
int myAge = 0x12;

// 浮点数类型
double height = 1.88;
```

> 补充:
>
> 1、在Dart 中 int 整数 和 double 浮点数 都是num 的子类. 
>
> 2、在Dart 中是不能直接将一个 整数 int 直接赋值给浮点数 double的, 也不能直接将一个 浮点数 double 直接赋值给 整数int的, 整数int 也是不能直接和浮点数参与运算的
>
> 3、但是在实际开发过程中, 如果我们不知道传入的是一个整数还是浮点数, 我们可以使用 num 来接收

```
int sum = 10.0 + 1; // 错误写法
num sum = 10.0 + 1; // 正确
```

#### 2、Dart 中字符串和数字之间的转换

```
// 1. 字符串 转 数字
var one = int.parse('111');
var two = double.parse('12.22');
print('${one}, ${one.runtimeType}');
print('${two}, ${two.runtimeType}');
```



```
// 2. 数字 转 字符串
main(List<String> args) {
 
var num1 = 123;
var num2 = 123.123;
var num1Str = num1.toString();
var num2Str = num2.toString();
var num1StrD = num1.toStringAsFixed(3); // 保留3位小数
var num2StrD = num2.toStringAsFixed(2); // 保留2位小数

print('${num1Str}, ${num1Str.runtimeType}');
print('${num2Str}, ${num2Str.runtimeType}');
print('${num1StrD}, ${num1StrD.runtimeType}');
print('${num2StrD}, ${num2StrD.runtimeType}');
} 

123, String
123.123, String
123.000, String
123.12, String
```



### 2、布尔类型

在Dart 中提供了一个布尔数据类型 bool, 取值为 true 和 false

```
// Dart 中的布尔数据类型
var flag = true;
print('${flag}, ${flag.runtimeType}');
```

> 注意:
>
> 在Dart 中, 布尔类型只有 true 和 false 两个取值, 没有非0即真, 非空即真的说法. 

```
var name = 'zhangsan';

// 错误做法
if(name){
	print(name);
}
```



### 3、字符串类型

#### 1、Dart 中的字符串

Dart中字符串是**UTF-16** 编码的单元序列. 你可以使用单引号或者双引号创建一个字符串(单行字符串). 你也可以使用三个单引号或者三个双引号表示一个多行字符串.

```
// 定义单行字符串 
var s1 = 'hello world';
var s2 = "hello world";
var s3 = 'hello\' world';
var s4 = "hello'world";
```

```
// 定义多行字符串
var msg = """
          今天的天气,
          真不错
          """;
```

#### 2、Dart中字符串和其它变量和表达式拼接

在Dart 中我们可以使用`${表达式或变量}` 这种方式将变量和表达式与字符串进行拼接, 示例如下:

```
var name = 'zhangsan';
var age = 18;
var height = 1.88;

print('name: ${name}, age: ${age}, height: ${height}');
// 等价, 如果表达式是一个单个标识符, 可以省略 {}
print('name: $name, age: $age, height: $height');
```



### 5、集合数据类型

对于集合数据类型, Dart 则内置了三种常用的数据类型: **List/ Map/ Set** , 其中, list 可以这样定义;

#### 1、List 

```
// 定义 List

// 1. 使用类型推导 定义
var letters = ['a', 'b', 'c', 'd'];
print('${letters}, ${letters.runtimeType}');

// 2. 明确指定类型 (泛型)
List<int> nums = [1, 2, 4];
print('${nums}, ${nums.runtimeType}');
```



#### 2、Set

在Dart 中我们可以使用`{}` 来定义Set, Set 和 List 的最大区别:

- Set 集合中的元素是无序的, 而 List 中的元素是有顺序的
- Set 集合中的元素是不重复的, 而List 中的元素是可以重复的

```
// 定义 Set

// 1. 使用类型推导 定义
var letterSet = {'a', 'b', 'c'};
print('${letterSet}, ${letterSet.runtimeType}');

// 2. 明确指定类型 泛型
Set<int> numSet = {1, 2, 3};
print('${numSet}, ${numSet.runtimeType}');
```



#### 3、Map

Map 就是我们常说的字典数据类型, 它的定义是这样的. 

```
// 定义 Map

// 1. 使用类型推导 定义
var infoMap = {'name':'zhangsan', 'age':18, 'height': 1.88};
print('${infoMap}, ${infoMap.runtimeType}');

// 2. 明确指定类型 泛型
Map<String, Object> infoMap2 =  {'name':'zhangsan', 'age':18, 'height': 1.88};
print('${infoMap2}, ${infoMap2.runtimeType}');
```



#### 4、集合的常见操作

了解了这三个集合的定义方式后, 我们来看一些集合最基础的公共操作

- 获取集合的长度

  > 所有的集合都支持获取长度

  ```
  var letters = ['a', 'b', 'c', 'd'];
  print('letters_lenght: ${letters.length}');
  
  var letterSet = {'a', 'b', 'c'};
  print('letterSet_length: ${letterSet.length}');
  
  var infoMap = {'name':'zhangsan', 'age':18, 'height': 1.88};
  print('infoMap_length: ${infoMap.length}');
  ```

- **List, Set**b 添加/ 删除/ 包含 操作

  并且, 对于`List` 来说, 由于它的元素是有序的, 因此它还提供了删除指定索引位置的元素. 

  ```
  // 添加元素
  var letters = ['a', 'b', 'c'];
  letters.add('d');
  print('${letters}, ${letters.runtimeType}');
  
  var numSet = {1,2,3};
  numSet.add(5);
  print('${numSet}, ${numSet.runtimeType}');
  
  
  
  // 删除元素
  bool deleteLettersOk = letters.remove('a');
  print('${deleteLettersOk}, ${letters}, ${letters.runtimeType}');
  // list 删除指定元素后 会返回对应的元素
  print('被删除了:  ${letters.removeAt(0)}');
  
  bool deleteNumSetOk = numSet.remove(2);
  print('${deleteNumSetOk}, ${numSet}, ${numSet.runtimeType}');
  
  
  // 判断包含元素
  print(letters.contains('b'));
  print(numSet.contains(3));
  ```

- Map 的操作

  由于Map 中有 key 和 name, 因此无论是取值还是操作, 都要明确是基于key的, 还是基于value的, 或者是基于 key/value的. 

  ```
  // Map 的常见操作
  
  var infoMap = {'name': 'zhangsan', 'age':18, 'height': 1.88};
  
  // 1. 根据key 获取 value
  print(infoMap['name']); // zhangsan
  
  // 2. 获取所有的 entries
  print('${infoMap.entries}, ${infoMap.entries.runtimeType}');
  
  // 3. 获取所有的 keys
  print('${infoMap.keys}, ${infoMap.keys.runtimeType}');
  
  // 4. 获取所有的 values
  print('${infoMap.values}, ${infoMap.values.runtimeType}');
  
  // 5. 判断是否包含某个key 或者 value 
  print('${infoMap.containsKey('name')}, ${infoMap.containsValue('zhangsan')}');
  
  // 6. 根据key 删除元素,  会返回被删除的key 对应的value
  var deleteObj = infoMap.remove('name');
  print('删除的元素: ${deleteObj}');
  ```

  

## 3、函数

### 1、函数的基本定义

Dart 是一种真正的面向对象的语言, 所以即使函数也是对象, 所以函数也是有类型的, Dart 中函数的类型是**Function** 

这也就意味着, 函数可以作为变量定义 或者 作为其它函数的参数 或者 返回值. 

- 函数的定义方式

```
返回值  函数的名称(参数列表){
	函数体
	return 返回值
}
```

按照上面的定义方式, 我们定义一个完整的函数;

```
int sum(int num1, int num2){
	return num1 + num2;
}
```

> Effective Dart 建议对公共的API, 使用类型注解, 但是如果我们省略掉了类型, 依然可以正常工作的

```
sum(num1, num2){
	return num1 + num2;
}
```

另外, 如果函数中只有一个表达式, name可以使用箭头函数语法 (arrow syntax)

```
sum(num1, num2)=> num1+num2;
```



### 2、函数的参数问题 

> 在Dart 中函数的参数可以分为两类:  必须参数 和 可选参数

#### 1、可选参数

在Dart 中的可选参数有两种: **命名可选参数, 位置可选参数** , 命名可选参数使用 `{}` 扩起来, 位置可选参数使用`[]` 扩起来. 如下:

```
命名可选参数:{param1, param2,...}
位置可选参数:[param1, param2,...]
```

- 命名可选参数示例;

```
main(List<String> args) {

  printInfo('zhangsan');
  printInfo('zhangsan', age: 18);
  printInfo('zhangsan', height: 1.88);
  printInfo('zhangsan', age:16, height: 1.66);
  printInfo('zhangsan', height: 1.66, age:16);
} 
 

printInfo(String name, {int age, double height}){
  print('name: ${name}, age: ${age}, height: ${height}');
}

name: zhangsan, age: null, height: null
name: zhangsan, age: 18, height: null
name: zhangsan, age: null, height: 1.88
name: zhangsan, age: 16, height: 1.66
name: zhangsan, age: 16, height: 1.66
```

- **命名可选参数, 可以指定某个参数是必须传的(使用 @required)** 

  在dart 中是不能使用 @required 的, 只能在Flutter中使用.

- 位置可选参数示例

```
main(List<String> args) {

printInfo('zhangsan');
printInfo('zhangsan', 18); 
printInfo('zhangsan', 16, 1.66); 
} 
 

printInfo(String name, [int age, double height]){
  print('name: ${name}, age: ${age}, height: ${height}');
}

name: zhangsan, age: null, height: null
name: zhangsan, age: 18, height: null
name: zhangsan, age: 16, height: 1.66
```



#### 2、参数默认值

参数可以有默认值, 在不传入的情况下, 使用默认值

> 注意:
>
> 只有可选参数才可以有默认值, 必须参数不能有默认值

```
// 参数的默认值
printInfo(String name, {int age = 18, double height = 1.88}){
  print('name: ${name}, age: ${age}, height: ${height}');
}
```

Dart 中的main函数就是一个接收可选的列表参数作为参数的, 所以在使用 main 函数时, 我们可以传入参数也可以不传参数. 

#### 3、函数是一等公民

在很多语言中, 函数并不能作为一等公民来使用, 比如: java, 这种限制让编程不够灵活, 所以现代的编程语言基本都支持函数作为一等公民来使用, Dart 也支持. 

这就意味着你可以将函数赋值给一个变量, 也可以将函数作为另外一个函数的参数或者返回值来使用

```
main(List<String> args) {
  // 1.将函数赋值给一个变量
  var bar = foo;
  print(bar);

  // 2.将函数作为另一个函数的参数
  test(foo);

  // 3.将函数作为另一个函数的返回值
  var func =getFunc();
  func('kobe');
}

// 1.定义一个函数
foo(String name) {
  print('传入的name:$name');
}

// 2.将函数作为另外一个函数的参数
test(Function func) {
  func('coderwhy');
}

// 3.将函数作为另一个函数的返回值
getFunc() {
  return foo;
}
```



#### 4、匿名函数的使用

大部分我们定义的函数都会有自己的名字, 比如: 前面定义的 foo、test函数等. 

但是, 在某些情况下, 给函数命名太麻烦了, 我们可以使用没有名字的函数, 这种函数我们可以称为匿名函数(anonymous function), 也可以叫 lambda 或者 closure

```
main(List<String> args) {

 // 1.定义数组
  var movies = ['盗梦空间', '星际穿越', '少年派', '大话西游'];

  movies.forEach((item) { 
    print(item);
  });
 
}
```



#### 5、词法作用域

Dart 中的词法有自己明确的作用域范围, 他是根据代码的结构 `{}` 来 决定作用域范围的, 优先使用自己作用域中的变量, 如果没有找到, 则一层层向外查找. 

```
var name = 'global';
main(List<String> args) {
  // var name = 'main';
  void foo() {
    // var name = 'foo';
    print(name);
  }

  foo();
}
```



#### 6、词法闭包 !!!

闭包可以访问其词法范围内的变量, 即使函数在其他地方被使用, 也可以正常访问. 

```
main(List<String> args) {

 makeAdder(num addBy) {
    return (num i) {
      return i + addBy;
    };
  } 

  var adder2 =makeAdder(2);  // 此处相当于 adder2(num a){ return 2 + a; }
  print(adder2(2));  // 结果为 4
 
}
```



### 3、函数的返回值问题

所有函数都返回一个值, 如果没有指定返回值, 则语句返回 null, 隐士附加到函数体.

```
main(List<String> args) { 
  print(test());  // 返回值为 null
  print(test2()); // 返回值为 2
}

test(){
  print('---test');
}

test2(){
  print('---test2');
  return 2;
}
```



# 五、Dart 之运算符、流程控制、类、对象



## 1、常用的运算符

> 这里, 我只列出相对于其他语言比较特殊的运算符, 因为某些运算符太简单了, 比如: + , - , +=, -=.
>
> 在Dart 中相较于其他编程语言, 新增了一些特殊的运算符,  之所以新增了一些运算符这都是为了我们在后续实际开发过程中方便. 



### 1、除法、整除、取模运算

```
var num = 7;
print(num / 3); 	// 除法操作, 结果2.3333..
print(num ~/ 3); 	// 整除操作, 结果2;
print(num % 3); 	// 取模操作, 结果1;
```



### 2、??= 赋值操作

Dart 有一个很多语言都不具备的赋值运算符

- 当变量为 null 时, 使用 ??= 后面的内容进行赋值
- 当变量有值时, 使用自己原来的值, ??= 后面相当于无效(不执行)

```
main(List<String> args) { 
  int age = 12;
  age ??= myAge();  // 如果age 为null时, 会将 myAge() 的结果赋值给 age 
  print(age); 
}

myAge(){
  print('---查询我的年龄---');
  return 2;
}
```



### 3、条件运算符 ?? 

Dart 中包含一直比较特殊的条件运算符: **expr1 ?? Expr2** 

- 如果expr1 是null , 则返回 expr2的结果.

- 如果 expr1 不是null, 则直接使用 expr1的结果

  ```
  var name = "zhangsan";
  var userName = name ?? "无名氏";
  ```



### 4、级联语法 .. 

- 某些时候, 我们希望对一个对象进行连续的操作, 这个时候可以使用级联语法

  ```
  class Person {
    String name;
  
    void run() {
      print("${name} is running");
    }
  
    void eat() {
      print("${name} is eating");
    }
  
    void swim() {
      print("${name} is swimming");
    }
  }
  
  main(List<String> args) {
    final p1 = Person();
    p1.name = 'zhangsan';
    p1.run();
    p1.eat();
    p1.swim();
  
  	// 下面的操作与上面的操作等价
    final p2 = Person()
                ..name = 'zhangsan';
                ..run()
                ..eat()
                ..swim();
  }
  ```



## 2、流程控制

> Dart 中的流程控制和其他语言中的流程控制差不多, 了解下就好

### 1、if 和 else

Dart 中的 if 和 else 的使用方法和其他语言中的if 和 else 是一样的, 唯一的区别是, 在Dart 中没有非空即真, 非0即真的说法, 必须是明确的 布尔类型 bool

```
var name = 'zhangsan';
if(name){ // 错误写法, () 必须是明确的 布尔类型
	print(name);
}

if(name.length > 0){ // 正确做法
	print(name);
}
```



### 2、循环操作

- 基本的for 循环

  ```
  for(var i = 0; i < 10; i++){
  	print(i);
  }
  ```

- for in 遍历List 和 Set 类型

  ```
  var names = ['zhangsan', 'lisi', 'wangwu'];
  for(var name in names){
  	print(name);
  }
  ```

- while 和 do while 和其他语言也是一样的

- break 和 continue 的用法也是一样的

### 3、switch  case

- 普通 switch 使用

  > 注意:
  >
  > 每一个case语句, 默认情况下必须以一个break结尾

  ```
  main(List<String> args){
  	var direction = 'east';
  	switch(direction){
  		case 'east':{
  			print('东');
  		}break;
  		
  		case 'south':{
  			print('南');
  		}break;
  		
  		case 'west':{
  			print('西);
  		}break;
  		
  		case 'north':{
  			print('北');
  		}break;
  		
  		default:{
  			print('其它方向');
  		}
  	}
  }
  ```

## 3、类和对象

> Dart 是一个面向对象的语言, 面向对象中非常重要的概念就是类, 类产生了对象. 
>
> 这一节, 我们就来具体学习类和对象, Dart中类的类有很多其它语言没有的特性, 所以这里我们会花比较长的篇幅来讲解. 

### 1、类的定义

在Dart 中, 定义类使用关键字 **class** 

类通常有两部分组成: 成员(member) 和 方法(method).

定义类的伪代码如下:

```
class 类名{
	类型 成员名;
	
	返回值类型 方法名(参数列表){
		方法体
	}
}
```



### 2、方法内访问属性时, this关键字可以省略

- 编写一个简单的Person类

  ```
  class Person{
  	String name;
  	
  	eat(){
  		print('${name} 在吃东西');
  	}
  }
  ```

  > 注意:
  >
  > 1、我们在方法中使用属性(成员/ 实例变量)时, 并没有 加 this 关键字.
  >
  > 2、在Dart 的开发风格中, 在方法内使用属性时 会 省略 this, 但是当有命名冲突时 this 关键字 不能省略.

### 3、创建实例对象时, new 关键字可以省略

```
main(List<String> args){
	// 1. 完整写法
	var p = new Person()
	p.name = 'zhangsan';
	p.eat();
	
	// 2. 简单写法 (Dart 语法风格推荐)
	var p2 = Person();
	p2.name = 'lisi';
	p2.eat();
	
	// 写法1和写法2 完全等价, 在Dart 语法风格中, 推荐这种写法. 
}
```



### 4、构造方法

#### 1、普通构造方法

我们知道,当通过一个类创建对象时, 会调用这个类的构造方法. 

- 当类中, `没有明确指定构造方法` 时, 将默认拥有一个`无参的构造方法` . 
- 在前面的Person中, 我们就是调用的默认的无参构造方法. 

我们也可以根据自己的需求, 定义自己的构造方法. 

- 当有了自定义的构造方法后, 系统提供的默认的无参的构造方法将会失效.
  - 当然, 你可能希望明确的写一个默认的构造方法, 但是会和我们自己定义的构造方法冲突
  - 这是因为Dart 本身, **不支持函数重载** (方法名相同, 方法签名不同)

```
main(List<String> args) { 

  var p = Person('zhangsan', 18);
  print(p);
}

 
 class Person{
   String name;
   int age;

   Person(String name, int age){
     this.name = name;
     this.age = age;
   }

   @override
   String toString() {
    
    return 'name: ${name}, age: ${age}';
   }
 }
```

另外, 在实现构造方法时, 通常做的事情就是通过 `参数 给 属性` 赋值.

为了简化这一过程,Dart 提供了一种更简洁的 **语法糖形式** 

上面我们的构造方法可以优化成下面的写法:

```
Person(this.name, this.age);

// 等价于下面
Person(String name, int age){
 this.name = name;
 this.age = age;
}
```

#### 2、命名构造方法

前面说了Dart 不支持函数重载, 如果我们重写了构造函数, 原来的构造函数就不能用了(也就是说在Dart 中我们没办法创建相同名字的构造方法), 但是 有时, 我们确实希望实现更多的构造方法, 方便外面使用, 我们应该怎么办呢? 

为了能进在Dart 中定义多个构造方法, 我们可以使用 **命名构造方法** 

```
main(List<String> args) { 

  var p = Person('zhangsan', 18);
  print(p);

  var p1 = Person.withName('有名字');
  print(p1);

  var p2 = Person.withAge(19);
  print(p2);
}

 
 class Person{
   String name;
   int age;

   // 构造方法1
   Person(String name, int age){
     this.name = name;
     this.age = age;
   }

   // 命名构造方法1
   Person.withName(String name){
     this.name = name;
     this.age = 0;
   }

   // 命名构造方法2
   Person.withAge(int age){
     this.name = '无名氏';
     this.age = age;
   }


   @override
   String toString() {
    
    return 'name: ${name}, age: ${age}';
   }
 }
```

> 有了命名构造方法后, 我们就可以提供更多的构造方法供外部调用.

比如: 我们在开发中, 经常将一个Map 转换成一个对象, 可以提供如下的方法:

```
class Person{
	String name;
	int age;
	
	Person(this.name, this.age);
	
	Person.withMap(Map<String, Object>map){
		this.name = map['name'];
		this.age = map['age'];
	}
}

main(List<String> args){
	Person p = Person.withMap({'name':'zhangsan', 'age':18});
	print(p);
}
```



#### 3、初始化列表

```
main(List<String> args) { 

var pt = Point(3, 4);
print(pt); 
  
}

 class Point{
   final num x;
   final num y;
   final num distance;

  // 错误写法
  //  Point(this.x,this.y){
  //    distance = sqrt(x*x + y*y);
  //  }

   // 正确写法, final 修饰的成员变量, 只能在初始化列表中初始化
   Point(this.x, this.y): distance = sqrt(x*x + y*y);

  @override
  String toString() {
    return 'x: ${x}, y: ${y}, distance: ${distance}';
  }
 }
```

> 1、上面这种写法, 我们就称为 初始化列表
>
> 2、final 修饰的成员 只能在初始化列表中进行初始化



#### 4、重定向 构造方法

在某些情况下, 我们希望在一个构造方法中去调用另外一个构造方法, 这个时候可以使用**重定向构造方法**

> 在一个构造方法中, 去调用另外一个构造方法( 注意: 是在冒号后面使用 this 关键字调用)

```
main(List<String> args) { 

  var p = Person.withAge(18);
  print(p);

  var p2 = Person.withName('xiaofang');
  print(p2);

  
}

 
 class Person{
   String name;
   int age;

   Person(this.name, this.age);
   
   // 构造方法调用构造方法 使用 this
   Person.withName(String name):this(name, 0);

   Person.withAge(int age): this('无名氏', age);

   @override
   String toString() {
   
    return 'name: ${name}, age: ${age}';
   }
 }
```



#### 5、常量构造方法

在某些情况下, `传入相同的值` 时, 我们希望`得到的是同一个对象` , 这个时候, 可以使用常量构造方法.

在默认的情况下, 创建对象时, 即使传入相同的参数, 创建出来的也不是同一个对象, 代码如下;

```
main(List<String> args) {
  var p1 = Person('zhangsan');
  var p2 = Person('zhangsan');
  
  // identical 是Dart 中提供的判断两个 变量是否是同一个对象的方法
  print(identical(p1, p2)); // false
}

class Person {
  String name;
  
  Person(this.name);
}
```

**但是, 如果我们将构造方法的前面加 `const` 进行修饰, 那么可以保证同一个参数, 创建出来的对象是相同的.**  

被`const` 修饰的构造方法, 我们称之为 **常量构造方法** , 如下示例:

```
main(List<String> args) {
  
  var p1 = const Person('zhangsan');
  var p2 = const Person('zhangsan');
  
  // identical 是Dart 中提供的判断两个 变量是否是同一个对象的方法
  print(identical(p1, p2)); // false
}

class Person {
  final String name; 
  
  // 1. 被 const 修饰的构造方法, 是常量构造方法
  // 2. 被const 修饰的构造方法, 的成员变量 必须使用 final 修饰
  // 即, 常量构造方法 中的所有成员都必须是常量
  const Person(this.name);
}
```

**常量构造方法的注意点:**

1、拥有常量构造方法的类中, 所有的成员变量必须是final修饰的, 即成员变量必须是常量.

2、为了可以通过常量构造方法, 创建出相同的对象, 不再使用 new 关键字, 而是使用const 关键字.

如果将结果赋值给非 const 修饰的变量, 构造方法前的 const 不能省略.

如果赋值给const 修饰的变量, 构造方法前的可以省略.

如下:

```
var p1 = const Person('zhangsan');
var p2 = const Person('zhangsan');

// 等价于下面
const p1 = Person('zhangsan');
const p2 = Person('zhangsan');
```

#### 6、工厂构造方法

Dart 提供了 **factory 关键字** , 用于通过工厂去获取对象. 

```
main(List<String> args) {
  var p1 = Person('zhangsan');
  var p2 = Person('lisi');
}

class Person {
  String name;  

  static final Map<String, Person> _cache = <String, Person>{};

  Person._internal(this.name);

  factory Person(String name){

    if(_cache.containsKey(name)){
      return _cache[name];
    }
    else{
      final p = Person._internal(name);
      _cache[name] = p;
      return p;
    }
  }
  
}
```



## 4、setter 和 getter

默认情况下, 在Dart 中类定义成属性(成员变量)是可以直接被外界访问的. 

但是, 在某些情况下, 我们希望监控这个 `类的属性` 被访问的过程, 这个时候就要使用到 `setter 和 getter` 

```
main(List<String> args) {
  var p = Person('zhangsan', 18);
  
  // 访问getter 方法
  print(p.getName);
  // 访问 setter 方法
  p.setName = 'xiaohong';
  print(p.getName);

  // 直接访问成员变量
  print(p.name); 
}

class Person {
  String name;  
  int age;

  Person(this.name, this.age);

  // 定义 getter 方法
  String get getName{
    print('------get name');
    return name;
  }
 
  // 定义 setter 方法
 set setName(String name){
   print('------set name');
   this.name = name;
 }
}
```



## 5、类的继承

面向对象的其中一大特性就是继承, 继承不仅仅可以减少代码的冗余量, 也是多态的使用前提. 

- Dart 中的继承使用 extends 关键字, 子类中使用super 来访问父类.

- 父类中的所有成员变量和方法都会被继承. 但是构造方法除外

  ```
  main(List<String> args) {
    var p = Person();
    p.run();
  }
  
  class Animal{
    int age;
    run(){
      print('在ben跑 ing');
    }
  }
  
  class Person extends Animal {
  
  }
  ```

- 子类可以 `拥有自己的成员变量` , 并且可以`对父类的方法进行重写`

  ```
  class Person extends Animal {
    // 子类自己的成员变量
    String name;
  
  	// 子类重写父类的方法
    @override
    run() {
      print('${name}在ben跑 ing');
    }
  }
  ```

- 子类中可以调用父类的初始化构造方法, 对某些属性进行初始化. 

  - 子类的构造方法在执行前, 将隐士的调用父类的`无参默认构造方法`  (没有参数且与类名同名)

  - 如果父类没有`无参默认构造方法`, 则子类的构造方法必须在初始化列表中通过`super` 显示调用父类的某个构造方法.  

    ```
    class Animal {
      int age;
    
      Animal(this.age);
    
      run() {
        print('在奔跑ing');
      }
    }
    
    class Person extends Animal {
      String name;
    
      // 此处必须使用 super 调用父类的构造方法
      Person(String name, int age) : name=name, super(age);
    
      @override
      run() {
        print('$name在奔跑ing');
      }
    
      @override
      String toString() {
        return 'name=$name, age=$age';
      }
    }
    ```

  ## 6、抽象类

  我们知道, 继承是多态的使用前提. 

  所以在定义很多通用的 **调用接口** 时, 我们通常会让调用者**传入父类** , 通过多态来实现更加灵活的调用方式. 

  但是, 父类本身可能并不需要对某些方法进行具体的实现, 所以父类中定义的方法, 我们可以定义为**抽象方法** 

  

- 什么是抽象方法?

  在Dart 中, 没有具体实现的方法(没有方法体的方法), 就是抽象方法. 

  - Dart 中的抽闲方法, 必须存在于抽象类中
  - 抽象类是使用`abstract` 生命的类

  下面的代码中, Shape 类就是一个抽象类, 其中包含一个抽象方法.

  ```
  // 抽象类
  abstract class Shape{
    // 抽象方法
    getArea();
  }
  
  class Circle extends Shape{
    double r;
  
    Circle(this.r);
  
    @override
    getArea() {
     return r * r * 3.14;
    }
  }
  
  class Reactangle extends Shape{
    double w;
    double h;
  
    Reactangle(this.w, this.h);
  
    @override
    getArea() {
      return w * h;
    }
  }
  ```

  > 注意:
  >
  > 1、抽象类不能实例化
  >
  > 2、抽象类中的抽象方法必须被子类实现, 抽象类中已经实现的方法, 可以不被子类重写.

## 6、隐式接口

- Dart 中的接口比较特殊, 没有一个专门的关键字来声明接口

- 默认情况下, 定义的每个类都相当于默认也声明了一个接口, 可以由其它类来实现.

  > Dart 不支持多继承

- 在开发中, 我们通常将用于给别人实现的类声明为抽象类.

  ```
  abstract class Runner{
    run();
  }
  
  abstract class Flyer{
    fly(){
      print('Flyer 都具备飞的能力');
    }
  }
  
  class SuperMan implements Runner, Flyer{
    String name;
  
    @override
    run() {
      print('${name} 在跑步');
    }
  
    // 通过 implements 实现的接口, 类中所有的方法都必须实现
    // 无论原来类中是否已经实现
    @override
    fly() {
      print('${name} 在 飞');
    }
  }
  ```

  > 注意:
  >
  > 通过 implements 实现的接口, 类中所有的方法都必须被 **重写**  无论这个方法在原来的类中是否有被实现. 

  

## 7、Mixin 混入

- 当我们在通过 `implements` 实现某个类的接口时, **类中所有的方法都必须 重写, 无论这个方法在原来类中是否有实现** 

- 但是在某些情况下, 一个类可能希望直接复用之前类的原有实现方案, 怎么做呢?

  - 使用继承吗? 但是在Dart中只支持单继承, 那么意味着你只能复用一个类的实现.Dart 提供另外一种方案: **Mixin 混入的方式** 
  - 在Dart中, 除了可以通过class 关键字来定义一个类外, 也可以通过 Mixin关键字来定义一个类.

- 通过Mixin 定义的类用于被其它类混入使用, 通过with 关键字来进行混入. 

  ```
  main(List<String> args) {
   
   var sMan = SuperMan();
   sMan.run();
   sMan.fly();
   
  }
  
  mixin Runner{
    run(){
      print('在奔跑');
    }
  }
  
  mixin Flyer{
    fly(){
      print('在 飞行');
    }
  }
  
  // 通过 implements 来实现的 接口, 必须重写原来类中所有的方法
  // class SuperMan implements Runner, Flyer
  
  class SuperMan with Runner, Flyer{
  
  }
  ```



## 8、类成员和类方法

前面我们在类中定义的成员和方法都是属于对象级别的, 在开发中我们有时也需要定义类级别的成员和方法. 

在Dart 中, 我们使用`static` 关键字来定义 `类成员 和 类方法`

```
main(List<String> args) {
 
 var stu = Student();
 stu.name = 'zhangsan';
 stu.stuNum = 123;

 // 类成员需要使用 类名来访问
 Student.time = '早上9点';
 // 类方法需要使用类名来访问
 Student.attendClass();

}

class Student{
  String name;
  int stuNum;

  static String time;

  study(){
    print('${name} 在学习');
  }

  static attendClass(){
    print('去上学');
  }

}
```



# 六、枚举、泛型



## 1、枚举

枚举在开发中也非常常见, 枚举也是一种特殊的类型, 通常用于表示固定**常量值** 



### 1、枚举的定义

在Dart 中, 枚举使用关键字 **enum** 来进行定义

```
main(List<String> args) {
 print(Colors.red);
}

enum Colors{
  red,
  green,
  blue
}
```



### 2、枚举的属性

枚举类型中有两个比较常见的属性:

- index: 用于表示每个枚举常量的索引, 从0开始.

- values: 包含每个枚举值得List.

  ```
  main(List<String> args) {
    print(Colors.red.index); 		// 0
    print(Colors.green.index); 	// 1
    print(Colors.blue.index); 	// 2
    
    // [Colors.red, Colors.green, Colors.blue]
    print(Colors.values); // List<Colors>
  }
  
  enum Colors {
    red,
    green,
    blue
  }
  ```

  > 枚举类型的注意事项:
  >
  > 1、不能对枚举进行子类化, 混合 或者 实现枚举
  >
  > 2、不能显示实例化一个枚举



## 2、泛型

为甚么要使用泛型呢?  不做过多解释



### 1、List 和 Map 的泛型

- List 中使用泛型的写法:

  ```
  // 创建 list 的方式
  var names = ['zhangsan', 'lisi', 'wangwu', 234];
  print(names.runtimeType); // List<Object>
  
  // List使用泛型1
  var names2 = <String>['zhangsna', 'lisi', 'wangwu'];
  // List使用泛型2
  List<String> names3 = ['zhangsna', 'wanglu'];
  ```

- Map 使用的泛型写法

  ```
  // 使用Map 的方式
  var info = {'name':'zhangsan', 'age':18};
  
  // Map使用泛型1
  Map<String, String> info1 = {'name':'lisi', 'address':'chengdu'};
  // Map使用泛型2
  var info2 = <String, String>{'name':'lisi', 'address':'chengdu'};
  ```

### 2、类定义的泛型

如果我们需要定义一个类, 用于存储位置信息Location, 但是并不确定使用者希望使用的是int类型, 还是double类型, 甚至是一个字符串, 这是后我们如何来定义这个类呢/

- 一种方式是使用 Object类型, 但是在之后使用时, 非常不方便
- 另一种方案就是使用泛型

Location 类的定义: Object 方式

```
class Location{
	Object x;
	Object y;
}

main(<List<String> args>){
 Location lct = Location(10,30);
 print(lct.x.runtimeType); // Object
 print(lct.x.runtimeType); // Object
}
```



Location 类定义: 泛型方式

```
class Location<T>{
	T x;
	T y;
	Location(this.x, this.y);
}


main(List<String> args){
	Location l1 = Location(10, 20);
	print(l1.x.runtimeType);  // int 
	
	Location l2 = Location('12', '13');
	print(l2.x.runtimeType); // String 
}
```



# 七、Dart 中库的使用





