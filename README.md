 n Flutter 学习

# flutter 开发快捷键

## 1、android studio 

- hot reload 功能, 快捷键  `command + \`

- hot restart功能, 快捷键  `shift + command + \` 

- 创建StatelessWidget 类, 快捷键 `stless` 后回车

- 创建StatefulWidget 类, 快捷键 `stful` 后回车

- 在android Studio 中, 如果你想要快速给已经编写好的widget包裹一个其它的Widget 的话可以使用快捷键 windows:(`alt + enter`), Mac:(`option + enter`)

- 在flutter中查找, 抽象类具体的子类: `option` + `command` + `b` 

- 将StatelessWidget 转换为StatefulWidget的快捷键: `option` + `enter` 	

  > 我们可以发现, 给一个Widget 包裹一个Container 的快捷键 和 将一个StatelessWidget 转换为StatefulWidget的快捷键 也是`option` + `enter` ,  也就是说, 在 android Studio 中, 相同的快捷键作用在不同的地方(代码上)效果是不同的, 这个需要注意一下.

- 关闭当前 激活的文件页面, 快捷键: `command` + `w`

- 格式化快捷键 `command` + `option` + `L` 

- 快速折叠所有代码,快捷键: `command` + `shift`+ `-` 

- 快速展开所有代码,快捷键: `command` + `shift`+ `+` 

- 快速折叠 当前段代码,快捷键: `command`  + `-` 

- 快速展开 当前段代码,快捷键: `command` + `+` 

- 上下挪动代码,快捷键 `option` + `shift` + `上下键` 

- 复制当前行代码快捷键 `command` + `d`

- 当前文件替换内容, 快捷键 `command` + `shift` + `R` 

- 将StateLessWidget 转为 StatefulWidget, 快捷键, `option`   + `enter` 

- 抽取一段代码为一个方法, 快捷键 `command` + `option` + `m` 





## flutter 帮助网站

- 官方文档

  flutter.dev

- 中文网站

  flutter.cn



## 2、设置修改 android studio 快捷键

`android studio` -> `preferences` -> `keymap`  然后在搜索框 搜索对应的快捷键即可.

因为android studio 可以被用作很多语言的开发, 比如: java, kotlin, flutter 等, 因此很有可能同一个快捷键和其它语言冲突, 造成快捷键失效, 因此这时我们要学会解决 android studio 中快捷键冲突的问题.



我们可以通过选中 某一个快捷键, 然后再右键选择 `add keyboard shortcut` 添加一个快捷键, 然后在弹出的快捷键弹窗中看当前快捷键是否有冲突, 示例如下:



![Snip20200813_5](images/Snip20200813_5.png)  ![Snip20200813_6](images/Snip20200813_6.png) 





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



# 七、Dart 中模块(库)的使用



## 1、Dart 模块(库)的介绍

在 Dart 中, 你可以导入一个库来使用它所提供的功能,库的使用可以使代码的重用性得到提高, 并且可以更好的组合代码.**默认情况下, 一个`dart` 文件就是一个模块(或者库文件), 即使你没有使用`library` 关键字声明** 

>  最早的时候我们一般使用`library` 关键字来声明一个模块(或者库文件) 但是现在我们一般没有这样做了. 现在不用`library` 也是可以的. 



## 2、Dart 中库的导入

我们在Dart开发中, 免不了会使用别人提供的库文件, 这时我们就需要将别人写好的`dart` 文件导入到我们的项目中, 这时我们就要使用 **import** 关键字来导入依赖文件, 具体使用情景主要有三种如下: 

- 直接使用 `import '模块路径';` 导入对应的模块并使用
- 使用 `as` 给导入的库取别名, 防止被导入的模块中有类名或者方法名与当前自己编写的dart 代码冲突
- 导出模块时使用关键字`hide` 隐藏部分 或者 关键字 `show` 导出部分
- 使用关键字 `export` 将多个子模块, 组合成一个大的模块, 供外部使用





### 1、直接导入模块(库) 使用

- 我们在使用Dart写代码时, 你会发现一个东西: 我们并没有定义过**List、Map  等等**  , 但是我们是可以直接在我们的代码中使用**List、Map 等类的**且不用导入 ,  说明想**List、Map** 这些类都是Dart系统内部帮我们定义的. 

- 当我们在使用Dart内部帮我们定义的类时, 按道理说我们是需要导入对应的模块的, 但是实际开发中我们并没有导入, 原因很简单, 像**List、Map** 这些类是在dart的核心库里`dart:core`面的. 我们在使用Dart 核心库里面的类时是不需要导入的, 直接使用即可. dart系统默认导入.  

- 当我们在使用非核心库或者其他库时, 我们都需要导入对应的模块并使用, 如下;

  ```
  import 'dart:库名字';
  ```

- 比如: 我们要使用 dart 库中的数据输出就需要导入 `import 'dart:io';` , 如果我们需要使用线程(使用隔离空间) 就需要导入 `import 'dart:isolate';`, 再或者我们使用异步就需要导入 `import 'dart:async';` 或者我们使用数学方的库就需要导入 `import 'dart:math';`,

  以上这些就是我们使用 dart 系统模块(库) 时的导入方式. 

  > 其实, 我们在编写 dart代码时, 有时候并不需要 知道我们要使用的类 在哪个模块里面, 并不需要每次都手动导入, 像vscode 开发工具, 一般都有自动提示导入功能, 这样借助工具我们就可以很容易的导入对应的库文件并使用了. 

  ![Snip20200712_6](images/Snip20200712_6.png) 

  ![Snip20200712_5](images/Snip20200712_5.png) 

  

### 2、使用`as` 关键字给导入的模块取别名

- 通常情况下我们使用 `import '模块名';` 导入对应的模块时时可以直接使用的, 如下图示:

  - 左侧是我们自定义的模块, 模块名为`tool/MathTool.dart` 

  - 右侧是我们书写的 dart 代码, 需要使用到左侧的模块.

    ![Snip20200712_7](images/Snip20200712_7.png) 

- 但是, 在有些时候, 我们导入的模块内的 类名或者方法名 与我们自己书写的类名或者方法名冲突(导入模块内的类名或方法名与外部正在书写的类名或者方法名相同), 这是我们不能直接使用导入的模块, 为了解决这种命名冲突的问题, 我们在导入指定的模块时, 可以使用关键字`as` 给被导入的模块起别名, 避免模块内外命名冲突, 如下图:

  ![Snip20200712_8](images/Snip20200712_8.png) 

  为了解决使用时 模块命名冲突, 我们使用 `as` 关键字给导入的模块取别名

  ![Snip20200712_9](images/Snip20200712_9.png) 



###  3、hide 隐藏部分, show 导出部分

默认情况下我们使用 `import '模块路径';` 或者 `import '模块路径' as 别名` 这两种方式导出的是模块内部所有的方法和属性, 但是有时候我们不希望将模块内的所有方法和属性全部导出, 仅仅是想导出一部分, 这时我们要怎么做呢? 

这时, 我们可以使用关键字, **show** 来导出部分内容, 或者使用关键字**hide** 来隐藏一部分. 具体示例如下;

- 我们定义了一个模块: `tool/MathTool.dart'

  ```
  int sumInt(int a, int b){
    return a + b;
  }
   
  double sumDouble(double a, double b){
    return a + b;
  }
  
  num sumNum(num a, num b){
    return a + b;
  }
  ```

  - **使用关键字 show, 导出模块中的部分内容** 如下:

    ```
    // 只导出模块中的 sumInt 和 sumDouble , 其它的隐藏
    import 'tool/MathTool.dart' show sumInt, sumDouble;
    ```

  - **使用关键字 hide, 隐藏模块中的部分内容** 如下:

    ```
    // 隐藏模块中的部 sumInt 和 sumDouble, 其它的全部导出
    import 'tool/MathTool.dart' hide sumInt, sumDouble;
    ```

    

### 3、export 关键字

有这么一种需求, 我们有个dateFormat工具类, 这个工具类中有很多功能, 而这些功能又是分文件写在不同的dart文件中的, 如果我们在另外的一个dart文件中想要使用 dateFormat 里面的所有功能的话, 我们就需要在使用的地方挨个 导入dateFormat 中其它的模块文件: 如下

```
// dateFormat 目录下有很多的子模块

dateFormat1.dart 文件
// dateFormat1 文件 具体实现

dateFormat2.dart 文件
// dateFormat2 文件 具体实现

dateFormat3.dart 文件
// dateFormat3 文件 具体实现


// 如果我们想要在 下面这个 test.dart 文件中用到 dateFormat1、dateFormat2、dateFormat2我们
// 就需要在test.dart 中挨个导入, 如下;
import 'dateFormat1.dart';
import 'dateFormat2.dart';
import 'dateFormat2.dart';

这样的话就很麻烦
```

为了解决在使用的地方重复的导入很多文件, 我们可以使用 **export** 关键字将一个子模块导入到一个大模块中, 外面在使用时, 只需要导入一个大模块即可, 如下

```
// 新建一个 dateFormat.dart 文件, 将dateFormat 中的其它小的子模块全部导这个大模块文件中

// 以下是dateFormat.dart 中的内容
export 'dateFormat1.dart';
export 'dateFormat2.dart';
export 'dateFormat2.dart';
```

这样我们在外面使用就简单了, 只需要导入一句

```
// 以下是 test.dart 中的文件内容
import 'dateFormat.dart';

// 下面就可以直接使用 dateFormat1 dateFormat2 dateFormat3  中提供的模块内容了
// 不需要再挨个导入
```



## 3、dart 中的私有成员

在Dart中没有其它语言中 `private` `protected` `public`  这些访问控制的关键字, 默认情况下 dart 文件中的所有的方法, 类都是公开的.

但是有时候, 我们在一个dart 文件中编写的有些`方法` `成员` `类` 这些我们确实不希望外部访问, 只是作为当前模块内部访问的, 这时我们可以在对应的表示前面加上下划线`_`, 这样, 带下划线`_` 前缀的`方法` `成员` `类` 就只能在当前模块(当前dart文件内)访问了, 外部无法访问

![Snip20200713_12](images/Snip20200713_12.png)



## 4、Dart 中第三方模块的使用

在dart中使用第三方的库和node中使用第三方的库很像.

**Flutter 或者 dart 的第三方库都在`pub.dev` 这地址** .

在Flutter 或者 dart 开发中想要找 第三方库, 直接在 `pub.dev` 这个地址下搜索即可. 搜索到对应的第三方库后, 你会看到对应的安装下载以及使用方法和步骤.



想要在 Dart 中使用第三方的 dart 库, 主要有以下几个步骤:

- 1、在项目中创建一个`pubspec.yaml` 文件, 并在文件描述第三方库信息

  > 其实, `pubspec.yaml` 这个文件就是dart开发中用来管理第三方库的一个配置管理文件.(一个第三方库描述文件), 如下图:

![Snip20200713_13](images/Snip20200713_13.png) 

- 使用 命令终端下载第三方库, 以下命令二选一

  - `pub get` 命令
  - `flutter pub get` 命令

- 导入第三方库到你的Dart 中

  ```
  import 'package:http/http.dart';
  ```

- 在 Dart 文件中使用第三方库即可





# 八、Flutter 开发





## 1、flutter项目的创建

我们在开发时创建flutter项目工程主要有两种方式:

- 通过开发工具创建 

  ![Snip20200713_15](images/Snip20200713_15.png) 

  一般来说, 我很少使用工具来创建flutter项目, 因为使用工具会生成一些额外和工具相关的莫名其妙的文件等, 导致项目不是很纯洁, 所以我在开发flutter时, 一般选择使用命令行来创建项目. 

  

- 通过终端命令创建

  通过命令创建flutter项目非常的简单, 在终端输入命令即可.

  ```
  // 错误命令 flutter create helloWorld
  flutter create hello_flutter			// 正确命令
  ```
  
  > **注意**:
  >
  > 1、flutter 项目的名称不要包含特殊符号, 另外不支持驼峰命名, 也可以理解为flutter项目名称不支持特殊符号和大写字母.
  >
  > 2、使用终端命令创建好flutter命令后, 使用对应的工具直接打开即可(vscode 或者 android studio)
  >
  > 3、顺便提示一下, 在创建flutter项目时好像要下载一些文件, 因此要保证电脑能上网.



## 2、打开flutter项目

打开flutter项目, 主要有两种方式:

- 使用命令终端运行flutter项目
- 使用开发工具打开flutter项目

### 1、使用终端命令打开flutter项目

其实, 当我们在使用终端命令创建flutter项目完成后, 在终端上已经提示了, 使用终端命令运行我们的项目, 这个完全没问题

```
// 使用终端命令 运行 flutter 项目
cd flutter项目目录
flutter run 
```

> 补充:
>
> 如果在使用终端命令 运行 flutter项目时提示: `No supported devices connected.` 说明当前没有设备, 打开电脑模拟器后再执行 `flutter run` 命令即可正常运行flutter项目

- 打开iOS模拟器

  打开Xcode -> 选择Xcode -> Open Developer Tool -> Simulator

  - 如果想要切换模拟器

    选择模拟器 -> HardWare -> Device -> 选择对应版本的模拟器即可



### 2、使用开发工具打开flutter项目

一般来说, 我们可以使用 `vscode` 和 `android studio` 开发工具来打开flutter项目. 

我一般使用`android studio` 打开flutter项目多一点, 所以下面我们说一下使用`android studio` 打开flutter的流程

- 启动 `android studio`

- 选择`Open an existsinng Android Studio project` 

  然后跟着指示选择对应的flutter的工程目录即可打开flutter项目

  ![Snip20200714_16](images/Snip20200714_16.png) 
  
  > 补充:
  >
  > 只要是使用工具打开`flutter` 项目, 不论是`vscode` 还是`android studio` . 在使用之前必须要安装`flutter 和 dart` 插件, 这个是前提条件, 如何安装, 百度一下即可.
  >
  > 如果不装这两个插件是没有办法打开和开发flutter的. 



## 3、flutter 工程目录介绍

![Snip20200729_1](images/Snip20200729_1.png) 

- `.dart_tool` 目录主要存储的是我们Flutter项目中Dart 依赖的一些第三方库信息. 不需要手动配置和修改
- `.idea` 目录, 因为Android Studio 是google 基于`IDEA` 开发的,因此项目中默认有这个`.idea` 目录, 我们不用管它.
- `android` 目录就是我们的android项目的代码
- `ios`目录就是我们的ios项目的代码

- `lib` 目录就是我们非常重要的flutter源代码的目录, 以后我们开发flutter所有的代码都写在这个`lib` 目录里面. 
- `test` 目录就是我们做测试的目录
- `.gitignore` 是做git项目管理的忽略文件, 如果我们在做git提交时如果不想提交, 就在这个文件里配置就可以了
- `.metadata` 文件, 是对我们的flutter 项目版本做记录的, 不需要手动修改. 
- `pubspec.yaml` 是用来管理第三库依赖的描述文件, 用来说明我们的项目需要安装怎样的第三方依赖库. 后续开发过程中会用到
- `.packages` 和 `pubspec.lock` 文件是我们安装第三方依赖后自动生成的第三方描述文件, 其中`pubspec.lock` 主要记录的是已经安装的第三方依赖的具体版本信息, 保证项目多次安装时, 安装同样版本的依赖.
- `README.md` 是用来写一些项目的描述信息. 

> 整个flutter项目的目录结构, 其实还以包含很多其它的内容, 目前先介绍这些常用的目录和文件, 其余的后续再补充. 



## 4、使用android studio 运行flutter项目

