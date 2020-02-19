# 欢迎来到Flutter入门体验:

- [安装Flutter框架](#安装Flutter框架)
- [编辑器设置](#编辑器设置)
- [创建，运行并更改第一个Flutter应用程序](#创建，运行并更改第一个Flutter应用程序)
- [编写第一个Flutter应用](#编写第一个Flutter应用)

# [安装Flutter框架](#安装Flutter框架)
*   [使用镜像](#使用镜像)
*   [系统要求](#系统要求)
*   [获取Flutter SDK](#获取flutter-sdk)
    *   [更新环境变量](#更新环境变量)
    *   [运行 flutter doctor](#运行-flutter-doctor)
# [编辑器设置](#编辑器设置)
*   [Android设置](#android设置)
    *   [安装Android Studio](#安装android-studio)
    *   [安装Visual-Studio-Code](#安装Visual-Studio-Code)
    *   [设置Android设备](#设置android设备)
    *   [设置Android模拟器](#设置android模拟器)
# [创建，运行并更改第一个Flutter应用程序](#创建，运行并更改第一个Flutter应用程序)
*   [创建新应用](#创建新应用)
*   [运行应用程序](#运行应用程序)
*   [体验热重载](#体验热重载)
# [编写第一个Flutter应用](#编写第一个Flutter应用)
*   [第1步: 创建 Flutter app](#创建Flutter-app)
*   [第2步: 使用外部包(package)](#使用外部包)
*   [第3步: 添加一个 有状态的部件（Stateful widget）](#添加一个有状态的部件)
*   [第4步: 创建一个无限滚动ListView](#创建一个无限滚动ListView)
*   [第5步: 添加交互](#添加交互)
*   [第6步: 导航到新页面](#导航到新页面)
*   [第7步：使用主题更改UI](#使用主题更改UI)



## 使用镜像

由于在国内访问Flutter有时可能会受到限制，Flutter官方为中国开发者搭建了临时镜像，大家可以将如下环境变量加入到用户环境变量中：

<div class="highlighter-rouge">

<div class="highlight">

    export PUB_HOSTED_URL=https://pub.flutter-io.cn
    export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn

</div>

</div>

**注意：** 此镜像为临时镜像，并不能保证一直可用，读者可以参考详情请参考 [Using Flutter in China](https://github.com/flutter/flutter/wiki/Using-Flutter-in-China) 以获得有关镜像服务器的最新动态。

## 系统要求

要安装并运行Flutter，开发环境必须满足以下最低要求:

*   **操作系统**: Windows 7 或更高版本 (64-bit)
*   **磁盘空间**: 400 MB (不包括Android Studio的磁盘空间).
*   **工具**: Flutter 依赖下面这些命令行工具.
    *   [Git for Windows](https://git-scm.com/download/win) (Git命令行工具)

        如果已安装Git for Windows，请确保命令提示符或PowerShell中运行 `git` 命令，不然在后面运行`flutter doctor`时将出现`Unable to find git in your PATH`错误, 此时需要手动添加`C:\Program Files\Git\bin`至`Path`系统环境变量中。

## 获取Flutter SDK

1.  去flutter官网下载其最新可用的安装包，[点击下载](https://flutter.io/sdk-archive/#windows) ；

    注意，Flutter的渠道版本会不停变动，请以Flutter官网为准。另外，在中国大陆地区，要想正常获取安装包列表或下载安装包，可能需要翻墙，读者也可以去Flutter github项目下去[下载安装包](https://github.com/flutter/flutter/releases) 。

2.  将安装包zip解压到你想安装Flutter SDK的路径（如：`C:\src\flutter`；注意，**不要**将flutter安装到需要一些高权限的路径如`C:\Program Files\`）。

3.  在Flutter安装目录的`flutter`文件下找到`flutter_console.bat`，双击运行并启动**flutter命令行**，接下来，你就可以在Flutter命令行运行flutter命令了。

<div class="alert alert-info" style="margin-top:-5px">

**注意：** 由于一些`flutter`命令需要联网获取数据，如果是在国内访问，由于众所周知的原因，直接访问很可能不会成功。 上面的`PUB_HOSTED_URL`和`FLUTTER_STORAGE_BASE_URL`是google为国内开发者搭建的临时镜像。详情请参考 [Using Flutter in China](https://github.com/flutter/flutter/wiki/Using-Flutter-in-China)

</div>

上述命令为当前终端窗口临时设置PATH变量。要将Flutter永久添加到路径中，请参阅[更新路径](#更新环境变量)。

要更新现有版本的Flutter，请参阅[升级Flutter](#升级Flutter)。

### 更新环境变量

要在终端运行 `flutter` 命令， 你需要添加以下环境变量到系统PATH：

*   转到 “控制面板>用户帐户>用户帐户>更改我的环境变量”
*   在“用户变量”下检查是否有名为“Path”的条目:
    *   如果该条目存在, 追加 `flutter\bin`的全路径，使用 `;` 作为分隔符.
    *   如果条目不存在, 创建一个新用户变量 `Path` ，然后将 `flutter\bin`的全路径作为它的值.
*   在“用户变量”下检查是否有名为”PUB_HOSTED_URL”和”FLUTTER_STORAGE_BASE_URL”的条目，如果没有，也添加它们。

重启Windows以应用此更改

### 运行 flutter doctor

打开一个新的命令提示符或PowerShell窗口并运行以下命令以查看是否需要安装任何依赖项来完成安装：

     flutter doctor

在命令提示符或PowerShell窗口中运行此命令。目前，Flutter不支持像Git Bash这样的第三方shell。

该命令检查环境并在终端窗口中显示报告。Dart SDK已经在捆绑在Flutter里了，没有必要单独安装Dart。 仔细检查命令行输出以获取可能需要安装的其他软件或进一步需要执行的任务（以粗体显示）

例如:

<pre>[-] Android toolchain - develop for Android devices
    • Android SDK at D:\Android\sdk
    **✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ**
    • Try re-installing or updating your Android SDK,
      visit https://flutter.io/setup/#android-setup for detailed instructions.
</pre>

第一次运行一个flutter命令（如flutter doctor）时，它会下载它自己的依赖项并自行编译。以后再运行就会快得多。

以下各部分介绍如何执行这些任务并完成设置过程。你会看到在`flutter doctor`输出中， 如果你选择使用IDE，我们提供了，IntelliJ IDEA，Android Studio和VS Code的插件， 请参阅[编辑器设置](#编辑器设置) 以了解安装Flutter和Dart插件的步骤。

一旦你安装了任何缺失的依赖，再次运行`flutter doctor`命令来验证你是否已经正确地设置了。

该flutter工具使用Google Analytics匿名报告功能使用情况统计信息和基本崩溃报告。 这些数据用于帮助改进Flutter工具。Analytics不是一运行或在运行涉及`flutter config`的任何命令时就发送， 因此可以在发送任何数据之前退出分析。要禁用报告，请执行`flutter config --no-analytics`并显示当前设置，然后执行`flutter config`。 请参阅[Google的隐私政策](https://www.google.com/intl/en/policies/privacy/)。

## 编辑器设置

使用 `flutter` 命令行工具，可以使用任何编辑器来开发Flutter应用程序。输入`flutter help`在提示符下查看可用的工具。

## Android设置

### 安装Android Studio

要为Android开发Flutter应用，可以使用Mac，Windows或Linux（64位）机器.

Flutter需要安装和配置Android Studio:

1.  下载并安装 [Android Studio](https://developer.android.com/studio/index.html).

2.  启动Android Studio，然后执行“Android Studio安装向导”。这将安装最新的Android SDK，Android SDK平台工具和Android SDK构建工具，这是Flutter为Android开发时所必需的

需要安装两个插件:
1.  Flutter插件： 支持Flutter开发工作流 (运行、调试、热重载等)
2.  Dart插件： 提供代码分析 (输入代码时进行验证、代码补全等)

要安装这些:
1.  启动Android Studio
2.  打开插件首选项 (Preferences>Plugins on macOS, File>Settings>Plugins on Windows & Linux)
3.  选择 Browse repositories…, 选择 Flutter 插件并点击 install
4.  重启Android Studio后插件生效

### 安装Visual-Studio-Code
VS Code: 轻量级编辑器，支持Flutter运行和调试.

### 安装 VS Code

*   [VS Code](https://code.visualstudio.com/), 安装1.20.1或更高版本.

### 安装Flutter插件

1.  启动 VS Code
2.  调用 **View>Command Palette…**
3.  输入 ‘install’, 然后选择 **Extensions: Install Extension** action
4.  在搜索框输入 `flutter` , 在搜索结果列表中选择 ‘Flutter’, 然后点击 **Install**
5.  选择 ‘OK’ 重新启动 VS Code

## 通过Flutter Doctor验证设置

1.  调用 **View>Command Palette…**
2.  输入 ‘doctor’, 然后选择 **‘Flutter: Run Flutter Doctor’** action
3.  查看“OUTPUT”窗口中的输出是否有问题

### 设置Android设备

要准备在Android设备上运行并测试Flutter应用，需要安装Android 4.1（API level 16）或更高版本的Android设备.

1.  在设备上启用 **开发人员选项** 和 **USB调试** 。详细说明可在[Android文档](https://developer.android.com/studio/debug/dev-options.html)中找到。
2.  使用USB将手机插入电脑。如果设备出现提示，请授权计算机访问设备。
3.  在终端中，运行 `flutter devices` 命令以验证Flutter识别连接的Android设备。
4.  运行启动应用程序 `flutter run`。

默认情况下，Flutter使用的Android SDK版本是基于你的 `adb` 工具版本。 如果想让Flutter使用不同版本的Android SDK，则必须将该 `ANDROID_HOME` 环境变量设置为SDK安装目录。

### 设置Android模拟器

要准备在Android模拟器上运行并测试Flutter应用，请按照以下步骤操作：

1.  在机器上启用 [VM acceleration](https://developer.android.com/studio/run/emulator-acceleration.html) .
2.  启动 **Android Studio>Tools>Android>AVD Manager** 并选择 **Create Virtual Device**.
3.  选择一个设备并选择 **Next**。
4.  为要模拟的Android版本选择一个或多个系统映像，然后选择 **Next**. 建议使用 _x86_ 或 _x86_64_ image .
5.  在 Emulated Performance下, 选择 **Hardware - GLES 2.0** 以启用 [硬件加速](https://developer.android.com/studio/run/emulator-acceleration.html).
6.  验证AVD配置是否正确，然后选择 **Finish**。

    有关上述步骤的详细信息，请参阅 [Managing AVDs](https://developer.android.com/studio/run/managing-avds.html).

7.  在 Android Virtual Device Manager中, 点击工具栏的 **Run**。模拟器启动并显示所选操作系统版本或设备的启动画面.
8.  运行 `flutter run` 启动设备. 连接的设备名是 `Android SDK built for <platform>`,其中 _platform_ 是芯片系列, 如 x86.

## 创建，运行并更改第一个Flutter应用程序

## 创建新应用

1.  选择 **File>New Flutter Project**
2.  选择 **Flutter application** 作为 project 类型, 然后点击 Next
3.  输入项目名称 (如 `myapp`), 然后点击 Next
4.  点击 **Finish**
5.  等待Android Studio安装SDK并创建项目.

上述命令创建一个Flutter项目，项目名为myapp，其中包含一个使用[Material 组件](https://material.io/guidelines/)的简单演示应用程序。

在项目目录中，应用程序的代码位于 `lib/main.dart`.

## 运行应用程序

1.  定位到Android Studio 工具栏:  
    ![Main IntelliJ toolbar](https://flutterchina.club/images/intellij/main-toolbar.png)
2.  在 **target selector** 中, 选择一个运行该应用的Android设备. 如果没有列出可用，请选择 **Tools>Android>AVD Manager** 并在那里创建一个
3.  在工具栏中点击 **Run图标**, 或者调用菜单项 **Run > Run**.
4.  如果一切正常, 应该在设备或模拟器上会看到启动的应用程序:  
    ![Starter App on Android](https://flutterchina.club/images/flutter-starter-app-android.png)

## 体验热重载

Flutter 可以通过 _热重载（hot reload）_ 实现快速的开发周期，热重载就是无需重启应用程序就能实时加载修改后的代码，并且不会丢失状态（译者语:如果是一个web开发者，那么可以认为这和webpack的热重载是一样的）。简单的对代码进行更改，然后告诉IDE或命令行工具你需要重新加载（点击reload按钮），你就会在你的设备或模拟器上看到更改。

1.  将字符串  
    `'You have pushed the button this many times:'` 更改为  
    `'You have clicked the button this many times:'`
2.  不要按“Stop”按钮; 让应用继续运行。
3.  要查看更改, 只需调用 **Save All** (`cmd-s` / `ctrl-s`), 或点击 **热重载按钮** (带有闪电⚡️图标的按钮).

你就会立即看到更新后的字符串。

## 编写第一个Flutter应用

## 创建Flutter-app
创建一个简单的、基于模板的Flutter应用程序，按照[创建第一个Flutter应用](#创建新应用)中的指南的步骤， 然后将项目命名为startup_namer（而不是myapp)，接下来你将会修改这个应用来完成最终的APP。

在这个示例中，你将主要编辑Dart代码所在的 **lib/main.dart** 文件,

<aside class="alert alert-success">

**提示:** 将代码粘贴到应用中时，缩进可能会变形。可以使用Flutter工具自动修复此问题:

*   Android Studio / IntelliJ IDEA: 右键单击Dart代码，然后选择 **Reformat Code with dartfmt**.
*   VS Code: 右键单击并选择 **Format Document**.
*   Terminal: 运行 `flutter format <filename>`.

</aside>

1.  替换 lib/main.dart.  
    删除lib / main.dart中的所有代码，然后替换为下面的代码，它将在屏幕的中心显示“Hello World”.

    <div class="language-dart highlighter-rouge">

    <div class="highlight">

        import 'package:flutter/material.dart';

        void main() => runApp(new MyApp());

        class MyApp extends StatelessWidget {
          @override
          Widget build(BuildContext context) {
            return new MaterialApp(
              title: 'Welcome to Flutter',
              home: new Scaffold(
                appBar: new AppBar(
                  title: new Text('Welcome to Flutter'),
                ),
                body: new Center(
                  child: new Text('Hello World'),
                ),
              ),
            );
          }
        }

    </div>

    </div>

2.  运行应用程序，你应该看到如下界面.

    <div style="text-align:center"><img src="https://flutterchina.club/get-started/codelab/images/hello-world-screenshot.png" /></div>

*   本示例创建一个Material APP。[Material](https://material.io/guidelines/)是一种标准的移动端和web端的视觉设计语言。 Flutter提供了一套丰富的Material widgets。

*   main函数使用了(`=>`)符号, 这是Dart中单行函数或方法的简写。

*   该应用程序继承了 StatelessWidget，这将会使应用本身也成为一个widget。 在Flutter中，大多数东西都是widget，包括对齐(alignment)、填充(padding)和布局(layout)

*   Scaffold 是 Material library 中提供的一个widget, 它提供了默认的导航栏、标题和包含主屏幕widget树的body属性。widget树可以很复杂。

*   widget的主要工作是提供一个build()方法来描述如何根据其他较低级别的widget来显示自己。

*   本示例中的body的widget树中包含了一个Center widget, Center widget又包含一个 Text 子widget。 Center widget可以将其子widget树对其到屏幕中心。

## 使用外部包

在这一步中，我们将开始使用一个名为english_words的开源软件包 ，其中包含数千个最常用的英文单词以及一些实用功能.

可以 在[pub.dartlang.org](https://pub.dartlang.org/flutter/)上找到[english_words](https://pub.dartlang.org/packages/english_words)软件包以及其他许多开源软件包

1.  pubspec文件管理Flutter应用程序的assets(资源，如图片、package等)。 在pubspec.yaml中，将english_words（3.1.0或更高版本）添加到依赖项列表，如下面高亮显示的行：

        dependencies:
          flutter:
            sdk: flutter

          cupertino_icons: ^0.1.0
          english_words: ^3.1.0

2.  在Android Studio的编辑器视图中查看pubspec时，单击右上角的 **Packages get**，这会将依赖包安装到项目。可以在控制台中看到以下内容：

        flutter packages get
        Running "flutter packages get" in startup_namer...
        Process finished with exit code 0

3.  在 **lib/main.dart** 中, 引入 `english_words`, 如高亮显示的行所示:

        import 'package:flutter/material.dart';
        import 'package:english_words/english_words.dart';

    在输入时，Android Studio会为提供有关库导入的建议。然后它将呈现灰色的导入字符串，让知道导入的库尚未使用（到目前为止）

4.  使用 English words 包生成文本来替换字符串“Hello World”.

    <aside class="alert alert-success">

    **Tip:** “驼峰命名法” (称为 “upper camel case” 或 “Pascal case” ), 表示字符串中的每个单词（包括第一个单词）都以大写字母开头。所以，“uppercamelcase” 变成 “UpperCamelCase”

    </aside>

    进行以下更改, 如高亮部分所示:

        import 'package:flutter/material.dart';
        import 'package:english_words/english_words.dart';

        void main() => runApp(new MyApp());

        class MyApp extends StatelessWidget {
          @override
          Widget build(BuildContext context) {
            final wordPair = new WordPair.random();
            return new MaterialApp(
              title: 'Welcome to Flutter',
              home: new Scaffold(
                appBar: new AppBar(
                  title: new Text('Welcome to Flutter'),
                ),
                body: new Center(
                  //child: new Text('Hello World'),
                  child: new Text(wordPair.asPascalCase),
                ),
              ),
            );
          }
        }

5.  如果应用程序正在运行，请使用热重载按钮 (![lightning bolt icon](https://flutterchina.club/get-started/codelab/images/hot-reload-button.png)) 更新正在运行的应用程序。每次单击热重载或保存项目时，都会在正在运行的应用程序中随机选择不同的单词对。 这是因为单词对是在 `build` 方法内部生成的。每次MaterialApp需要渲染时或者在Flutter Inspector中切换平台时 `build` 都会运行.

    <div style="text-align:center"><img src="https://flutterchina.club/get-started/codelab/images/step2-screenshot.png" /></div>

## 添加一个有状态的部件
State_less_ widgets 是不可变的, 这意味着它们的属性不能改变 - 所有的值都是最终的.

State_ful_ widgets 持有的状态可能在widget生命周期中发生变化. 实现一个 stateful widget 至少需要两个类:

1.  一个 StatefulWidget类。
2.  一个 State类。 StatefulWidget类本身是不变的，但是 State类在widget生命周期中始终存在.

在这一步中，将添加一个有状态的widget-RandomWords，它创建其State类RandomWordsState。State类将最终为widget维护建议的和喜欢的单词对。

1.  添加有状态的 RandomWords widget 到 main.dart。 它也可以在MyApp之外的文件的任何位置使用，但是本示例将它放到了文件的底部。RandomWords widget除了创建State类之外几乎没有其他任何东西

        class RandomWords extends StatefulWidget {
          @override
          createState() => new RandomWordsState();
        }

2.  添加 RandomWordsState 类.该应用程序的大部分代码都在该类中， 该类持有RandomWords widget的状态。这个类将保存随着用户滚动而无限增长的生成的单词对， 以及喜欢的单词对，用户通过重复点击心形 ❤️ 图标来将它们从列表中添加或删除。

    你会一步一步地建立这个类。首先，通过添加高亮显示的代码创建一个最小类

        class RandomWordsState extends State<RandomWords> {
        }

3.  在添加状态类后，IDE会提示该类缺少build方法。接下来，将添加一个基本的build方法，该方法通过将生成单词对的代码从MyApp移动到RandomWordsState来生成单词对。

    将build方法添加到RandomWordState中，如下面高亮代码所示

        class RandomWordsState extends State<RandomWords> {
          @override
          Widget build(BuildContext context) {
            final wordPair = new WordPair.random();
            return new Text(wordPair.asPascalCase);
          }
        }

4.  通过下面高亮显示的代码，将生成单词对代的码从MyApp移动到RandomWordsState中

        class MyApp extends StatelessWidget {
          @override
          Widget build(BuildContext context) {
            final wordPair = new WordPair.random();  // 删除此行

            return new MaterialApp(
              title: 'Welcome to Flutter',
              home: new Scaffold(
                appBar: new AppBar(
                  title: new Text('Welcome to Flutter'),
                ),
                body: new Center(
                  //child: new Text(wordPair.asPascalCase),
                  child: new RandomWords(),
                ),
              ),
            );
          }
        }

重新启动应用程序。如果尝试热重载，则可能会看到一条警告：

    Reloading...
    Not all changed program elements ran during view reassembly; consider
    restarting.

这可能是误报，但考虑到重新启动可以确保更改在应用界面中生效。

应用程序应该像之前一样运行，每次热重载或保存应用程序时都会显示一个单词对。

<div style="text-align:center"><img src="https://flutterchina.club/get-started/codelab/images/step3-screenshot.png" /></div>

## 创建一个无限滚动ListView
在这一步中，将扩展（继承）RandomWordsState类，以生成并显示单词对列表。 当用户滚动时，ListView中显示的列表将无限增长。 ListView的`builder`工厂构造函数允许按需建立一个懒加载的列表视图。

1.  向RandomWordsState类中添加一个`_suggestions`列表以保存建议的单词对。 该变量以下划线（_）开头，在Dart语言中使用下划线前缀标识符，会强制其变成私有的。

    另外，添加一个`biggerFont`变量来增大字体大小

        class RandomWordsState extends State<RandomWords> {
          final _suggestions = <WordPair>[];

          final _biggerFont = const TextStyle(fontSize: 18.0);
          ...
        }

2.  向RandomWordsState类添加一个 `_buildSuggestions()` 函数. 此方法构建显示建议单词对的ListView。

    ListView类提供了一个builder属性，`itemBuilder` 值是一个匿名回调函数， 接受两个参数- BuildContext和行迭代器`i`。迭代器从0开始， 每调用一次该函数，`i`就会自增1，对于每个建议的单词对都会执行一次。该模型允许建议的单词对列表在用户滚动时无限增长。

    添加如下高亮的行:

        class RandomWordsState extends State<RandomWords> {
          ...
          Widget _buildSuggestions() {
            return new ListView.builder(
              padding: const EdgeInsets.all(16.0),
              // 对于每个建议的单词对都会调用一次itemBuilder，然后将单词对添加到ListTile行中
              // 在偶数行，该函数会为单词对添加一个ListTile row.
              // 在奇数行，该函数会添加一个分割线widget，来分隔相邻的词对。
              // 注意，在小屏幕上，分割线看起来可能比较吃力。
              itemBuilder: (context, i) {
                // 在每一列之前，添加一个1像素高的分隔线widget
                if (i.isOdd) return new Divider();

                // 语法 "i ~/ 2" 表示i除以2，但返回值是整形（向下取整），比如i为：1, 2, 3, 4, 5
                // 时，结果为0, 1, 1, 2, 2， 这可以计算出ListView中减去分隔线后的实际单词对数量
                final index = i ~/ 2;
                // 如果是建议列表中最后一个单词对
                if (index >= _suggestions.length) {
                  // ...接着再生成10个单词对，然后添加到建议列表
                  _suggestions.addAll(generateWordPairs().take(10));
                }
                return _buildRow(_suggestions[index]);
              }
            );
          }
        }

3.  对于每一个单词对，`_buildSuggestions`函数都会调用一次`_buildRow`。 这个函数在ListTile中显示每个新词对，这使在下一步中可以生成更漂亮的显示行

    在RandomWordsState中添加一个`_buildRow`函数 :

        class RandomWordsState extends State<RandomWords> {
          ...

          Widget _buildRow(WordPair pair) {
            return new ListTile(
              title: new Text(
                pair.asPascalCase,
                style: _biggerFont,
              ),
            );
          }
        }

4.  更新RandomWordsState的build方法以使用`_buildSuggestions()`，而不是直接调用单词生成库。 更改后如下面高亮部分：

        class RandomWordsState extends State<RandomWords> {
          ...
          @override
          Widget build(BuildContext context) {
            final wordPair = new WordPair.random(); // 删除这两行
            return new Text(wordPair.asPascalCase);
            return new Scaffold (
              appBar: new AppBar(
                title: new Text('Startup Name Generator'),
              ),
              body: _buildSuggestions(),
            );
          }
          ...
        }

5.  更新MyApp的build方法。从MyApp中删除Scaffold和AppBar实例。 这些将由RandomWordsState管理，这使得用户在下一步中从一个屏幕导航到另一个屏幕时， 可以更轻松地更改导航栏中的的路由名称。

    用下面高亮部分替换最初的build方法：

        class MyApp extends StatelessWidget {
          @override
          Widget build(BuildContext context) {
            return new MaterialApp(
              title: 'Startup Name Generator',
              home: new RandomWords(),
            );
          }
        }

重新启动应用程序。你应该看到一个单词对列表。尽可能地向下滚动，将继续看到新的单词对。

<div style="text-align:center"><img src="https://flutterchina.club/get-started/codelab/images/step4-screenshot.png" /></div>

## 添加交互
在这一步中，将为每一行添加一个可点击的心形 ❤️ 图标。当用户点击列表中的条目，切换其“收藏”状态时，将该词对添加到或移除出“收藏夹”。

1.  添加一个 `_saved` Set(集合) 到RandomWordsState。这个集合存储用户喜欢（收藏）的单词对。 在这里，Set比List更合适，因为Set中不允许重复的值。

        class RandomWordsState extends State<RandomWords> {
          final _suggestions = <WordPair>[];

          final _saved = new Set<WordPair>();

          final _biggerFont = const TextStyle(fontSize: 18.0);
          ...
        }

2.  在 `_buildRow` 方法中添加 `alreadySaved`来检查确保单词对还没有添加到收藏夹中。

        Widget _buildRow(WordPair pair) {
          final alreadySaved = _saved.contains(pair);
          ...
        }

3.  同时在 `_buildRow()`中， 添加一个心形 ❤️ 图标到 ListTiles以启用收藏功能。接下来，你就可以给心形 ❤️ 图标添加交互能力了。

    添加下面高亮的行:

        Widget _buildRow(WordPair pair) {
          final alreadySaved = _saved.contains(pair);
          return new ListTile(
            title: new Text(
              pair.asPascalCase,
              style: _biggerFont,
            ),
            trailing: new Icon(
              alreadySaved ? Icons.favorite : Icons.favorite_border,
              color: alreadySaved ? Colors.red : null,
            ),
          );
        }

4.  重新启动应用。你现在可以在每一行看到心形❤️图标️，但它们还没有交互。

5.  在 `_buildRow`中让心形❤️图标变得可以点击。如果单词条目已经添加到收藏夹中， 再次点击它将其从收藏夹中删除。当心形❤️图标被点击时，函数调用`setState()`通知框架状态已经改变。

    添加如下高亮的行:

        Widget _buildRow(WordPair pair) {
          final alreadySaved = _saved.contains(pair);
          return new ListTile(
            title: new Text(
              pair.asPascalCase,
              style: _biggerFont,
            ),
            trailing: new Icon(
              alreadySaved ? Icons.favorite : Icons.favorite_border,
              color: alreadySaved ? Colors.red : null,
            ),
            onTap: () {
              setState(() {
                if (alreadySaved) {
                  _saved.remove(pair);
                } else {
                  _saved.add(pair);
                }
              });
            },
          );
        }

<aside class="alert alert-success">

**提示:** 在Flutter的响应式风格的框架中，调用`setState()` 会为State对象触发`build()`方法，从而导致对UI的更新

</aside>

热重载你的应用。你就可以点击任何一行收藏或移除。请注意，点击一行时会生成从心形 ❤️ 图标发出的水波动画


<div style="text-align:center"><img src="https://flutterchina.club/get-started/codelab/images/step5-screenshot.png" /></div>

## 导航到新页面
在这一步中，将添加一个显示收藏夹内容的新页面（在Flutter中称为路由(route)）。将学习如何在主路由和新路由之间导航（切换页面）。

在Flutter中，导航器管理应用程序的路由栈。将路由推入（push）到导航器的栈中，将会显示更新为该路由页面。 从导航器的栈中弹出（pop）路由，将显示返回到前一个路由。

1.  在RandomWordsState的build方法中为AppBar添加一个列表图标。当用户点击列表图标时，包含收藏夹的新路由页面入栈显示。

    <aside class="alert alert-success">

    **提示:** 某些widget属性需要单个widget（child），而其它一些属性，如action，需要一组widgets(children），用方括号[]表示。

    </aside>

    将该图标及其相应的操作添加到build方法中：

        class RandomWordsState extends State<RandomWords> {
          ...
          @override
          Widget build(BuildContext context) {
            return new Scaffold(
              appBar: new AppBar(
                title: new Text('Startup Name Generator'),
                actions: <Widget>[
                  new IconButton(icon: new Icon(Icons.list), onPressed: _pushSaved),
                ],
              ),
              body: _buildSuggestions(),
            );
          }
          ...
        }

2.  向RandomWordsState类添加一个 `_pushSaved()` 方法.

        class RandomWordsState extends State<RandomWords> {
          ...
          void _pushSaved() {
          }
        }

    热重载应用，列表图标将会出现在导航栏中。现在点击它不会有任何反应，因为 `_pushSaved` 函数还是空的。

3.  当用户点击导航栏中的列表图标时，建立一个路由并将其推入到导航管理器栈中。此操作会切换页面以显示新路由。

    新页面的内容在在MaterialPageRoute的`builder`属性中构建，`builder`是一个匿名函数。

    添加Navigator.push调用，这会使路由入栈（以后路由入栈均指推入到导航管理器的栈）

        void _pushSaved() {
          Navigator.of(context).push(
          );
        }

4.  添加MaterialPageRoute及其builder。 现在，添加生成ListTile行的代码。ListTile的`divideTiles()`方法在每个ListTile之间添加1像素的分割线。 该 `divided` 变量持有最终的列表项。

        void _pushSaved() {
          Navigator.of(context).push(
            new MaterialPageRoute(
              builder: (context) {
                final tiles = _saved.map(
                  (pair) {
                    return new ListTile(
                      title: new Text(
                        pair.asPascalCase,
                        style: _biggerFont,
                      ),
                    );
                  },
                );
                final divided = ListTile
                  .divideTiles(
                    context: context,
                    tiles: tiles,
                  )
                  .toList();
              },
            ),
          );
        }

5.  builder返回一个Scaffold，其中包含名为“Saved Suggestions”的新路由的应用栏。 新路由的body由包含ListTiles行的ListView组成; 每行之间通过一个分隔线分隔。

    添加如下高亮的代码:

        void _pushSaved() {
          Navigator.of(context).push(
            new MaterialPageRoute(
              builder: (context) {
                final tiles = _saved.map(
                  (pair) {
                    return new ListTile(
                      title: new Text(
                        pair.asPascalCase,
                        style: _biggerFont,
                      ),
                    );
                  },
                );
                final divided = ListTile
                  .divideTiles(
                    context: context,
                    tiles: tiles,
                  )
                  .toList();

                return new Scaffold(
                  appBar: new AppBar(
                    title: new Text('Saved Suggestions'),
                  ),
                  body: new ListView(children: divided),
                );
              },
            ),
          );
        }

6.  热重载应用程序。收藏一些选项，并点击应用栏中的列表图标，在新路由页面中显示收藏的内容。 请注意，导航器会在应用栏中添加一个“返回”按钮。你不必显式实现Navigator.pop。点击后退按钮返回到主页路由。



<div style="text-align:center"><img src="https://flutterchina.club/get-started/codelab/images/step6a-screenshot.png" /></div>
<div style="text-align:center"><img src="https://flutterchina.club/get-started/codelab/images/step6b-screenshot.png" /></div>

## 使用主题更改UI
1.  可以通过配置ThemeData类轻松更改应用程序的主题。 应用程序目前使用默认主题，下面将更改primary color颜色为白色。

    通过如下高亮部分代码，将应用程序的主题更改为白色：

        class MyApp extends StatelessWidget {
          @override
          Widget build(BuildContext context) {
            return new MaterialApp(
              title: 'Startup Name Generator',
              theme: new ThemeData(
                primaryColor: Colors.white,
              ),
              home: new RandomWords(),
            );
          }
        }

2.  热重载应用。 请注意，整个背景将会变为白色，包括应用栏。

3.  使用 [ThemeData](https://docs.flutter.io/flutter/material/ThemeData-class.html) 来改变UI的其他方面。 Material library中的 [Colors](https://docs.flutter.io/flutter/material/Colors-class.html)类提供了许多可以使用的颜色常量， 你可以使用热重载来快速简单地尝试、实验。

<div style="text-align:center"><img src="https://flutterchina.club/get-started/codelab/images/step7-themes.png" /></div>
