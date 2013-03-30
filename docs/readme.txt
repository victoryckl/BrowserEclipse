android4.0浏览器在eclipse编译的方法

1.从android4.0系统的代码中拷贝一份浏览器的代码，到本地文件夹，并重命名为BrowserEclipse:
<android4.0源码>/package/apps/Browser  -->  <本地目录>/BrowserEclipse

2.在eclipse中导入工程BrowserEclipse。
菜单File-import，选择Android-Existing Android Code Into Workspace。
浏览文件夹，并选择工程的根目录：<本地目录>/BrowserEclipse。
去掉tests工程的勾选按钮，暂时不管tests工程。
重命名工程：选择工程，鼠标右键菜单-Refactor-Rename，输入BrowserEclipse。
此时，工程中会有很多错误，暂时不用理睬。

3.添加库文件。
从编译通过的android4.0源码的out目录中拷贝相应的文件到BrowserEclipse的systemlib路径下，文件如下：
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\android-common_intermediates\classes.jar
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\android-support-v13_intermediates\classes.jar
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\android-support-v4_intermediates\classes.jar
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\core_intermediates\classes.jar
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\framework_intermediates\classes.jar

在eclispe中刷新下工程，再选择工程，鼠标右键菜单-Build Path-Configure Build Path，在Libraries页面中，选择Add Library-User Libraries-New，输入库名称systemlib，并勾选输入框下面的“System Library”。

回到User Libraries窗口，选择新建立的systemlib，点击按钮“Add JARs”，把systemlib\文件夹下面的五个classes.jar都添加进去。

一路OK按钮，回到Java Build Path界面，选择Order and Export页面，选择新建立systemlib，点击Top按钮，顶到第一位，OK。

4.屏蔽一些代码。
经过第3步骤，回到eclipse编辑界面，刷新工程，此时大部分的错误已经解决，仅剩少数几个错误，把这些错误地方屏蔽掉，即可：
屏蔽EventLogTags相关的行：
BrowserEclipse\src\com\android\browser\LogTag.java；
屏蔽VisibleForTesting相关的行：
BrowserEclipse\src\com\android\browser\BrowserActivity.java
BrowserEclipse\src\com\android\browser\provider\BrowserProvider2.java
BrowserEclipse\src\com\android\browser\autocomplete\SuggestedTextController.java
此时，应该没有编译错误了。

5.增加一个java文件，避免运行时错误:
BrowserEclipse\src\com\android\common\content\SyncStateContentProviderHelper.java
来自android4.0源码：
frameworks\ex\common\java\com\android\common\content\SyncStateContentProviderHelper.java

6.修改BrowserEclipse\AndroidManifest.xml，增加<uses-sdk android:minSdkVersion="14"/>

7.卸载系统应用Broser.apk，安装BrowserEclipse.apk。
这里需要先把机器root，才能进行，这个apk只能在android4.0的系统中运行正常，在4.1中不能运行。
先备份/system/app/Browser.apk和Browser.odex，拷贝到/sdcard即可。
删除/system/app/Browser.apk和Browser.odex，重启机器。
安装BrowserEclipse.apk，查看效果。