我们在使用 android studio 运行flutter项目时, 主要分为三步:

1、选择并打开指定的模拟器(ios  或 android 模拟器)

2、选择一个已经打开的模拟器(iOS 或 android)作为启动模拟器

3、选择run图标运行flutter程序

![Snip20200715_2](images/Snip20200715_2.png)  



![Snip20200715_5](images/Snip20200715_5.png) 



![Snip20200715_6](images/Snip20200715_6.png) 



## 5、flutter 项目的启动

在flutter开发中项目的启动主要分为两种: **冷启动和热启动** .

 具体呢又可以划分为三种操作: 

**冷启动、热重启、热重载** 



### 1、flutter冷启动和热启动

- **冷启动** 

  所谓冷启动, 就是这个flutter项目完全没有启动,从0开始启动, 这个过程我们就称为冷启动. 	冷启动意味着, 我们整个flutter的框架包括我们自己写的flutter代码全部都是从0开始启动的. 这个过程非常的慢.根据你电脑的配置不同启动花销的时间也不同, 可能1~5分钟不等. 

- **热启动**

  当我们的flutter项目已经启动了, 我们修改了一些代码, 想要立马看到修改的效果, 一种方式是结束当前的程序运行后再冷启动, 另一种就是直接热启动



### 2、flutter 冷启动 热重启 热重载

在我们使用`vscode` 或者 `android studio` 开发flutter项目时, 经常会用到 **hot restart 和 hot reload** 这两个功能. 

![Snip20200715_8](images/Snip20200715_8.png) 

- hot reload 功能, 快捷键  `command + \`
- hot restart功能, 快捷键 `shift + command + \` 

**下面我们来简单的介绍一下, 热重载(hot reload)  和 热重启(hot restart) 他们之间的关系和区别** 

其实我们在运行一个flutter项目的时候有三种方式:

1、冷启动

- 当前的项目完全没有启动, 从0开始启动. 所有的flutter框架的代码和我们自己写的代码都是从0开始启动加载的. 耗时长.

2、热重启 (快捷键 shift + command + `\`)

- 当我们执行热重启后, flutter会重新运行我们整个 flutter app 的. 换句话说执行热重启后我们的flutter app 是从0开始运行的. 热重启比冷启动执行时间要短的多.

  > **注意:** 
  >
  > 虽然, 冷启动和热重启, 整个flutter app 都是从0开始运行的, 但是不要把他们搞混了, 冷启动是完完全全的从0开始启动app, 而 热重启是对已经启动的app 进行从0运行, 没有运行过得app 是不能直接热重启的. 

3、热重载 (快捷键 command + `\`)

- hot  reload 热重载, 最主要是执行build 方法.  如果修改的内容不是在 `build` 方法里面, 这时热重载是不生效的.  换句话说, 当我们按下 command + `\` 时, flutter 会重新制定build 方法, 如果我们修改的内容在build 方法里面, 那么被修改的内容就会被呈现, 否则没反应.

### 3、冷启动、热重启、热重载总结

- flutter app完全没有启动过, 需要启动就使用冷启动. 
- flutter app 已经启动了, 想要让app 再次从0开始启动一遍,可以选则再次冷启动, 也可以选择热重启, 如果希望快一点看到效果就选择热重启否则就冷启动.
- 如果flutter app 已经运行, 我们修改了 build 方法内的内容, 想要快速看到效果就可以选择热重载. 



## 6、第一个flutter 项目

![Snip20200729_2](images/Snip20200729_2.png) 

```
import 'package:flutter/material.dart';

main(List<String> args){
  runApp(
      Center(
        child: Text(
          'hello flutter',
          textDirection:TextDirection.ltr,
          style: TextStyle(
              fontSize: 50,
              // 注意: 此处是Colors 不是Color. 
              // 比如: orange 就是Colors 中的一个静态属性
              color: Colors.orange,
              backgroundColor:Colors.red
          ),
        ),
      )
  );
}
```

> ```v
> 1. dart 代码的入口 是main函数, main函数是整个Dart 应用程序的入口
> 2. main 函数可以没有参数, 也可以有参数, 参数是一个 List 类型, eg: List<String> args
> 3. flutter 在启动后, 我们应当首先调用 runApp() 这个全局函数
> 	3.1. 我们在 main 函数中运行 runApp() 全局函数时, 一般我们选择的是 'package:flutter/material.dart' 模块中的 runApp,不要选择错了
> 4. 在flutter 中万物皆 widget, 所有的东西都是widget
> 5. 在flutter 中, Widget不能直接使用, 因为Widget是一个抽象类.
> ```

到这里的话, 我们最简单的flutter 项目就开发完了.



# 九、material设计风格



## 1、什么是material 风格

- material 是google公司推行的一套`设计风格` , 或者叫做` 设计语言` `设计规范` 等. 
- 在material 里面有非常多的设计规范, 比如: `颜色` 、`文字的排版`、`填充` 等. 
- 在flutter中, 高度集成了`material风格的 widget`
- 在我们的应用中, 我们可以直接使用这些widget来创建我们的应用. (后面我们会用到很多, 里面有些关键的widget我们是必须掌握才能开发flutter的)

**补充:**

widget 到底是什么东西?

- 我们学习flutter, 从一开始就可以有一个基本的认识: **flutter中万物皆是widget**
- 在我们iOS或者Android开发中, 我们界面有很多种类的划分: 应用(Application)、视图控制器(viewController)、活动(Activity)、视图(View)、按钮(button)等等
- 但是在Flutter开发中, 这些都是不同类型的 widget而已.
- 也就是说, 我们整个应用内程序中, **所看到的内容** 几乎都是widget, 甚至**内边距设置** 我们也要使用一个叫`PaddingWidget` 来设置.



## 2、第一个material App

```
import 'package:flutter/material.dart';

main(List<String> args){
  print('----程序启动了');

  runApp(
    MaterialApp(
      home: Center(
        child: Text(
          'hello material app',
          style: TextStyle(
            color: Colors.white,
            fontSize: 20,
            backgroundColor: Colors.red
          ),
        ),
      ),
    )
  );
}
```

> ```
> /**
>  * 通常我们开发 flutter项目时, 整个流程是这样
>  * 1. 先在 main 方法中运行 runApp 方法.
>  * 2. 在runApp 方法中, 我们直接传入一个 MaterialApp , 就是告诉程序我们要运行一个 material风格的 app
>  * 3. 在 MaterialApp 中有个home参数, 直接传入我们要显示的widget 即可
>  * 4. 这样我们的 material 风格的app 就运行了
>  * 5. 在material App 中因为已近设置了 方向, 因此后续我们 就不用再单独在 子widget 中在设置排版方向了
>  *
>  * 总结:
>  * 我们使用MaterialApp 包裹我们所有的子widget, 或则说我们在 runApp 中运行MaterialApp 其实就是告诉
>  * 系统, 我们整个app 都采用material 风格开发, 后面我们很多东西就沿用material 风格了, 就不需要再单独设置.
>  */
> ```

![materialApp01](images/materialApp01.png)  

## 3、第二个Material 风格的 app

```
import 'package:flutter/material.dart';

main(List<String> args){

  runApp(
      MaterialApp(
        debugShowCheckedModeBanner: false ,     // 不显示右上角的debug 图标
        home: Scaffold(
          appBar:AppBar(
            title: Text(
              '我是标题',
              style: TextStyle(
                  color: Colors.white,
                  fontSize: 20
              ),
            ),
            backgroundColor: Colors.lightBlue,
          ) ,
          body: Center(
            child: Text(
              'material scaffold app',
              style: TextStyle(
                  color: Colors.white,
                  backgroundColor: Colors.cyan,
                  fontSize: 30
              ),
            ),
          ),
        ),
      )
  );

}
```

> ```
> /**
>  * Scaffold  翻译过来的话就是脚手架
>  *
>  * 1. 脚手架一个主要的功能就是帮助我们快速的搭建页面
>  * 2. 在Scaffold 中, 我们最主要的就是传入2个参数,  appBar 和 body
>  * 其中appBar 就是类似于我们iOS中的导航 nav, 而 body 就有点类似于我们controller 中
>  * 要显示的控制器的view
>  * 3. 其中 appBar 是一个需要继承自PreferredSizeWidget 的widget, 但是PreferredSizeWidget 是一个
>  * 抽象类, 不能实例化, 一般我们使用它的子类 AppBar 或者  TabBar
>  *
>  *
>  */
> ```

![](images/scaffoldApp.png) 







## 4、Material app 重构

这个章节, 我们主要是要对我们之前写的Material App 进行结构上的重构, 让我们写的代码更结构化, 这样便于我们后续的维护和开发, 以及各个版本迭代

-  app 抽取

  ```
  import 'package:flutter/material.dart';
  main(List<String> args){
    runApp(YRApp());
  }
  ```

  从上面来看, 我们把整个app 都抽到一个叫 YRApp 的类里面, 这样 main 方法就清晰了, 里面只需要 runApp 就行了, 具体 run 的是那个app , 我们只需要按照规范把YRApp 在其他地方写好就行了, main 不需要再关心其它逻辑, 这样职责就清晰了, main 方法只需要 runApp 就好

- YRHomePage 抽取

  ```
  class YRHomepage extends StatelessWidget{
    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: homePageAppBar() ,
        body: YRHomePageBody()
      );
  
    }
  
    AppBar homePageAppBar(){
      return AppBar(
        title: Text(
          '我是标题',
          style: TextStyle(
              color: Colors.white,
              fontSize: 20
          ),
        ),
        backgroundColor: Colors.green,
      );
    }
  }
  ```

- YRHomePageBody 抽取

  ```
  class YRHomePageBody extends StatelessWidget{
    @override
    Widget build(BuildContext context) {
      return Center(
        child: Text(
          'YRHomeage',
          style: TextStyle(
              color: Colors.white,
              backgroundColor: Colors.cyan,
              fontSize: 30
          ),
        ),
      );
    }
  }
  ```

  



​	



# 十、StatelessWidget & StatefulWidget



## 1、StatelessWidget 介绍

StatelessWidget 通常被称作一种没有状态state(也可以理解为data) 需要维护的Widget

- 它们的数据通常是直接写死的(放在widget中的数据, 必须被定义为final), 为什么定义在StatelessWidget 中的数据必须定义为final, 我们在后面的章节中会介绍.
- StatelessWidget中的数据通常是从父widget(parent widget) 中传入的, 而且一旦传入就不能被改变了. 
- StatelessWidget 中的数据也可以从InheritedWidget 中获取, 这个在后面也会将

## 2、创建继承自StatelessWidget 的widget

很简单, 一般来说只需两步:

- 定义一个类, 继承自StatelessWidget

- 重写StatelessWidget 的 build 方法, 返回自己想要显示的widget 即可. 

  ```
  class YRHomePage extends StatelessWidget{
  
    @override
    Widget build(BuildContext context) {
      
      return Center(
        child: Text(
          '自定义widget, 继承自StatelessWidget',
          style: TextStyle(
              color: Colors.white,
              backgroundColor: Colors.red
          ),
        ),
      );
    }
  }
  ```

## 3、build 方法的解释



- 当flutter 在拿到我们自己创建的继承自StatelessWidget的类创建实例时就会调用它里面重写的 build 方法, 渲染里面返回的widget

- 我们需要在 build 方法中告诉flutter, 我们自己定义的widget 希望渲染什么元素, 比如一个Text Widget 等等. 

- StatelessWidget 是没有办法主动执行 build方法的, 当我们的数据发生变化的时候, build方法会被重新调用

  > 在我们的flutter开发中, 一般来说, 我们是不会且也不会主动的调用widget 中的build 方法的, 一般都是用来让系统自己调用的. 



## 4、build 方法在什么情况下被执行



- 当我们的StatelessWidget是第一次插入到Widget 树中时, 也就是第一次被创建时
- 当我们的父Widget (parent widget) 发生改变的时候, 子Widget 会被重新构建
- 如果我们的Widget依赖InheritedWidget 的数据, InheritedWidget 中的数据发生变化的时候会被调用. 

> 其实,当我们在 执行 热重载的时候, build 方法就会被再次调用, 重新绘制页面, 这也就是为甚么说, hot reload 时, 只有build 中的修改会被改变. 



## 5、StatelessWidget 中的@immutable 注解

前面我们将我StatelessWidget 是没有状态的, 现在我们来说一下StatelessWidget 中的@immutable 注解. 

- 首先, 注解这个东西是flutter中才有的, 在Dart 中是没有这一说法, `注解`这个东西涉及到Dart的元编程, 我们这里不讲

- 在flutter官方中是这样定义 Widget类的, 如下图:

  ![Snip20200805_2](images/Snip20200805_2.png) 

  注意到没有, 在前面有个 `@immutable` 注解

- 当我们在被`@immutable` 注解 注解的类或是继承自被`@immutable` 注解的类中定义非`final` 修饰的属性(成员变量)时, 代码就会报错, 提示如下错误:

  ![Snip20200805_4](images/Snip20200805_4.png) 

  这个就是官方给我们的错误提示, 意思就是说被@immutable注解或者是继承自被@immutable 注解的类, 所有的成员变量必须是 final 的, 即成员变量必须是常量,  因为是常量, 所以成员属性的值一旦确定就不能变, 这也就是为什么, 我们说StatelessWidget 是没有状态的不能修改状态的原因, 因为属性压根不能变, 是常量
  
- 官方对于 `@immutable` 有做解释, 具体看这里: https://api.flutter.dev/flutter/meta/immutable-constant.html





## 6、flutter 中Widget 知识补充那个

- 在flutter开发中所有的Widget都是不能定义状态的, 因为 Widget 类是被`@immutable` 注解的.

- 因此不论是继承自StatelessWidget 还是继承自StatefullWidget 都是不能定义状态的, 这个结论很重要, 很重要.

- 以下的写法都是错误的

  ```
  class YRLessWidget extends StatelessWidget{
    String name; // 此处错误, 必须是final 修饰的变量
  }
  
  ```

  ```
  class YRFullWidget extends StatefulWidget{
    String name; // 错误写法, 此处必须是final 修饰
  }
  ```



## 7、同意协议demo

```
import 'package:flutter/material.dart';

main(List<String> args){
  runApp(YRApp());
}

class YRApp extends StatelessWidget{
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
    	// 不显示右上角的debug 图标
      debugShowCheckedModeBanner: false ,     
      home: YRHomepage()
    );
  }
}

class YRHomepage extends StatelessWidget{
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: homePageAppBar() ,
      body: YRHomePageBody()
    ); 
  }

  AppBar homePageAppBar(){
    return AppBar(
      title: Text(
        '我是标题',
        style: TextStyle(
            color: Colors.white,
            fontSize: 20
        ),
      ),
      backgroundColor: Colors.green,
    );
  }
}

class YRHomePageBody extends StatefulWidget{

  @override
  State<StatefulWidget> createState() {
    // 创建一个我们自己实现的 State, YRHomePageBodyState
    return YRHomePageBodyState();
  }
}

class YRHomePageBodyState extends State<YRHomePageBody>{

  var  flag = true;
  @override
  Widget build(BuildContext context) {

    return Center(
      child: Row(
        mainAxisAlignment: MainAxisAlignment.center,
        children: <Widget>[
          Checkbox(
              value: flag,
              onChanged: (value){
                setState(() {
                  flag = value;
                });
              }),
          Text(
            "同意协议",
            style: TextStyle(
              color: Colors.white,
              backgroundColor: Colors.cyan,
              fontSize: 40
            ),
          )

        ],
      ),
    );
  }
}
```

![](images/tongyixiyi.png) 

> **说明**
>
> 在Material App 中, 一个Scaffold 就相当于是我们iOS中的一个UIViewController, 在Scaffold 中主要有 appBar 和 body, 其中 appBar 就相当于是我们的导航条 navBar, 而 body 就相当于是UIViewController 中的View 主要用来展示页面内容. 		 
>
> 也类似于Android 中的Activity 



## 8、StatefullWidget 回顾

我们在自定义继承自StatefullWidget 类的类的时候发现, 其实, 我们需要定义两个类, 一个类继承自StatefullWidget 一个类继自State

其中, 继承自State的类是用来管理记录状态的, 因为继承自Widget的类是没有状态的. 		

```
class HomePage extends StatefulWidget{
  @override
  State<StatefulWidget> createState() {
    // TODO: implement createState
    return HomePageState();
  }
}

class HomePageState extends State<HomePage>{
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return Center(
      child: Text(
        """ 自定义继承自StatefulWidget 的类需要自己创建2个类
        一个是继承自 StatefulWidget 的类
        一个是继承自 State的类, 继承自State的类用来记录状态 """
      ) ,
    );
  }
}
```





## 9、StatelessWidget 简单案例



- 最终案例效果

  ![](images/column1.png)  ![](images/listview1.png) 

  ```
  示例代码1:
  import 'package:flutter/material.dart';
  main(){
    runApp(YRStatelessApp());
  }
  
  class YRStatelessApp extends StatelessWidget{
    @override
    Widget build(BuildContext context) {
  
      return MaterialApp(
        debugShowCheckedModeBanner: true,
        home: YRStatelessAppHome(),
      );
    }
  }
  
  
  class YRStatelessAppHome extends StatelessWidget{
    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(
          title: Text('我是标题'),
        ),
        body: ProductPage(),
      ) ;
    }
  }
  
  class ProductPage extends StatelessWidget{
    final String imageUrl1 = "https://tva1.sinaimg.cn/large/006y8mN6gy1g72j6nk1d4j30u00k0n0j.jpg";
    final String imageUrl2 = "https://tva1.sinaimg.cn/large/006y8mN6gy1g72imm9u5zj30u00k0adf.jpg";
    final String imageUrl3 = "https://tva1.sinaimg.cn/large/006y8mN6gy1g72imqlouhj30u00k00v0.jpg";
    @override
    Widget build(BuildContext context) {
      return Column(
        children: <Widget>[
          ProductPagetem('apple1',
              'apple1 描述apple1 描述apple1 描述apple1',
              imageUrl1
          ),
          ProductPagetem('apple2',
              'apple2 描述apple2 apple2 描述apple2',
              imageUrl2
          ),
          ProductPagetem('apple1dsf',
              'apple3 描述apple3 apple2 描述apple3',
              imageUrl3
          ),
  
        ],
      );
    }
  }
  
  
  class  ProductPagetem extends StatelessWidget{
  
    final String title;
    final String desc;
    final String imageUrl;
  
    final titleStyle = TextStyle(color: Colors.orange, fontSize: 30);
    final descStyle = TextStyle(color: Colors.green, fontSize: 20);
  
    ProductPagetem(
        this.title,
        this.desc,
        this.imageUrl
        );
  
    @override
    Widget build(BuildContext context) {
      return  Column(
        children: <Widget>[
          Text(
            this.title,
            style: titleStyle,
          ),
          SizedBox( // 使用SizeBox 可以做垂直和水平方向上的间距
              height: 8
          ),
          Text(
            this.desc,
            style: descStyle,
          ),
          Image.network(this.imageUrl)
        ],
      );
    }
  }
  ```

  

  ```
  // 示例代码2: 
  import 'package:flutter/material.dart';
  main(){
    runApp(YRStatelessApp());
  }
  
  class YRStatelessApp extends StatelessWidget{
    @override
    Widget build(BuildContext context) {
  
      return MaterialApp(
        debugShowCheckedModeBanner: true,
        home: YRStatelessAppHome(),
      );
    }
  }
  
  
  class YRStatelessAppHome extends StatelessWidget{
    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(
          title: Text('我是标题'),
        ),
        body: ProductPage(),
      ) ;
    }
  }
  
  class ProductPage extends StatelessWidget{
    final String imageUrl1 = "https://tva1.sinaimg.cn/large/006y8mN6gy1g72j6nk1d4j30u00k0n0j.jpg";
    final String imageUrl2 = "https://tva1.sinaimg.cn/large/006y8mN6gy1g72imm9u5zj30u00k0adf.jpg";
    final String imageUrl3 = "https://tva1.sinaimg.cn/large/006y8mN6gy1g72imqlouhj30u00k00v0.jpg";
    @override
    Widget build(BuildContext context) {
      return ListView(
        children: <Widget>[
          ProductPagetem('apple1',
              'apple1 描述apple1 描述apple1 描述apple1',
              imageUrl1
          ),
          ProductPagetem('apple2',
              'apple2 描述apple2 apple2 描述apple2',
              imageUrl2
          ),
          ProductPagetem('apple1dsf',
              'apple3 描述apple3 apple2 描述apple3',
              imageUrl3
          ),
  
        ],
      );
    }
  }
  
  
  class  ProductPagetem extends StatelessWidget{
  
    final String title;
    final String desc;
    final String imageUrl;
  
    final titleStyle = TextStyle(color: Colors.orange, fontSize: 30);
    final descStyle = TextStyle(color: Colors.green, fontSize: 20);
  
    ProductPagetem(
        this.title,
        this.desc,
        this.imageUrl
        );
  
    @override
    Widget build(BuildContext context) {
      return  Column(
        children: <Widget>[
          Text(
            this.title,
            style: titleStyle,
          ),
          SizedBox( // 使用SizeBox 可以做垂直和水平方向上的间距
              height: 8
          ),
          Text(
            this.desc,
            style: descStyle,
          ),
          Image.network(this.imageUrl)
        ],
      );
    }
  }
  ```



### 示例分析:

**为什么示例一的代码 会出现黄条的页面呢?**

- 在flutter的布局中 子widget只知道自己的大小, 然后父widget对子widget显示的位置进行调整. 而父widget 发现子widget 超出了自己的安全区域, 到时就会报黄条的错误, 说子widget 越界了.` relayoutboundary 错误`
- 在flutter开发中, 只要是你的内容, 超出了父widget可以显示的区域, 且你没有将超出元素的父元素设置为可滚动的元素, 那么就会报比较经典的,, 也就是说flutter中的内容只能在安全区域显示.
- Column 这个Widget是不可以滚动的, 我们可以使用ListView 这个Widget 代替,ListView 也是一个Widget, 当ListView 这个Widget内的内容超出了自己的范围, 那么ListView 的内容就是可以滚动的了



## 10、StatelessWidget 案例二

设置Widget之间的间距

设置Widget的内边距

设置Widget的垂直对齐方式, 以及水平对齐方式

### 1、设置Widget 之间的间距

> 使用SizeBox 这个Widget 可以设置上下Widget之间的间距, 也可以设置左右Widget 之间的间距

- 在iOS 开发中, 我们设置上下两个View之间的间距, 调整View的Y值即可, 在安卓或者前端开发中设置上下两个元素之间的间距, 我们设置Margin即可, 但是在我们的flutter开发中, 设置上下两个Widget 之间的间距时与iOS 、安卓、前端中的方式都不一样 , 在flutter中设置两个Widget之间的间距有很多种方法, 大概有4~5中, 但是这里我们可以使用在两个Widget之间插入一个Widget来实现. 
- 这里我们介绍,使用SizeBox这个widget 来实现连个Widget之间的间距

```
class ProductItem extends StatelessWidget{
  final String title;
  final String desc;
  final String imageUrl;
  
  ProductItem(this.title, this.desc, this.imageUrl);
  
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return Column(
      children: <Widget>[
        Text(this.title),
        SizedBox(height: 10),  // 设置一个上下为10 的间距
        Text(this.desc),
        SizedBox(height: 10),  // 设置一个上下为10 的间距
        Image.network(this.imageUrl)
      ],
    );
  }
}
```



### 2、设置Widget的边框和内边距

> 在flutter 中, 我们可以通过Container 这个Widget来给其它的Widget设置边框和内边距. 
>
> 在flutter开发中, 我们可以通过给Container这个Widget来给其它的Widget设置内边距

- 在flutter开发中, 我们不直接像在iOS 或者安卓 或者前端中直接给设置边框和内边距. 
- 在flutter开发中我们可以给其它的Widget增加一个Container容器Widget, 将其它Widget包裹在理面, 然后通过Container 的decoration 属性给Widget设置边框和内边距
- 在flutter开发中, 如果我们想要给一个Widget增加内边距, 这时我们就可以考虑使用一个Container将对应的Widget包裹, 然后设置Container 的Padding 属性即可.

> 说明:
>
> 1、Container 这个Widget中的Decoration 属性是装饰的意思, 是一个`Decoration` 类型(抽象类), 不能直接使用, 一般我们使用它的子类`BoxDecoration` 来设置边框以及背景色等, 
>
> 2、需要注意的是, 其实在Container中除了可以通过 `decoration ` 属性来装饰我们的Container, 也可以直接使用哪个Container中的color属性来直接设置Container的背景色, 但是 `color` 属性和 `decoration` 属性只能选择一个不能同时用
>
> 3、Container 中的`padding` 属性虽然可以用来设置内边距, 但是因为`padding` 属性是`EdgeInsetsGeometry` 类型(抽象类) , 不能直接使用呢, 一般我们使用哪个`EdgeInsets` 子类



```
class  ProductItem extends StatelessWidget{

  final String title;
  final String desc;
  final String imageUrl;
  
  final titleStyle = TextStyle(color: Colors.orange, fontSize: 30);
  final descStyle = TextStyle(color: Colors.green, fontSize: 20);

  ProductItem(this.title, this.desc, this.imageUrl);

  @override
  Widget build(BuildContext context) {
    return  Container(

      decoration: BoxDecoration(
        border: Border.all(
          color: Colors.green,
          width: 10
        ),
        color: Colors.white
      ),
      padding: EdgeInsets.all(10),
      child: Column(
        children: <Widget>[
          Text(
            this.title,
            style: titleStyle,
          ),
          SizedBox( // 使用SizeBox 可以做垂直和水平方向上的间距
              height: 8
          ),
          Text(
            this.desc,
            style: descStyle,
          ),
          Image.network(this.imageUrl)
        ],
      ),
    );
  }
}

```

![Snip20200807_1](images/Snip20200807_1.png) 



### 3、设置水平和垂直对齐方式

在flutter中的布局和前端中Flex布局很像

在flex布局中没有严格的水平布局和垂直布局的概念, 也就是说在flex 布局中是没有严格意义的水平轴和垂直轴的概念.

在flex布局中只有**主轴 和 交叉轴** , 有的地方也叫做 **主轴 和 侧轴** , 的概念, 我习惯上将这两个轴叫做**主轴 和 侧轴** .

主轴和侧轴始终代表两个垂直的方向, 主轴代表的方向可以是水平的也可以竖直的, 当然侧轴代表的方向也可以是水平的或者是竖直的, 具体的方向需要根据特定的环境来定. 



- 主轴的排列方式主要有以下几种:

  ```
  enum MainAxisAlignment {
    start,
    end,
    center, 
    spaceBetween,
    spaceAround,
    spaceEvenly,
  }
  ```

- 侧轴的排列方式主要有以下几种:

  ```
  enum CrossAxisAlignment {
    start,
  	end,
  	center,
    stretch,
    baseline,
  }
  ```




# 十一、生命周期

## 1、StatefulWidget 的生命周期



### 1、生命周期的理解

什么是生命周期?

- 客户端开发: 在iOS开发中我们需要知道UIViewController 从创建到销毁的整个过程,

  android开发中, 我们要知道Activity从创建到销毁的整个过程, 以便在不同的生命周期方法中完成不同的操作.

- 前端开发中, Vue、React开发中, 组件也都有自己的生命周期, 在不同的生命周期中我们可以做不同的操作/

flutter中Widget 的生命周期:

- StatelessWidget 可以由父Widget直接传入值, 并调用构造方法来构造, 整个过程非常的简单
- 而, StatefulWidget需要通过State来管理其数据, 并且还要监控状态的改变决定是否重新build整个Widget
- 所以, 在flutter开发中, 我们主要讨论StatefulWidget的生命周期, 也就是它从创建到销毁的整个过程.

> 对于我们开发者来说, 生命周期有什么样的意义:
>
> 1、初始化一些变量、 数据、状态
>
> 2、发送网络请求
>
> 3、监听组件的监听事件
>
> 4、管理内存

```
// 因为在StatelessWidget 中, 只有一个构造函数和 build 方法
// StatelessWidget一旦创建出来就定了, 所以我们一般很少说StatelessWidget的生命周期
class YRHomeContent extends StatelessWidget{
  final String content;

  YRHomeContent(this.content);

  @override
  Widget build(BuildContext context) {
    return  Text(content);
  }
}
```





### 2、生命周期的---简单版

> 在这个版本中, 我们讲解那些常用的方法和回调, 下个版本中我们解释一些比较复杂的方法和回调



那么StatefulWidget有那些生命周期的回调呢? 他们分别在什么情况下执行呢? 

- 在下图中, 灰色的部分是flutter内部操作的, 我们并不需要去手动设置它
- 白色的部分, 表示我们可以去监听 或者 可以 手动调用

我们知道一个StatefulWidget本身包含两个类组成: `StatefulWidget` 和 `State` , 我们对他们分开进行总结, 如下: 

![Snip20200811_2](images/Snip20200811_2.png) 

```
import 'package:flutter/material.dart';

main(){
  runApp(YRCounterApp());
}

class YRCounterApp extends StatelessWidget{

  @override
  Widget build(BuildContext context) {

    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: Text('我是标题'),
        ), 
      body: ChangeFlag(),
      )

    );
  }
}

class ChangeFlag extends StatefulWidget {
  @override
  _ChangeFlagState createState() => _ChangeFlagState();
}

class _ChangeFlagState extends State<ChangeFlag> {
  int flag = 1;
  @override
  Widget build(BuildContext context) {
    return Container(
      child: Column(
        children: <Widget>[
          RaisedButton(
            child: Text('change flag: $flag'),
            onPressed: (){
              setState(() {
                flag = (flag == 1 ? 0 : 1);
              });
            },
          ),
          HomeContent()
        ],
      ),
    );
  }
}


class HomeContent extends StatefulWidget {

  HomeContent(){
    print('1. 调用 statefulWidget 的构造方法');
  }
  @override
  _HomeContentState createState(){
    print('2. 调用 StatefulWidget 的 createState 方法');
    return _HomeContentState();
  }
}

class _HomeContentState extends State<HomeContent> {

  int _count = 0;

  _HomeContentState(){
    print('3. 调用 State 的构造方法');
  }

  // 注意, 自定义initState 方法时, 必须调父类的 initState方法
  @override
  void initState() {
    print('4. 调用 state 的initState 方法');
    super.initState();
  }

  @override
  Widget build(BuildContext context) {

    print('5. 调用 state 的 build 方法');
    return Container(
      width: 500,
      height: 100,
      color: Colors.cyan,
      child: RaisedButton(
        child: Text('点解+, 当前计数: $_count'),
        onPressed: (){
          print('点击了+');
          setState(() {
            _count++;
          });
        },
      ),
    );
  }

  // 自定义dispose 方法, 必须调父类的 dispose 方法
  @override
  void dispose() {
    print('6. 调用 state 类的  dispose 方法');
    super.dispose();
  }

  // 自定义 didChangeDependencies 方法, 必须调用父类的didChangeDependencies
  @override
  void didChangeDependencies() {
    print(' 调用 state 类的  didChangeDependencies 方法');
    super.didChangeDependencies();
  }

  // 自定义 didUpdateWidget 方法, 必须调父类的 didUpdateWidget
  @override
  void didUpdateWidget(HomeContent oldWidget) {
    print(' 调用 state 类的 didUpdateWidget 方法');
    super.didUpdateWidget(oldWidget);
  }

  // 自定义 setState 方法, 必须调用父类的 setState 方法
  @override
  void setState(fn) {
    print('调用 State 类的 setState 方法');
    super.setState(fn);
  }
}
```

从上面的代码及流程图, 我们可以发现 `StatefulWidget` 主要有9个生命周期方法

- 1、`StatefulWidget` 中的构造方法

  > 构造方法主要用来创建和初始化StatefulWidget 对象

- 2、`StatefulWidget` 中的createState方法

  > createState 方法主要用来创建一个State实例对象, 来维护StatefulWidget对象
  >
  > 其次, 在调用对应的createState 方法的同时, 执行State类中的相关方法

- 3、`State` 中的 构造方法

  > 构造State实例对象

- 4、`State` 中的 `initState` 方法, 重写时必须调父类的 initState 方法

  > 在执行 initState 方法时, 我们通常会做一些数据初始化操作, 或者肯能也会发送一些网络请求等等

- 5、`State`中的 didChangeDependencies 方法

  > didChangeDependencies 这个生命周期的方法, 在两种情况下会调用
  >
  > 情况1: 当`State` 类中的 `initState` 方法被调用后, 会调用 didChangeDependencies 方法
  >
  > 情况2: 当从其它对象中中依赖的一些数据发生变化的时候会再次调用 didChangeDependencies方法,  比如: 我们前面有提到的 `inheritedWidget` , 一旦 didChangeDependencies 方法被调用后, 就后重新调用 State 中的 build 方法
  >
  > 这里我们可以大致介绍下, 什么是inheritedWidget, 首先inherited 是继承的意思, 我们前面有提到过其实Widget可以理解为是一个配置, inheritedWidget 可以理解为是可以及成果的Widget, 一般我们在做数据共享的时候会用到. 比如: 我们几个不同的Widget在显示同一个数据状态时就可以使用

- 6、`State` 中的 build 方法

  > 这个方法主要是为StatefulWidget 构建widget

- 7、`State` 中的   `setState` 方法

  > 一旦调用 State 中的setState 方法, 就会调用 Element的 markNeedsBuild 方法, 标记需要 build,然后就会重新调用State 中的build 方法, 对widget中的内容进行重新绘制, 最终达到更新页面的目的
  >
  > 换句话说, State中的setState 的本质就是给对应的Element 做 needbuild 的标记, 等到下一帧的时候调用build方法重新构建widget, 刷新页面的目的

- 8、`State` 中的 `didUpdateWidget` 方法

  > 当父Widget发生改变的时候, 就会调用子Widget 的didUpdateWidget 方法, 当子widget 的didUpdateWidget  方法, 然后子Widget 接着就会调用build 方法重build自己的Widget, 达到页面变化的效果
  >
  > 其实从`didUpdateWidget` 的名称中, 我们可以知道, 这个方法是Widget被更新的意思, 其实原理是这样的:
  >
  > -  一句话, StatefulWidget 被创建后会被对应的一个State持有(管理), 这个State只会创建和销毁一次, 但是State持有的Widget可能会变化. 当父widget 重新调用build 后, 就会调用持有子Widget的State的 didUpdateWidget方法, 接着State中就会重新在调用build 方法重新构建子Widget, didUpdateWidget的目的是让子Widget对应的State重新指向一个新的Widget

- 9、`State` 中的 dispose 方法, 重写时必须调用父类的 dispose 方法. 



> 以上, 就是我们StatefulWidget 的一个比较完整的生命周期的流程
>
> 大家需要对这个流程很熟悉, 才能真正的掌握flutter开发的正确姿势. 
>
> 如果你对flutter的生命周期都不清楚, 那你就不会掌握代码的运行逻辑, 会出问题的





### 3、生命周期的---复杂版

![Snip20200811_2](images/Snip20200811_2.png) 

我们在前面学习生命周期简单版的时候, 上图中灰色的几个生命周期函数是没有学习的, 下面我们来学习一下其它的几个生命周期函数:

`mounted` `dirty State` `clean state` 



- `mounted` 是State中内置的一个属性`(get 属性)`, 事实上我们不了解它开发也是没有问题的, 但是如果你想要深入的学习, 会对State的机制有更加深刻的理解. 

  - 很多资料中是没有提到这个属性的, 但是我这里把它列出来, 是内部设置的, 不需要我们手动进行修改

    ![Snip20200812_4](images/Snip20200812_4.png)

    > 从上面的截图, 我们可以知道, 
    >
    > 在我们创建了一个 State, 在State执行 initState 方法之前, frameWork(即我们的flutter框架)会通过一个`BuildContext` 挂在这个属性, 这个mouted 属性最主要的功能就是记录一个`_Element` 这个属性是否为空, 如果`_Element` 不为空就表示你当前是处于`mounted` 挂在状态, 否则就处于非挂载状态(销毁状态)

- `dirty state` 的含义是脏的 state 的意思

  - 它实际上是通过一个Element的东西(我们后面会学习Element的绘制原理) 的属性来标记的

  - 将它标记为dirty, 会等待下一次的重绘检查, 强制调用 build 方法来构建我们的Widget

    > 后面我们会写一篇关于StatelessWidget 和 StatefulWidget的区别的文章, 讲解一下在开发中我们如何选择StatelessWidget和StatefulWidget

- `clean state` 的含义是干净的 state

  - 它表示当前build 出来的widget, 下一次重绘检查时不需要重新build	





# 十二、基础Widget



基础Widget: `文本` 、`按钮` 、`图片`、`输入框` 



## 1、 编程范式

### 1、编程范式的理解

**编程范式** 对于初学编程的人来说是一个虚无缥缈的东西, 但是确实我们日常开发中都在默认的遵循的一些**模式 和 方法**

- 比如: 我们常用的`面向对象编程` 就是一种编程范式, 与之对应的或者结合开发的包括:`面向过程编程`、`函数式编程` 、`面向协议编程` 
- 另外还有两个对应的编程范式: `命令式编程`  和 `声明式编程`
  - **命令式编程**: 命令式编程非常好理解, 就是一步步给计算机命令(指令), 告诉它我们要做的事情
  - **生命式编程**: 声明式编绳与命令式编程不同, 声明式编程通常是描述目标的性质,比如: 
    - 你应该是什么样式的
    - 你依赖那些状态(数据), 并且当依赖的状态(数据) 发生变化的时候, 我们通过某些方式通知目标作出相应的变化(改变)

> 因为我们flutter的 编程范式 与 iOS 和 android 的编程范式是不一样的, iOS 和 android 一般任然采用的命令式更多, 而flutter中一般采用的是声明式的, 只有在 编程方式上有了大概的理解后, 这样我们在flutter开发中才会有正确的思维方式以及思考方向



想我们平时用到的 `Vue` `React` 就是属于声明式的框架, 我们要实现功能时, 找到对应的组件, 配置对应的参数(描述)即可, 我们不需要知道里面的实现细节. 像我们在iOS 和android 开发中我们就需要了解更多的细节一步步实现

### 2、flutter的编程范式

从2009年(数据来自维基百科), 声明式编程就开始流行起来, 并且在`Vue` 、`React` 、包括iOS中的`SwiftUI` 以及`flutter` 项目中都采用了声明式编程.



现在我们开开发一个需求:

实现一个 hello world, 之后又修改成 hello flutter

- 如果我们采用命令式编程, 伪代码应该是这样的

  ```
  final text = new Text();
  var title = "Hello world";
  text.setContent(title);
  
  // 修改数据
  title = "hello flutter";
  text.setContent(title);
  ```

- 声明式编程 , 我们通常维护一套数据集

  - 这个数据可以来自自己的父类、来自自身State管理、来自inheritedWidget、来自同一的状态管理的地方

  - 总之, 我们知道有这么一个数据集, 并且告诉flutter这些数据集在哪里使用

    ```
    var title = "hello world";
    Text(title); // 告诉Text widget 内部显示的就是 title中的内容
    
    // 修改数据
    title = "hello flutter";
    // 通知重新 build widget 即可, 他在build 的时候自动的就取到了新数据
    setState((){
    	
    })
    ```



> 一定要对声明式编程有个理解, 这样在 后续flutter 开发中才会更得心应手. 





## 2、文本Widget (待完善)

在 Android 中, 我们使用的是 TextView, 在iOS  中我们使用UILabel来显示文本

在flutter中, 我们使用`Text` 组件来控制文本如何展示.

### 1、Text 的使用 (普通文本)

在flutter中, 我们可以将文本的控制显示分成两类:

- **控制文本 布局的参数**: 

  - 如文本对齐的方式 `textAlign` 、文本排版方向`textDirection` 、文本显示最大行数`maxLines`、文本的截断规则`overflow` 等等, 这些都是构造函数中的参数. 

- **控制文本 样式的参数**: 

  - 如字体的名称`fontFamily` 、字体大小`fontSize` 、文本颜色`color` 、文本阴影`shadows` 等等, 这些参数被统一封装到了构造函数中的参数`style` 中. 

```
 const Text(
    this.data, {
    Key key,
    this.style,					// 显示额样式, 比如字体大小, 颜色, 背景
    this.strutStyle,
    this.textAlign,
    this.textDirection,
    this.locale,
    this.softWrap,
    this.overflow,
    this.textScaleFactor,
    this.maxLines,
    this.semanticsLabel,
    this.textWidthBasis,
    this.textHeightBehavior,
  })
```

Text widget就是用于显示最基础的文本, 相当于我们iOS 中的UILabel 或者 android 中的TextView, 使用很简单. 只有一个必选参数用于接收要显示的字符串, 这里就不再敖述了

#### 1、Text Demo1

```
class TextContentDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Container 有个特点是, 设置了宽高信息就按具体的宽高信息来显示, 否则按照父组件的大小展示
    // 给Container组件提供宽高信息的方式有很多: 比如: 设置宽高属性width,height 或者约束Constraints, 或者设置
    // child 属性, 这些都算是给Container提供宽高信息
    return Container(
      color: Colors.pink,
      child: Text(
        "《定风波》 苏轼 \n莫听穿林打叶声，何妨吟啸且徐行。\n竹杖芒鞋轻胜马，谁怕？一蓑烟雨任平生。",
        style: TextStyle(
            fontSize: 15,
            color: Colors.white,
            backgroundColor: Colors.orange    // Text 的背景色, 这个最好别用, 容易出现字体大小背景色不好看的样式
        ),
      ),
    );
  }
}
```

![](images/textdm1.png) 



#### 2、TextDemo e2

```
class TextContentDemo2 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Container 有个特点是, 设置了宽高信息就按具体的宽高信息来显示, 否则按照父组件的大小展示
    // 给Container组件提供宽高信息的方式有很多: 比如: 设置宽高属性width,height 或者约束Constraints, 或者设置
    // child 属性, 这些都算是给Container提供宽高信息
    return Container(
      color: Colors.pink,
      width: double.infinity,
      height: 100,
      child: Text(
          "《定风波》 苏轼 \n莫听穿林打叶声，何妨吟啸且徐行。\n竹杖芒鞋轻胜马，谁怕？一蓑烟雨任平生。",
        style: TextStyle(
          fontSize: 30,
          color: Colors.white,
          backgroundColor: Colors.orange    // Text 的背景色, 这个最好别用, 容易出现字体大小背景色不好看的样式
        ),
        maxLines: 3,    // 最大显示行数, 如果要显示的行数不确定就不设置, 没有像iOS中的0就是显示任意行数
        textAlign: TextAlign.right,   // 只有当Text的父组件的宽度超过自己时才会有效果
        overflow: TextOverflow.fade,

      ),
    );
  }
}
```

![](images/textdm2.png) 





### 2、Text.rich 富文本展示

前面展示的文本，我们都应用了相同的样式，如果我们希望给他们不同的样式呢？

- 比如《定风波》我希望字体更大一点，并且是黑色字体，并且有加粗效果；
- 比如 苏轼 我希望是红色字体；

如果希望展示这种混合样式，那么我们可以利用分片来进行操作（在Android中，我们可以使用SpannableString，在iOS中，我们可以使用NSAttributedString完成，了解即可）



#### 1、Text.rich 的简单使用

```
class TextRichDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      child: Text.rich(
        TextSpan(
          children: [
            TextSpan(text: "《定风波》", style: TextStyle(fontSize: 25, fontWeight: FontWeight.bold, color: Colors.black)),
            TextSpan(text: "苏轼", style: TextStyle(fontSize: 18, color: Colors.redAccent)),
            TextSpan(text: "\n莫听穿林打叶声，何妨吟啸且徐行。\n竹杖芒鞋轻胜马，谁怕？一蓑烟雨任平生。")
        ],
      )
      ),

    );
  }
}
```

![](images/textrichdm1.png )  



#### 3、Text.Rich 图文示例

先来一个示例效果:

![Textrich](images/Textrich.png) 

在来一段示例代码:

```
mport 'package:flutter/material.dart';
main(List<String> args){
  runApp(YRApp());
}


class YRApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: true,
      home: HomePage()
    );
  }
}


class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('我是标题'),
      ) ,
      body: TextContent(),
    ) ;
  }
}



class TextContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Column(
      children: <Widget>[
        // 普通文本使用 Text 这个Widget即可
        Text(
          '我是普通文本',
          style: TextStyle(
            fontSize: 20,
            color: Colors.white,
            backgroundColor: Colors.green
          ),
        ),

        // 富文本需要使用 Text.rich
        Text.rich(
          TextSpan(
            text: '我是富文本的文字\n',
            children:[
              TextSpan(
                  text:'我是富文本的富文本文字\n'
              ),
              WidgetSpan(
                child: Icon(Icons.favorite, color: Colors.red, size: 30,)
              )

            ]
          ),
          textAlign: TextAlign.right,
          style: TextStyle(
            backgroundColor: Colors.orange
          ),

        ),

      ],
    );
  }
}

```

最后来个总结:

> ```
> 简单说:
> - 如果我们想要显示一段纯文本, 使用Text 这个Widget即可
> - 如果我们想要显示一段富文本, 就使用 Text.rich()
> 
> 在Text.rich()  中有个 InlineSpan 类型的必选参数, 也就是说如果我们要显示富文本, 就必须把富文本的文字图片等包装成InlineSpan 类型的Widget
> 
> 然而 InlineSpan 是抽象类我们不能直接使用, 通过快捷键 `option+command+b` 我们发现抽象类
> InlineSpan 有两个实现类 TextSpan 和 WidgetSpan, 也就是说我们要显示的富文本内容(图文)最终需要包装成 TextSpan或者WidgetSpan
> 
> 其中TextSpan 中有个text的可选属性用于接收字符串的文本, 有个 List 类型的可选属性 children 用来接收其它要显示的 InlineSpan Widget. 
> 
> 而在WidgetSpan中只有一个 Widget类型的child 属性用来接收其它要显示的 widget
> ```



## 3、按钮的使用



Material widget库中提供了多种按钮Widget如: `FloatingActionButton`、`RaisedButton`、`FlatButton`、`OutlineButton`等

```
class ButtonDemoContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Column(
      children: <Widget>[
        FloatingActionButton(
          child: Text('float action button title'),
          onPressed: () {
            print(' float action button 被点击了');
          },
        ),

        RaisedButton(
          child: Text('raise buttonn'),
          onPressed: () {
            print('raise button click');
          },
        ),
        FlatButton(
          child: Text('flat buttonn'),
          onPressed: () {
            print('flat button click');
          },
        ),
        OutlineButton(
          child: Text('OutlineButton buttonn'),
          onPressed: () {
            print('OutlineButton button click');
          },
        ),
        // 自定义button
        FlatButton(
          color: Colors.orange,
          highlightColor: Colors.red,
          textColor: Colors.white,
          shape:RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(10)
              ),
          child: Text('自定义 buttonn'),
          onPressed: () {
            print('自定义 button click2');
          },
        ),
        FlatButton(
          color: Colors.red,
          disabledColor: Colors.grey,
          highlightColor: Colors.blue,
          // 设置圆角
          shape:RoundedRectangleBorder(
              borderRadius:BorderRadius.circular(10)
          ) ,

          child: Row(
            // 控制主轴上占用的宽度
            mainAxisSize: MainAxisSize.min,
            children: <Widget>[
              Text('自定义button'),
              SizedBox(width: 25,),
              Icon(Icons.people)
            ],
          ),
          // onPress 这个属性很重要, 直接控制了 button 的disable
          onPressed: (){
            print('自定义 图文 button 点击了');
          },
        ),
        IconButton(
          color: Colors.cyan,
          icon: Icon(Icons.people),
          onPressed: (){},
        )
      ],
    );
  }
}
```

![](images/buttondemo1.png)  





## 4、图片的使用

图片可以让我们的应用更加丰富多彩，Flutter中使用Image组件

Image组件有很多的构造函数，我们这里主要学习两个：

- Image.assets：加载本地资源图片；
- Image.network：加载网络中的图片；









### 1、本地图片的使用

在我们的flutter开发中, 使用本地图片主要有三个步骤:

- 在flutter项目中创建一个文件, 用于存储图片

- 在`pubspec.yaml` 文件中配置图片的信息

  ![Snip20200817_1](images/Snip20200817_1.png) 


```
class ImageDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Image(
    	// Image Widget有个续传属性 image 是一个ImageProvider, 加载本地图片时, 我们可以使用
    	// AssetImage, 提供一个图片路劲即可
      image: AssetImage('asset/images/card@1x.png'),
    );
  }
}
```

> 一般我们使用本地图片, 为了简化代码 一般法会尽量使用  `Image.asset()` 代替

```
Image.asset('asset/images/card@1x.png');
```

### 2、网络图片的使用

相对来讲，Flutter中加载网络图片会更加简单，直接传入URL并不需要什么配置，所以我们先来看一下Flutter中如何加载网络图片。

我们先来看看Image有哪些属性可以设置：

> const Image({
>   ...
>   this.width, *//图片的宽*
>   this.height, *//图片高度*
>   this.color, *//图片的混合色值*
>   this.colorBlendMode, *//混合模式*
>   this.fit,*//缩放模式*
>   this.alignment = Alignment.center, *//对齐方式*
>   this.repeat = ImageRepeat.noRepeat, *//重复方式*
>   ...
> })

```
class ImageDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Image(
      image:NetworkImage(url)
    );

  }
}
```

> 般我们使用网络图片, 为了简化代码 一般法会尽量使用  `Image.network()` 代替

```
Image.network(url);
```





### 3、图片常用的属性介绍

- `width`、`height`：用于设置图片的宽、高. 

  - 当不指定宽高时，图片会根据当前父容器的约束限制，尽可能的显示其原始大小
  - 如果只设置`width`、`height`的其中一个，那么另一个属性(宽、高)默认会按比例缩放，但可以通过下面介绍的`fit`属性来指定适应规则。

- `fit`：该属性用于在图片的显示空间和图片本身大小不同时指定图片的适应模式。具体取值如下:

  ```
  enum BoxFit {
    fill,
    contain,
    cover,
    fitWidth,
    fitHeight,
    none,
    scaleDown,
  }
  ```

- **示例代码如下:**

  ```
  
  class ImageDemoContent extends StatelessWidget {
    final String url =
        'https://pics2.baidu.com/feed/fc1f4134970a304e410cd2820c348981c8175c9b.jpeg?token=f9c9fd8d67c2cf3c1c152eca34009a3c';
  
    @override
    Widget build(BuildContext context) {
      return Column(
        children: <Widget>[
          Row(
            children: <Widget>[
              Container(
                  color: Colors.cyan,
                  child: Image(
                    image: NetworkImage(url),
                    width: 120,
                  )),
              Text('只设置宽,不设置fit属性')
            ],
          ),
          
          
          SizedBox(height: 10,),
          Row(
            children: <Widget>[
              Container(
                  color: Colors.orange,
                  child: Image(
                    image: NetworkImage(url),
                    width: 120,
                    height: 120,
                  )),
              Text('同时设置宽高, 不设置fit属性')
            ],
          ),
          
          
          SizedBox(height: 10,),
          Row(
            children: <Widget>[
              Container(
                  color: Colors.pink,
                  child: Image(
                    image: NetworkImage(url),
                    width: 120,
                    height: 120,
                    fit: BoxFit.fill, //会拉伸填充满显示空间，图片本身长宽比会发生变化，图片会变形
                  )),
              Text('同时设置宽高, 和fit=fill')
            ],
          ),
          
          
          SizedBox(height: 10,),
          Row(
            children: <Widget>[
              Container(
                  color: Colors.pink,
                  child: Image(
                    image: NetworkImage(url),
                    width: 120,
                    height: 120,
                    fit: BoxFit.cover, //会按图片的长宽比放大后居中填满显示空间，图片不会变形，超出显示空间部分会被剪裁。
                  )),
              Text('同时设置宽高和 fit= cover')
            ],
          ),
          
          
          SizedBox(height: 10,),
          Row(
            children: <Widget>[
              Container(
                  color: Colors.pink,
                  child: Image(
                    image: NetworkImage(url),
                    width: 120,
                    height: 120,
                    // 这是图片的默认适应规则，图片会在保证图片本身长宽比不变的情况下缩放以适应当前显示空间，图片不会变形。
                    fit: BoxFit.contain,
                  )),
              Text('同时设置宽高, 设置fit=contain')
            ],
          ),
          
          
          SizedBox(height: 10,),
          Row(
            children: <Widget>[
              Container(
                  color: Colors.pink,
                  child: Image(
                    image: NetworkImage(url),
                    width: 120,
                    height: 120,
                    // fitHeight 图片等比缩放, 高度拉伸到指定高度, 宽度超出会裁剪掉
                    // fitWidth 图片等比缩放, 宽度拉伸到指定高度, 高度超出会裁剪掉
                    // 可以把 cover 理解成为fitWidth 或者 fitHeight
                    fit: BoxFit.fitHeight,
                  )),
              Text('同时设置宽高, 设置fit=fitHeight')
            ],
          ),
        ],
      );
    }
  }
  
  ```

  ![](images/imagefit1.png)  



### 4、圆角图片

> 在Flutter中实现圆角效果也是使用一些Widget来实现的。



#### 1、CircleAvatar 实现圆角

CircleAvatar可以实现圆角头像，也可以添加一个子Widget：

换句话说, CircleAvatar 就是一个实现圆角功能的Widget,  将要显示圆角的Widget使用CircleAvatar包裹配上参数即可

```
const CircleAvatar({
  Key key,
  this.child, *// 子Widget*
  this.backgroundColor, *// 背景颜色*
  this.backgroundImage, *// 背景图像*
  this.foregroundColor, *// 前景颜色*
  this.radius, *// 半径*
  this.minRadius, *// 最小半径*
  this.maxRadius, *// 最大半径*
})
```

> 注意:
>
> 此处, backgroundImage 是一个ImageProvider类型的参数, 不能直接使用图片

- 示例代码: 

  ```
  class CircleImageDemo1 extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return CircleAvatar(  
        backgroundImage: NetworkImage(url),
        radius: 100 / 2,
        child: Text('我是 文字', style: TextStyle(fontSize: 20, color: Colors.green),),
      );
    }
  }
  ```

  ![](images/circleiamge1.png) 



#### 2、ClipOval 实现圆角

```
const ClipOval({
    Key key, 
    this.clipper, 
    this.clipBehavior = Clip.antiAlias, 
    Widget child
})
```

通常我们使用ClipOval 来实现圆角头像,默认情况下 ClipOval 会根据子组件的宽高自动实现圆角, 如果子组件宽高相等就是一个圆, 否则就是一个椭圆

 示例代码如下:

```
class ClipOvalDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Column(
      children: <Widget>[
        ClipOval(
          child: Container(
            color: Colors.green,
            child: Image(
              image: NetworkImage(url),
              width: 100,
              height: 200,
            ),
          )
        ),
        
        SizedBox(height: 10,),
        
        ClipOval(
          child: Container(
            color: Colors.green,
            child: Image(
              image: NetworkImage(url),
              width: 200,
              height: 200,
            ),
          )
        ),
      ],
    );
  }


}
```

![](images/clipovaldemo1.png) 



#### 3、Container + BoxDecoration 实现圆角

## 5、字体图标 icon



## 6、表单Widget

> 和用户交互的其中一种就是输入框，比如注册、登录、搜索，我们收集用户输入的内容将其提交到服务器。



### 1、**TextField** 的简单介绍

TextField用于接收用户的文本输入，它提供了非常多的属性，我们来看一下源码：

但是我们没必要一个个去学习，很多时候用到某个功能时去查看是否包含某个属性即可

```
const TextField({
  Key key,
  this.controller,
  this.focusNode,
	//  用于设置输入框相关的样式, 如下:
  //	icon：设置左边显示的图标
  //  labelText：在输入框上面显示一个提示的文本
  //  hintText：显示提示的占位文字
  //  border：输入框的边框，默认底部有一个边框，可以通过InputBorder.none删除掉
  //  filled：是否填充输入框，默认为false
  //  fillColor：输入框填充的颜色
  this.decoration = const InputDecoration(),
  
  TextInputType keyboardType,		// 键盘的类型(数字键盘, 文字键盘)
  this.textInputAction,					// return 键显示的样式
  this.textCapitalization = TextCapitalization.none,
  this.style,										// 设置输入框文字样式
  this.strutStyle,
  this.textAlign = TextAlign.start,	// 文本对齐方式
  this.textAlignVertical,
  this.textDirection,
  this.readOnly = false,
  ToolbarOptions toolbarOptions,
  this.showCursor,
  this.autofocus = false,
  this.obscureText = false,
  this.autocorrect = true,
  this.maxLines = 1,
  this.minLines,
  this.expands = false,
  this.maxLength,
  this.maxLengthEnforced = true,
  this.onChanged,				// 监听输入框内容的改变，传入一个回调函数
  this.onEditingComplete,
  this.onSubmitted,			// 点击键盘中右下角的down时，会回调的一个函数
  this.inputFormatters,
  this.enabled,
  this.cursorWidth = 2.0,
  this.cursorRadius,
  this.cursorColor,
  this.keyboardAppearance,
  this.scrollPadding = const EdgeInsets.all(20.0),
  this.dragStartBehavior = DragStartBehavior.start,
  this.enableInteractiveSelection = true,
  this.onTap,
  this.buildCounter,
  this.scrollController,
  this.scrollPhysics,
})
```



​			

### 2、TextField 的简单使用

示例代码如下:

```
class TextFieldContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      child: TextField(
        keyboardType:TextInputType.text,                  // 键盘的样式(数字键盘, 文字键盘...)
        textInputAction: TextInputAction.join,            // return 键显示的样式
        style: TextStyle(color:Colors.red, fontSize: 30), // 输入框的文字样式
        decoration: InputDecoration (
          icon: Icon(Icons.people),  // 输入框左边的按钮
          hintText: '我是占位文字',   // 输入框的占位文字
          hintStyle: TextStyle(color: Colors.green),
          filled: true,         // 只有filled为true 时, 才能使用fillColor
          fillColor: Color.fromARGB(50, 255, 0, 0) // 输入框填充色
        ),
        onChanged: (String value ){ // 当输入框的文字发生变化就会回调这个方法, 在这里监听输入框的变化
          print('textfield change: $value');
        },
        onSubmitted: (String value){ // 当用户点击 done 按钮时回调这个方法
          print('key board down: $value');
        },
      ),
    );
  }
}
```

![](images/textfield1.png) 



### 3、TextField 的controller

我们可以给TextField添加一个控制器（Controller），可以使用它设置文本的初始值，也可以使用它来监听文本的改变；

> 事实上，
>
> 如果我们没有为TextField提供一个Controller，那么会Flutter会默认创建一个TextEditingController的，这个结论可以通过阅读源码得到, 如下:
>
> ```
> @override
>   void initState() {
>     super.initState();
>     // ...其他代码
>     if (widget.controller == null)
>       _controller = TextEditingController();
>   }
> ```

我们也可以自己来创建一个Controller控制一些内容：

```
class TextFieldContent2 extends StatefulWidget {
  @override
  _TextFieldContent2State createState() => _TextFieldContent2State();
}

class _TextFieldContent2State extends State<TextFieldContent2> {
  // 因为我们要个TextField 设置controller, 且只设置一次, 所以我们在 initState 方法中设置最好
  final textEditingCtr = TextEditingController();

  @override
  void initState() {
    super.initState();

    // 1.通过controller 设置TextField的默认文字
    textEditingCtr.text = "默认昵称";

    // 2. 监听文本框
    textEditingCtr.addListener(() {
      print('text edit ctr listener: ${textEditingCtr.text}');
    });
  }

  @override
  Widget build(BuildContext context) {
    return Container(
      child: TextField(
        controller: textEditingCtr, 
        decoration: InputDecoration(
            contentPadding: EdgeInsets.all(10), hintText: "请输入昵称"),
      ),

    );
  }
}
```









## 7、Form表单



### 1、Form的基本使用

Form表单也是一个Widget，可以在里面放入我们的输入框。

但是Form表单中输入框必须是FormField类型的

- 我们查看刚刚学过的TextField是继承自StatefulWidget，并不是一个FormField类型；
- 我们可以使用TextFormField，它的使用类似于TextField，并且是继承自FormField的；

我们通过Form的包裹，来实现一个注册的页面：

```

class FormContent extends StatefulWidget {
  @override
  _FormContentState createState() => _FormContentState();
}

class _FormContentState extends State<FormContent> {
  @override
  Widget build(BuildContext context) {
    return Form(

      child: Container(
        padding: EdgeInsets.fromLTRB(10, 0, 10, 0),
        margin: EdgeInsets.fromLTRB(0, 50, 0, 0),
        color: Colors.lightGreen,

        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: <Widget>[
            TextFormField(
              decoration: InputDecoration(
                icon: Icon(Icons.people, color: Colors.orange,),
                hintText: '用户名',
              ),
            ),

            SizedBox(height: 10,),
            TextFormField(
              obscureText: true,  // 是否显示密码
              decoration: InputDecoration(
                icon: Icon(Icons.lock, color: Colors.orange,),
                hintText: "密码",
              ),
            ),

            SizedBox(height: 10,),
            Container(
              width: double.infinity,
              child: RaisedButton(
                color: Colors.orange,
                child: Text('点击 注册'),
                onPressed: (){

                },
              ),
            )
          ],
        ),
      ),
    );
  }
}


```

![](images/formdemo1.png)  





### 2、保存和获取表单数据

**有了表单后，我们需要在点击注册时，可以同时获取和保存表单中的数据，怎么可以做到呢？**

1. 需要监听注册按钮的点击，在之前我们已经监听的onPressed传入的回调中来做即可。（当然，如果嵌套太多，我们待会儿可以将它抽取到一个单独的方法中）

2. 监听到按钮点击时，同时获取`用户名`和`密码`的表单信息。

   

**如何同时获取`用户名`和`密码`的表单信息？** 

如果我们调用`Form的State对象`的save方法，就会调用Form中放入的TextFormField的onSave回调

```
TextFormField(
  obscureText: true,  // 是否显示密码
  decoration: InputDecoration(
    icon: Icon(Icons.lock, color: Colors.orange,),
    hintText: "密码",
  ),
  onSaved: (value){
    print('获取到用户密码: ${value}');
  },
)
```

但是，我们有没有办法可以在点击按钮时，拿到 `Form对象` 来调用它的save方法呢？

> 知识点：
>
> 在Flutter如何可以获取一个通过一个引用获取一个StatefulWidget的State对象呢？

```
class FormContent extends StatefulWidget {
  @override
  _FormContentState createState() => _FormContentState();
}

class _FormContentState extends State<FormContent> {

  // 注册一个formkey
  final registFormKey = GlobalKey<FormState>();
  String userName, password;


  @override
  Widget build(BuildContext context) {
    return Form(
      // 通过formKey.currentState 可以获取到它的State对象
      key: registFormKey,
      child: Container(
        padding: EdgeInsets.fromLTRB(10, 0, 10, 0),
        margin: EdgeInsets.fromLTRB(0, 50, 0, 0),
        color: Colors.lightGreen,
        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: <Widget>[
            TextFormField(
              decoration: InputDecoration(
                icon: Icon(Icons.people, color: Colors.orange,),
                hintText: '用户名',
              ),
              onSaved: (value){
                print('获取到用户名: ${value}');
                this.userName = value;
              },
            ),

            SizedBox(height: 10,),
            TextFormField(
              obscureText: true,  // 是否显示密码
              decoration: InputDecoration(
                icon: Icon(Icons.lock, color: Colors.orange,),
                hintText: "密码",
              ),
              onSaved: (value){
                print('获取到用户密码: ${value}');
                this.password = value;
              },

            ),

            SizedBox(height: 10,),
            Container(
              width: double.infinity,
              child: RaisedButton(
                color: Colors.orange,
                child: Text('点击 注册'),
                onPressed: (){

                  this.registerForm();
                },
              ),
            )
          ],
        ),
      ),

    );
  }

  void registerForm(){
    registFormKey.currentState.save();
    print(registFormKey.currentState);
    print('username: ${userName}, password: ${password}');
  }

}
```



### 3、验证填写的表单数据



在表单中，我们可以添加`验证器`，如果不符合某些特定的规则，那么给用户一定的提示信息

比如我们需要账号和密码有这样的规则：账号和密码都不能为空。

按照如下步骤就可以完成整个验证过程：

- 1、为TextFormField添加validator的回调函数；
- 2、调用Form的State对象的validate方法，就会回调validator传入的函数；

```
class FormContent extends StatefulWidget {
  @override
  _FormContentState createState() => _FormContentState();
}

class _FormContentState extends State<FormContent> {

  // 注册一个formkey
  final registFormKey = GlobalKey<FormState>();
  String userName, password;


  @override
  Widget build(BuildContext context) {
    return Form(
      // 通过formKey.currentState 可以获取到它的State对象
      key: registFormKey,
      child: Container(
        padding: EdgeInsets.fromLTRB(10, 0, 10, 0),
        margin: EdgeInsets.fromLTRB(0, 50, 0, 0),
        color: Colors.lightGreen,
        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: <Widget>[
            TextFormField(
              decoration: InputDecoration(
                icon: Icon(Icons.people, color: Colors.orange,),
                hintText: '用户名',
              ),
              onSaved: (value){ // 当调用 form 的save 方法时, 会自动调用 TextFormField 的onSaved 方法, 获取内容
                print('获取到用户名: ${value}');
                this.userName = value;
              },
              // 我们通过给 TextFormField 添加 验证器来验证数据格式
              validator: (value){
                if(value.isEmpty){
                  return "用户名不能为空";
                }
                return null;
              },
            ),

            SizedBox(height: 10,),
            TextFormField(
              obscureText: true,  // 是否显示密码
              decoration: InputDecoration(
                icon: Icon(Icons.lock, color: Colors.orange,),
                hintText: "密码",
              ),
              onSaved: (value){
                print('获取到用户密码: ${value}');
                this.password = value;
              },
              // 我们通过给 TextFormField 添加 验证器来验证数据格式
              validator: (value){
                if(value.isEmpty){
                  return "密码不能为空";
                }
                return null;
              },

            ),

            SizedBox(height: 10,),
            Container(
              width: double.infinity,
              child: RaisedButton(
                color: Colors.orange,
                child: Text('点击 注册'),
                onPressed: (){

                  this.registerForm();
                },
              ),
            )
          ],
        ),
      ),

    );
  }

  void registerForm(){
    // 获取form 中每个 TextFormField 的文字内容
    registFormKey.currentState.save();
    // 通过调用 validate 方法验证 TextFormField的数据
    registFormKey.currentState.validate();

    print(registFormKey.currentState);
    print('username: ${userName}, password: ${password}');
  }

}
```

![](images/textformfieldvalidate1.png) 



也可以为TextFormField添加一个属性：autovalidate

- 不需要调用validate方法，会自动验证是否符合要求；

```
TextFormField(
  obscureText: true,  // 是否显示密码
  decoration: InputDecoration(
    icon: Icon(Icons.lock, color: Colors.orange,),
    hintText: "密码",
  ),
  onSaved: (value){
    print('获取到用户密码: ${value}');
    this.password = value;
  },
  // 通过自动验证数据格式, 不需要调用 form 的validate() 方法
  autovalidate: true,
  // 我们通过给 TextFormField 添加 验证器来验证数据格式
  validator: (value){
    if(value.isEmpty){
      return "密码不能为空";
    }
    return null;
  },

)
```



# 十三、flutter 布局

在我们前面有用到的 `Button` 、`Image` 、`TextField` 、`Text` 、`Icon`  这些我们在flutter中一般称为叶子组件. 



为了实现界面内组件的各种排布方式，我们需要进行布局，和其他端不同的是，Flutter中因为万物皆Widget，所以布局也是使用Widget来完成的。

Flutter中的布局组件非常多，有31个用于布局的组件，**Flutter布局组件**

在学习的过程中，我们没必要一个个全部掌握，掌握最常用的，一些特殊的组件用到时去查文档即可；



> Flutter将布局组件分成了 `单子布局组件`（Single-child layout widgets） 和 `多子布局组件`（Multi-child layout widgets）

## 1、单子布局组件

> 单子布局组件的含义是其只有一个子组件, 可以通过设置一些属性设置改子组件所在的位置信息.
>
> 比如: 常用的单子布局组件有:
>
> `Align` 、`Center` 、`Padding`、`Container`



### 1、Align 布局组件

> 看到`Align`这个词，我们就知道它有我们的对齐方式有关。
>
> 在其他端的开发中（iOS、Android、前端）Align通常只是一个属性而已，但是Flutter中Align也是一个组件。

我们可以通过源码来看一下Align有哪些属性：

```
const Align({
  Key key,
  this.alignment: Alignment.center, // 对齐方式，默认居中对齐
  this.widthFactor, // 宽度因子，不设置的情况，会尽可能大
  this.heightFactor, // 高度因子，不设置的情况，会尽可能大
  Widget child // 要布局的子Widget
})
```



这里我们特别解释一下`widthFactor`和`heightFactor`作用：

- 因为子组件在父组件中的对齐方式必须有一个前提，就是父组件得知道自己的范围（宽度和高度）；

- 如果`widthFactor`和`heightFactor`不设置，那么默认Align会尽可能的大

  换句话说, 如果没有设置 widthFactor 和 heightFactor 那么Align占据的大小同父组件的宽高一样

  如果设置了WidthFactor 和 heightFactor 那么Align 的宽度和高度就是子组件的 对应倍数.

  

  ```
  class SingleChildContent extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return Align(
        child: Icon(Icons.people, size: 40,),
        alignment: Alignment.bottomRight,
        widthFactor: 2,  // 宽度因子, Align的宽度为Icon的2倍
        heightFactor: 2, // 高度因子, Align的高度为Icon的2倍
      );
    }
  }
  ```

  ![Snip20200827_3](images/Snip20200827_3.png) 



### 2、Center 布局组件

Center组件我们在前面已经用过很多次了。

事实上Center组件继承自Align，只是将alignment设置为Alignment.center。

源码分析：

```
class Center extends Align {
  const Center({
    Key key,
    double widthFactor,
    double heightFactor,
    Widget child
  }) : super(key: key, widthFactor: widthFactor, heightFactor: heightFactor, child: child);
}
```

示例:

```
class CenterContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Center(
      child: Icon(Icons.people, size: 40,),
      widthFactor: 2,
      heightFactor: 2,
    );
  }
}
```

![](images/centerdemo1.png) 













### 3、Padding 布局组件

> Padding组件在其他端也是一个属性而已，但是在Flutter中是一个Widget，但是Flutter中没有Margin这样一个Widget，这是因为外边距也可以通过Padding来完成。
>
> Padding通常用于设置子Widget到父Widget的边距（你可以称之为是父组件的内边距或子Widget的外边距）。

源码分析：

```
const Padding({
  Key key,
  @required this.padding, // EdgeInsetsGeometry类型（抽象类），使用EdgeInsets
  Widget child,
})
```

示例:

```
class PaddingContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Padding(
        padding: EdgeInsets.all(20),
        child: Text(
          "莫听穿林打叶声，何妨吟啸且徐行。竹杖芒鞋轻胜马，谁怕？一蓑烟雨任平生。",
          style: TextStyle(
              color: Colors.redAccent,
              fontSize: 18
          ),
        )
    );
  }
}
```

![](images/paddingdemo1.png) 



## 2、Container 布局组件(重要!!! )

> Container在开发中被使用的频率是非常高的，特别是我们经常会将其作为容器组件。

下面我们来看一下Container有哪些属性：

```
Container({
  this.alignment,
  this.padding, //容器内补白，属于decoration的装饰范围
  Color color, // 背景色
  Decoration decoration, // 背景装饰
  Decoration foregroundDecoration, //前景装饰
  double width,//容器的宽度
  double height, //容器的高度
  BoxConstraints constraints, //容器大小的限制条件
  this.margin,//容器外补白，不属于decoration的装饰范围
  this.transform, //变换
  this.child,
})
```



- 在flutter的开发中, Container 是一个比较特殊的布局组件, 一个Container 容器布局组件具体显示占据多大的空间情况是比较多的, 后面我们会详细的讲解.

- 在讲解Container 布局组件前我们需要先来了解一下在flutter中关于组件的布局流程:

  

### 1 、flutter布局流程及原理介绍

- 大家知道, 我们在flutter开发中, 各种widget 最后都是形成一棵树结构, 最后渲染出来的是一棵RenderObjectTree.

- Flutter 的布局流程其实是这样的, 首先父节点会告诉子节点自己的盒约束Constraits`(一般是BoxConstraints)`,  在BoxConstraits中主要有`minWidth`、`maxWidth`、`minHeight`、`maxHeight` 信息用于描述自己的宽高范围, 当子节点(Renderobject) 拿到父节点约束信息后就知道父节点的宽高范围了, 然后子节点就在父节点的宽高范围内对自己做一个布局调整(比如: 对自己的大小做一个调整, 自己的显示方式调整(比如ListView可以滚动) ). 调整完后父节点就知道子节点的尺寸了且子节点会再将自己的盒约束Constraints 传给自己的子节点, 一层层的布局.

  > 比如说:  父节点是一个Row且盒约束的 maxWidth是 100, 但是 有3个子节点分别的宽度是`50`、`40`、`30`  , 显然 50+40+30 的宽度是超过了父节点的盒约束宽度的, 此时就会报 黄条的越界警告, 说布局错误. 其实父节点在布局子节点的时候会计算一下所有子节点的size 判断是否会越界, 发现越界了就会抛出越界的错误并绘制黄条的警告,如下图

  ![column1](images/column1.png) 

  换句话说, 在我们的flutter布局中, 子节点会根据父节点的盒约束BoxConstraits来调整自己的大小, 不同的子节点有各自调整大小的方式, 子节点调整完自己的大小后会将自己的尺寸再汇报给父节点.

  也就是说, 父节点先将自己的盒约束Constraints传递给子节点, 子节点拿到父节点的盒约束Constraints后再根据父节点的盒约束Constraints调整自己的尺寸, 尺寸调整完成后再将自己的尺寸汇报给父节点, 父节点拿到子节点的尺寸后就知道具体的子节点如何排布, 布局了.

  > 比如说, 父节点知道了子节点的尺寸后, 父节点结合 主轴的对齐方式MainAxisAlignment 以及侧轴的对齐方式CrossAxisAlignment 对子节点进行布局了, 等等...

	

	### 2、flutter 布局总结 

- 父节点会将自己的盒约束传递给子节点, 告诉子节点自己的宽高范围.

- 子节点拿到父节点的盒约束后, 就知道了父节点的宽高范围, 然后子节点就根据父节点的宽高范围调整自己的尺寸以及显示方式

  >  比如:Column 和ListView 作为子节点时调整方式和显示就不一样.

- 子节点根据父节点的盒约束调整完成尺寸和显示方式后, 父节点就知道了子节点的大小, 父节点再根据主轴和侧轴的对齐方式等等,来调整子节点的显示位置 position, 这样整个布局就完成了.

- 当然, 如果子节点还有自己的子节点的话, 就这样一层层的调整, 最后就完成了所有的显示布局了.



### 3、Container 中常见的几种布局介绍

在我们的官方文档中, 对于Container 的描述, 有这么一句总结, 如下:

> Summary:
>
> Container tries, in honor to alignment, to size itself to the child,  to honor the width、 height, and constraints, to expand to fit parent, to be as small as posible.
>
> 翻译: 容器Container尝试，为了对齐，根据子对象调整自身大小，遵循宽度、高度和约束，扩展以适合父对象，尽可能小。

这句话怎么理解呢? 

是这样, Container这个容器为了对齐Alignment , 它会根据子节点的尺寸, 或者设置的宽高, 或者设置的constraints来调整自己的大小, 又或者如果Contianer这个组件内没有设置子节点 或者 宽高 或则 constraints时container 就和父节点一样大.

```
import 'package:flutter/material.dart';
main(List<String> args){
  runApp(YRApp());
}

class YRApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: true,
      home: HomePage()
    );
  }
}

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('我是标题'),
      ) ,
      body: ContainerContent(),
    ) ;

  }
}

```

**示例如下:**

- **表现1:**

  根据子节点调整自己的大小, 子节点有多大自己就多大, 即Container包裹子节点.

  > 即,默认情况下, Container 是包裹子节点的, 子节点多大,Container就占多大

  ```
  // Container占据的大小就是 子节点的大小
  class ContainerContent extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return Container(
        color: Colors.green,
        child: Text('我 是container 的文本'),
      );
    } 
  }
  ```

  ![](images/container_1.png) 

- **表现2:**

   根据Container 中设置的width 和 height 来调整自己的大小, 

  > 即,如果Container 中设置了 width 或 height 那么Container就按照具体的宽高显示

  ```
  // Container 占据的大小就是 width 和 height 描述的大小
  class ContainerContent extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return Container( // 按照宽200, 高100 显示
        width: 200,
        height: 100,
        color: Colors.green,
        child: Text('我 是container 的文本'),
      );
    } 
  }
  ```

  ```
  // Container 占据的高度是 height指定的, 宽度为子节点的宽度
  class ContainerContent extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return Container( // 按照高100, 宽度为子节点的宽 显示
        height: 100,
        color: Colors.green,
        child: Text('我 是container 的文本'),
      );
    } 
  }
  ```

  ```
  // Container 占据的高度是子节点的高度, 宽度是指定的width
  class ContainerContent extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return Container( // 按照宽200, 高度为子节点的高 显示
        width: 200,
        color: Colors.green,
        child: Text('我 是container 的文本'),
      );
    } 
  }
  ```

  ![](images/container_21.png)  ![](images/container_23.png) ![](images/container_22.png)  

- **表现3: ** 

- 当Container中没有设置 width 和 height 且没有子节点时, Container 会扩展到和父节点一样大

  > 即, 如果仅仅是一个Container, 则container 会和父节点一样大

  ```
  // Container中没有子节点, 也没有设置任何宽高信息, Contianer 占据的大小就是 父节点的大小
  class ContainerContent extends StatelessWidget {
  
    @override
    Widget build(BuildContext context) {
      return Container( // 父节点有多大, container 就多大
        color: Colors.green,
      );
    } 
  } 
  
  // Container中没有子节点
  // 只设置了高度信息,高度为 height所指定, 宽度就位父节点宽度
  class ContainerContent extends StatelessWidget {		
    @override
    Widget build(BuildContext context) {
        return Container( // 高度200, 宽和父节点一样高
          height: 200,
          color: Colors.green,
        );
      } 
  }
  
  // Container中没有子节点
  // 只设置了宽度信息,宽度为 width所指定, 高度就位父节点高度
  class ContainerContent extends StatelessWidget {
    @override Widget build(BuildContext context) {
      return Container( // 高度200, 宽和父节点一样高
        width: 200,
        color: Colors.green,
      );
  	}
  }
  ```
  
   ![](images/container_31.png) ![](images/container_32.png) ![](images/container_33.png) 



### 4、Container 布局总结

上面我们对flutter的布局流程原理以及Container 布局的几种常见情况都做了一些简单的介绍和示例, 其实还有一些其它情况这里就不介绍了, 后面用到再说. 

其实, 从前面几个Container 的布局情况我们可以发现一个特点, 就是 只要在Container内部能获取到 宽高相关的信息, 那么Container 在展示的时候就会按照已知的宽高信息来展示, 如果Container 没有获取到具体的宽高信息, 那么他就和父节点一样宽或这一样高



> 其实, 
>
> - 当我们在给Container 这个Widget 指定 `child` 元素时, 或者 设置 `width 、height`  或者设置 `constraints` 时, 都算是给Container 提供宽高信息. 
> - 只要Container 能拿到宽高信息, 它就会按照指定的宽高信息来展示, 否则就按照父元素的宽高来展示
>
> 这就是我在使用Container 是总结到的一些特点. 

**其实, Container的布局还远不止我们上面介绍的几种情况, 它还有 padding 属性, margin属性, alignment属性, 这些都会影响整个Container 的显示的, 后续我们再细讲**



### 5、Container 中的 padding、margin、 alignment属性



在Container中, 除了我们前面提到的 `width` 、`height` 、`constraints`、`child` 属性外, 还有 `padding` 、`margin` 和 `alignment` 属性. 这些都会影响我们的container 的显示以及所占据的位置的. 



### 6、Container 中BoxDecoration

圆角、阴影

Container 有一个非常重要的属性`decoration` , 它对应的是`Decoration` 类型, 不过他是抽象类我们不能直接用, 一般我们在开发中使用它的子类`BoxDecoration`

- BoxDecoration 常见属性

  ```
  const BoxDecoration({
      this.color, // 颜色，会和Container中的color属性冲突
      this.image, // 背景图片
      this.border, // 边框，对应类型是Border类型，里面每一个边框使用BorderSide
      this.borderRadius, // 圆角效果
      this.boxShadow, // 阴影效果
      this.gradient, // 渐变效果
      this.backgroundBlendMode, // 背景混合
      this.shape = BoxShape.rectangle, // 形变
    })
  ```

- 示例:

  ```
  class BoxDecotationContent extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return Center(
        child: Container(
          width: 150,
          height: 150,
          child: Icon(
            Icons.pets,
            size: 50,
          ),
          alignment: Alignment.center,
          decoration: BoxDecoration(
              color: Colors.amber,
  //          border: Border( // 单独设置边框
  //              top: BorderSide(  width: 2, style: BorderStyle.solid, color: Colors.red),
  //              left: BorderSide(  width: 2, style: BorderStyle.solid, color: Colors.green),
  //              bottom: BorderSide(  width: 2, style: BorderStyle.solid, color: Colors.blue),
  //              right: BorderSide(  width: 2, style: BorderStyle.solid, color: Colors.cyan)
  //          ),
              border: Border.all(
                  // 同时设置边框
                  width: 3,
                  color: Colors.redAccent,
                  style: BorderStyle.solid),
              borderRadius: BorderRadius.circular(
                  20) ,// 注意: 如果要同时设置边框和圆角时, 边框只能使用Border.all的方式设置
  //            shape: BoxShape.circle,  // shape 不能同时和borderRadius 同时用, 要冲突
              boxShadow: <BoxShadow>[ // 可以同时设置多个阴影
                BoxShadow(
                  offset: Offset(15,15),  // 阴影的偏移量
                  color: Colors.purple,
                  blurRadius: 5           // 阴影的模糊度
                ),
                BoxShadow(
                  offset: Offset(5,5),
                  color: Colors.green,
                  blurRadius: 3           // 阴影的模糊度
                )
  
              ],
            //渐变你色
            gradient: LinearGradient(
              colors: [
                Colors.red, Colors.orange,Colors.blue, Colors.yellow
              ]
            )
              ),
  
        ),
      );
    }
  }
  
  ```

  ![](images/containerboxdecoration1.png) 



### 7、实现圆角图片

前面我们提到可以通过 `Container+BoxDecoration`来实现圆角图像。

示例代码:

```
class CircleContainerContent extends StatelessWidget {
  String url =
      "https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=206669978,1648196901&fm=26&gp=0.jpg";

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: <Widget>[
        Center(
          child: Container(
            width: 120,
            height: 120,
            decoration: BoxDecoration(
                color: Colors.yellow,
                borderRadius: BorderRadius.circular(20),
                image: DecorationImage(
                    image: NetworkImage(url), fit: BoxFit.cover)),
          ),
        ),
        SizedBox(
          height: 30,
        ),
        Center(
          child: Container(
            width: 120,
            height: 120,
            decoration: BoxDecoration(
                image: DecorationImage(
                    image: NetworkImage(url), fit: BoxFit.cover),
                color: Colors.yellow,
                shape: BoxShape.circle),
          ),
        ),
      ],
    );
  }
}
```

![](images/ContainerCircle.png) 



## 3、多子布局

> 在开发中，我们经常需要将多个Widget放在一起进行布局，比如水平方向、垂直方向排列，甚至有时候需要他们进行层叠，比如图片上面放一段文字等；
>
> 这个时候我们需要使用多子布局组件（Multi-child layout widgets）。
>
> 比较常用的多子布局组件是Row、Column、Stack，我们来学习一下他们的使用。



### 1、Flex 组件

事实上, 我们即将学习的`Row` 组件和 `Column` 组件都继承自`Flex` 组件

- Flex 组件和 Row 、Column 组件的主要区别就是多了一个 direction属性
- 当direction属性的值为 Axis.horizontal的时候, 则为 Row
- 当direction属性的值为 Axis.vertical的时候, 则为column.

在学习Row和Column之前, 我们先学习一下`主轴` 和`交叉轴(侧轴)` 的概念

![](images/mainX.jpg) 

因为Row是一行排布的, Column是一列排布的, 那么他们都存在两个方向, 并且两个Widget排列的方向应该是对立的. 

不管是在`Row` 中, 还是在`Column` 中, 都存在主轴和交叉轴(侧轴) 的概念.

在Flex 布局中我们需要知道Row 和 Column 常用的几个属性: 

- `mainAxisAlignment` 主轴的排布方式
- `mainAxisSize` 主轴的大小
- `crossAxisAlignment` 侧轴的排布方式
- `textDirection` 文字的方向
- `verticalDirection` 主轴的方向
- `textBaseline` 基线的对齐方式

```
// 文字的方向
enum TextDirection {
 	rtl,
	ltr,
}

// 主轴的排布方式
enum MainAxisAlignment {
  start,
  end,
  spaceBetween,
  spaceAround,
  spaceEvenly,
}

// 交叉轴排布方式
enum CrossAxisAlignment {
  start,
  end,
  center,
  stretch,		// 每个子组件在交叉轴上 拉满父组件的 范围
  baseline,
}

// 主轴的排布方向
enum VerticalDirection {
  up,
	down,
}

// 基线对齐方式 (有文字时, 效果更明显)
enum TextBaseline {
  alphabetic,
	ideographic,
}

// 组件在主轴上占用的空间的大小
enum MainAxisSize {
  min,	// 主轴方向上占用尽量小的空间(包裹子组件内容)
  max,	// 主轴方向上占用尽量大的空间(一般是父组件有多大就占用多大)
}
```



### 2、Row 组件

> Row组件用于将所有的子Widget排成一行，实际上这种布局应该是借鉴于Web的Flex布局。
>
> 如果熟悉Flex布局，会发现非常简单。

Row 组件的特点:

- 水平方向尽可能占用比较大的空间
- 垂直方向尽量占用小比较小的空间(包裹内容)

```
Row(
  // Row默认情况下
  // 在水平会尽量占用较大的空间
  // 在垂直方向上会占用较小的空间(包裹子组件内容 )
  // 但是最终, 在主轴上占用较多的还是占用较少的空间, 我们可以通过 mainAxisSize 来控制
  children: <Widget>[
    Text('Row 的文字内容', style: (TextStyle(backgroundColor: Colors.green)),)
  ],
);

Row(
  // 我们可以通过 mainAxisSize 来控制, 主轴上占用的空间大小
  mainAxisSize: MainAxisSize.min,
  children: <Widget>[
    Text('Row 的文字内容', style: (TextStyle(backgroundColor: Colors.green)),)
  ],
);
```
![](images/row-max.png) ![](images/row-min.png) 



### 3、Column



### 4、可伸缩组件

`Flexible ` 和 `Expanded` 伸缩, 变大和变小



## 4、Stack 组件

在开发中 , 我们多个组件很有肯能需要重叠显示, 比如: 在一张图片上显示一个文字或者一个按钮

在Android 中可以使用 Frame来实现, 在web端可以使用绝对定位, 在flutter中我们需要使用层叠布局 Stack



### 1、Stack 介绍

```
import 'package:flutter/material.dart';
main(List<String> args){
  runApp(YRApp());
}


class YRApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: true,
      home: HomePage()
    );
  }
}


class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('我是标题'),
      ) ,
      body: StackContent(),
    ) ;

  }
}

class StackContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    /**
     * 1. 在我们开发中, Stack 默认的大小是包裹内容的, 也就是说在Stack 中最大的child 有多大, Stack就占据多大
     * 换句话说, 默认情况下Stack是包裹所有内容的
     * 2. 在Stack中所有的 child 是按照 数组children 中书写的顺序层第的, 后面的child盖在前面的child上面, 在Stack
     * 中是没有 网页中的Zindex 层叠顺序这一说法的, 如果要改变层叠顺序, 那么修改 数组children中的元素顺序即可
     * 3. 在Stack 中, 虽然我们能让所有的子组件之间出现层叠(一层盖一层)的效果, 我们也能控制子组件的显示位置, 但是我们
     * 只能通过alignment控制所有子组件的对齐方式, 不能单个的指定位置
     *4. 在Stack 中也有一个 fit 属性, 默认你情况下是 loose按照子组件默认的大小排布, 也可以是 expand 表示和父组件一样大表示的是拉伸
     * 如果Stack的fit 是StackFit.expand 的话, 所有的子元素都会被拉升到父组件的大小
     */
    return Stack(
      alignment: AlignmentDirectional.topCenter,
      fit: StackFit.expand,
      children: <Widget>[

        Container(
          width: 180,
          height: 100,
          color: Colors.cyan,
        ),
        Image.asset("asset/images/card@1x.png", width: 200,),
        Row(
          mainAxisSize: MainAxisSize.min,
          children: <Widget>[
          Text('wo shi wen ben ', style: TextStyle(backgroundColor: Colors.red),)
        ],)
      ],
    );
  }
}
```

- 在我们开发中, Stack 默认的大小是包裹内容的, 也就是说在Stack 中最大的child 有多大, Stack就占据多大,换句话说, 默认情况下Stack是包裹所有内容的
- 在Stack中所有的 child 是按照 数组children 中书写的顺序层第的, 后面的child盖在前面的child上面, 在Stack中是没有 网页中的Zindex 层叠顺序这一说法的, 如果要改变层叠顺序, 那么修改 数组children中的元素顺序即可
- 在Stack 中, 虽然我们能让所有的子组件之间出现层叠(一层盖一层)的效果, 我们也能控制子组件的显示位置, 但是我们只能通过alignment控制所有子组件的对齐方式, 不能单个的指定位置
- 在Stack 中也有一个 fit 属性, 默认你情况下是 loose按照子组件默认的大小排布, 也可以是 expand 表示和父组件一样大表示的是拉伸,如果Stack的fit 是StackFit.expand 的话, 所有的子元素都会被拉升到父组件的大小

```

import 'package:flutter/material.dart';
main(List<String> args){
  runApp(YRApp());
}


class YRApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: true,
      home: HomePage()
    );
  }
}


class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('我是标题'),
      ) ,
      body: StackContent(),
    ) ;

  }
}

class StackContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    /**
     * 1. 在我们开发中, Stack 默认的大小是包裹内容的, 也就是说在Stack 中最大的child 有多大, Stack就占据多大
     * 换句话说, 默认情况下Stack是包裹所有内容的
     * 2. 在Stack中所有的 child 是按照 数组children 中书写的顺序层第的, 后面的child盖在前面的child上面, 在Stack
     * 中是没有 网页中的Zindex 层叠顺序这一说法的, 如果要改变层叠顺序, 那么修改 数组children中的元素顺序即可
     * 3. 在Stack 中, 虽然我们能让所有的子组件之间出现层叠(一层盖一层)的效果, 我们也能控制子组件的显示位置, 但是我们
     * 只能通过alignment控制所有子组件的对齐方式, 不能单个的指定位置
     *4. 在Stack 中也有一个 fit 属性, 默认你情况下是 loose按照子组件默认的大小排布, 也可以是 expand 表示和父组件一样大表示的是拉伸
     * 如果Stack的fit 是StackFit.expand 的话, 所有的子元素都会被拉升到父组件的大小
     */
    return Stack(
      alignment: AlignmentDirectional.topCenter,
      fit: StackFit.expand,
      children: <Widget>[

        Container(
          width: 180,
          height: 100,
          color: Colors.cyan,
        ),
        Image.asset("asset/images/card@1x.png", width: 200,),
        Row(
          mainAxisSize: MainAxisSize.min,
          children: <Widget>[
          Text('wo shi wen ben ', style: TextStyle(backgroundColor: Colors.red),)
        ],)
      ],
    );
  }
}
```



#### 2、Stack 结合 Positon组件实现 层叠绝对定位

```

import 'package:flutter/material.dart';
main(List<String> args){
  runApp(YRApp());
}


class YRApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: true,
      home: HomePage()
    );
  }
}


class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('我是标题'),
      ) ,
      body: StackContent(),
    ) ;

  }
}

class StackContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    /**
     * 使用Stack 的正确姿势
     * 1. 使用一个设置的 宽高的Container 包裹Stack
     * 2. 设置Stack 的fit 属性为StackFit.expand 即将Stack 扩展为Container的大小
     * 3. Stack的children 属性中的所有子组件 均 使用 Position 组件包裹
     * 4. 在Position组件中 包裹上要显示的 具体组件即可, 比如: Text 或者 Image 等等
     */
    return Container(
      width: double.infinity,
      height: 200,
      color: Colors.green,
      child: Stack(
        fit: StackFit.expand,
        children: <Widget>[
          Positioned(
            left: 0,
            top: 0,
            child: Image.asset('asset/images/card@1x.png', width: 150,),
          ),
          Positioned(
            right: 0,
            bottom: 0,
            child: Text('我是 Stack 中的 position 中的text的文本',
              style: TextStyle(backgroundColor: Colors.orange),
            ),
          )
        ],
      ),
    );
  }
}
```

 

![](images/stackfit0.png)  



## 5、滚动的Widget

列表是移动端经常使用的一种视图展示方式, 在flutter中提供了 ListView 和 GridView



### 1、ListView  组件

> 移动端数据量比较大时，我们都是通过列表来进行展示的，比如商品数据、聊天列表、通信录、朋友圈等。
>
> 在Android中，我们可以使用ListView或RecyclerView来实现，在iOS中，我们可以通过UITableView来实现。
>
> 在Flutter中，我们也有对应的列表Widget，就是ListView。

创建ListView 通常有4种方式:

- 方式1: 默认构造方法:`ListView()` 

- 方式2: `ListView.builder()`

- 方式3: `ListView.separated()`

- 方式4: `ListView.custom()` 

#### 1、ListView 的基本使用

```
class ListViewContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView(
    	// List.generate 是一个数组构造函数, 可以构建一个指定数量的数组List
      children: List.generate(50, (index){
        return   Padding(
          padding: EdgeInsets.all(10),		// 为了让文字显示的更好看, 使用了padding 包裹
          child: Text('ListView 基本使用 $index'),
        );
      }),
    );
  }
}
```

![](images/listviewdemo1.png) 



#### 2、ListTile 的使用

在开发中, 我们经常见到一种列表, 有图标、有标题、副标题, 尾部还有图标, 这种样式, 我们可以使用flutter为我们提供的 `ListTile`

```
class ListTileContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView(
      children: List.generate(30, (index) {
        return ListTile(
        leading: Icon(Icons.people, size: 30,color: Colors.green,),
        title: Text('通讯录: $index') ,
        subtitle: Text('子标题'),
        trailing: Icon(Icons.delete, size: 15, color: Colors.red,),
        );
      }),
    );
  }
}
```

![](images/listviewdemo2.png) 



#### 3、ListView 实现水平滚动

我们在使用ListView时, 最多的应用场景是用来做垂直方向的列表, 但是我们也可以使用ListView 来实现水平的滚动

```
class ListViewHScrollContennt extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView(
      // 设置滚动方向
      scrollDirection: Axis.horizontal,
      // 设置行高(列宽)
      itemExtent: 200,
      
      children: List.generate(30, (index) {
        return ListTile(
          leading: Icon(
            Icons.people,
            size: 30,
            color: Colors.green,
          ),
          title: Text('通讯录: $index'),
          subtitle: Text('子标题'),
          trailing: Icon(
            Icons.delete,
            size: 15,
            color: Colors.red,
          ),
        );
      }),
    );
  }
}
```



#### 4、ListView.builder 的基本使用

我们在使用ListView时, 如果要显示的数量很少就可以直接使用ListView的默认构造方法`ListView()` 来实现, 但是如果数据量大了的话就不能直接使用默认的构造方法, 因为ListView在使用默认构造方法时时全量加载所有的子Widget, 不论显示与否, 当数据量很大的时候这是有很大的性能开销的. 

如果数据量大的话, 我们需要使用ListView另外的方法来实现, 一般我们使用 `ListView.builder()` , 在ListView.builder 中要求我们传递2个参数, 参数一是要显示的子组件的数量, 参数2是一个回调函数, 用来加载要显示的子组件.

```
class ListViewBuilderContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView.builder(
      itemCount: 30,
       
      // itemBuilder 是一个item的一个构造器, 将要显示某一行时才会加载某一行, 降低性能消耗
      itemBuilder:(BuildContext context, int index){
        return ListTile(
          leading: Icon(Icons.people, color: Colors.green,),
          title: Text('wo shi biaoti $index'),
          subtitle: Text('wo shi zi biaoti '),
          trailing: Icon(Icons.delete, color: Colors.red,),
        );
      }

    );
  }
}
```

![](images/listviewdemo3.png) 



#### 5、ListView.separated 的简单使用

`ListView.separated`可以生成列表项之间的分割器，它比`ListView.builder`多了一个`separatorBuilder`参数，该参数是一个分割器生成器。 你可以这样理解, 在ListView 中通过itemBuilder来构造一个个的要显示的item, 通过separatedBuilder 来构建一个个要显示的分割线

```
// 带分割线的 ListView
class ListViewSeparatedContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView.separated(
        itemCount: 50,
        
        // itemBuilder 是每一个item的构造函数, 用于显示每一行
        itemBuilder: (BuildContext context, int index) {
          return ListTile(
            leading: Icon(
              Icons.people,
              color: Colors.green,
            ),
            trailing: Icon(Icons.delete, color: Colors.red),
            title: Text('我是 ListViewSepatated 的 title'),
            subtitle: Text('我是 listViewSeparated 的 subtitle'),
          );
        },
        
        // separaterBuilder 是每一个分割线的构造函数, 用于显示分割线
        separatorBuilder: (BuildContext context, int index) {
          return Divider(  		// 我们可以使用 Divider 做分割线
            height: 1,
            thickness: 1,  		// 分割线的粗细
            color:  index % 2 == 0 ?  Colors.orange : Colors.green,
            indent: 30,     	// 前面缩进的距离
            endIndent: 30,  	// 尾部缩进的距离
          );
        });
  }
}
```

![](images/listviewdemo4.png) 



### 2、GridView

在我们flutter开发中, 我们除了可以使用ListView来实现表格的效果, 我们也可以使用GridView来实现类似的效果

GridView 主要有几个方法:

- `GridView()` 默认构造方法
- `GridView.count`
- `GridView.extent`
- `GridVeiw.builder` 



#### 1、GridView 默认构造函数的使用

一种使用GridView的方式就是使用构造函数来创建，和ListView对比有一个特殊的参数：`gridDelegate`

`gridDelegate`用于控制交叉轴的item数量或者宽度，需要传入的类型是SliverGridDelegate，但是它是一个抽象类，所以我们需要传入它的子类：**SliverGridDelegateWithFixedCrossAxisCount** 或 **SliverGridDelegateWithMaxCrossAxisExtent**



- 交叉轴上固定数量 的 item , 使用`SliverGridDelegateWithFixedCrossAxisCount` 

  > SliverGridDelegateWithFixedCrossAxisCount({
  >   @required double crossAxisCount, *// 交叉轴的item个数*
  >   double mainAxisSpacing = 0.0, *// 主轴的间距*
  >   double crossAxisSpacing = 0.0, *// 交叉轴的间距*
  >   double childAspectRatio = 1.0, *// 子Widget的宽高比*
  > })

  ```
  class GridViewContent extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return GridView(
  
        // 在gridView 中我们通过 gridDelegate 来控制交叉轴上子widget显示的数量
        // 以及子widget之间的间距
        gridDelegate:SliverGridDelegateWithFixedCrossAxisCount(
            crossAxisCount: 3, // 交叉轴上item的数量
            crossAxisSpacing: 10, // 交叉轴间距(列间距)
            mainAxisSpacing: 20,  // 主轴间距(行间距)
            childAspectRatio:1.5 // 子元素item的宽高比
        ) ,
  
        children: List.generate(30, (index) {
          return Container(
            alignment: Alignment.center,
            color: Color.fromARGB(255, Random().nextInt(255), Random().nextInt(255), Random().nextInt(255)),
            child: Text('index: $index'),
          );
        }),
      );
    }
  }
  ```

  ![](images/gridviewdemo1.png) 

- 交叉轴上使用非固定个数 item, 使用`SliverGridDelegateWithMaxCrossAxisExtent` 

  > SliverGridDelegateWithMaxCrossAxisExtent({
  >   double maxCrossAxisExtent, *// 交叉轴的item宽度*
  >   double mainAxisSpacing = 0.0, *// 主轴的间距*
  >   double crossAxisSpacing = 0.0, *// 交叉轴的间距*
  >   double childAspectRatio = 1.0, *// 子Widget的宽高比*
  > })

  ```
  class GridViewContent2 extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return GridView(
        gridDelegate: SliverGridDelegateWithMaxCrossAxisExtent(
            maxCrossAxisExtent: 200, // 交叉轴上最大的item宽度, 很多时候实际达不到这个宽度
            mainAxisSpacing: 20,
            crossAxisSpacing: 30,
            childAspectRatio: 3
        ),
        children: List.generate(30, (index) {
          return Container(
            alignment: Alignment.center,
            color: Color.fromARGB(255, Random().nextInt(255),
                Random().nextInt(255), Random().nextInt(255)),
            child: Text('index: $index'),
          );
        }),
      );
    }
  }
  ```

  ![](images/gridviewdemo2.png) 



**前面两种方式也可以不设置delegate**

可以分别使用：`GridView.count构造函数`和`GridView.extent`构造函数实现相同的效果，这里不再赘述。



#### 2、GridView.build

和ListView一样，使用默认构造函数会一次性创建所有的子Widget，会带来性能问题，所以我们可以使用`GridView.build`来交给GridView自己管理需要创建的子Widget。

```
class GridViewBuildContent extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GridView.builder(
        gridDelegate:
        SliverGridDelegateWithFixedCrossAxisCount(
            crossAxisCount: 3,
            crossAxisSpacing: 3,
            mainAxisSpacing: 5
        ),
        itemBuilder: (BuildContext ctx, index) {
          return Container(
            alignment: Alignment.center,
            color: Colors.orange,
            child: ListTile(
              leading: Icon(Icons.people),
              title: Text(
                  'index: $index'
              ),
            ),
          );
        }
    );
  }
}
```





### 3、Slivers的基本使用

因为我们需要把很多的Slivers 放在一个CustomScrollView中, 所以CustomScrollView有一个slivers属性,里面让我们放对应的一些sliver

- `SliverList` 类似于我们之前使用过的ListView
- `SliverFixedExtentList` 类似于SliverList, 只是可以设置滚动的高度
- `SliverGrid` 类似于我们之前使用过的GridView
- `SliverPadding` 设置Sliver的内边距, 因为可能要单独给sliver设置内边距
- `SliverAppBar` 添加一个AppBar, 通常用来作为CustomScrollView和headerView
- `SliverSafeArea` 设置内容显示在安全区域 ( 比如: 不让齐刘海挡住我们的内容)

下面我们简单演示一下, Sliver + SliverPadding+SliverSafeArea 的组合

`Scaffold` 类似于控制器

`SafeArea` 安全区域

`SliverSafeArea`  sliver的安全区域

`SliverPadding` 给sliver的滑动内容增加内边距



## 6、监听滚动







# 十四、异步&网络请求



## 1、Dart 是单线程的



### 1、程序中的耗时操作

- **开发中的耗时操作**:

  网络请求、文件的读取都是属于耗时操作, 如果所有的耗时操作都放到主线程执行的话, 主线程是会被阻塞的, 带给用户的体验就是卡顿和没有反应, 这是不行的. 

  

- **如何处理耗时操作**:

  针对如果处理耗时操作, 不同的语言有不同的处理方式.

  - **方式一: ** 多线程

    比如: java、C++、C语言、OC 等, 我们普遍的做法是开启一个新的线程(`thread`), 在新开启的线程中做耗时操作, 耗时操作完毕后再通过线程之间的通信, 将结果给到对应的线程(`一般是主线程`)继续处理.

  - **方式二**:单线程 + 事件循环

    比如: javaScript 和 Dart 都是采用单线程+事件循环来处理耗时操作. 那么单线程+事件循环是如何处理耗时操作的, 我们下面会讲解. 

    

### 2、Dart的异步操作 Future

> 说明:
>
> 1. 因为Dart是单线程的, 因此在Dart开发中或者在flutter开发中不会存在像其他语言(比如: java/C++/C)中说的主线程与子线程的说法.即在Dart中只有主线程, 所有的方法都是在主线程中执行的
> 2. 因为在Dart中只有主线程没有子线程的说法, 为了保证在Dart开发中程序不会因为耗时操作(比如: 文件的读取, 网络请求)而阻塞, 在Dart开发中引入了异步的概念. 换句话说在Dart开发中凡是涉及到耗时的操作我们都需要放到异步中来执行, 执行完后再通过回调返回结果.
> 3. 为了更好的在Dart中使用异步, 引入了Future的概念. 所有的耗时操作都需要使用 Future来进行包装处理.

**Dart 中Future 的使用步骤大致是这样的:** 

- 使用`Future` 进行耗时操作封装(`future`成功的耗时封装, 异常的耗时封装)

- 使用 `future.then()` 对耗时操作的结果进行处理

- 使用`future.then().catchError()`  对耗时操作中产生的 异常或者错误结果进行处理

- 使用`future.then().catchError().whenComplete()` 完成异步的收尾工作  **(推荐)**

  或者 使用 `future.catchError().whenComplete()` 完成异步的收尾工作**(推荐)** 

  或者使用`future.then().whenComplete()` 完成异步的收尾工作 **(不推荐, 有异常风险)**

  也可以使用 `future.whenComplete() 完成异步的收尾工作  **(不推荐, 有异常风险)** 

```
// 异步操作的封装
int i = 0;
Future<String> getNetworkData3(){

  return Future<String>((){
    sleep(Duration(seconds: 5));
    if(i < 2){
      i ++;
      //  reture 返回的结果需要通过 future.then 来获取
      //  可以给future 使用泛型约束 return 返回的数据类型, 这样外面在.then 中可以直接使用对应的数据类型
      return '异步操作 成功完成 $i';
    }
  // 当程序出错时, 需要通过 throw Exceptionn 的方式将 异常抛出, 外面需要使用 future.catchError 来接收
  throw Exception('future 抛出异常');
  });
}
```



```
// 异步操作的调用哪个
FlatButton(
  color: Colors.orange,
  child: Text('future 最完整写法'),
  onPressed: (){
	  print('\n\n');
    print('future 最完整写法 发出异步任务开始');
    Future<String> future = getNetworkData3();
    future.then((String rst){
      print('成功结果: $rst');
    }).catchError((error){
      // future 抛出异常 来到这里
      print('异常错误: $error');
    }).whenComplete((){
      // 不论前面的 future 是正常执行还是异常执行, 只要future 完成就会来到这里
      print('future 最完整写法 future 结束了');
    });
    print('future 最完整写法 发出异步任务完成');
  },
 );
```

![](images/future1.png) 




