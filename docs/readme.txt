android4.0�������eclipse����ķ���

1.��android4.0ϵͳ�Ĵ����п���һ��������Ĵ��룬�������ļ��У���������ΪBrowserEclipse:
<android4.0Դ��>/package/apps/Browser  -->  <����Ŀ¼>/BrowserEclipse

2.��eclipse�е��빤��BrowserEclipse��
�˵�File-import��ѡ��Android-Existing Android Code Into Workspace��
����ļ��У���ѡ�񹤳̵ĸ�Ŀ¼��<����Ŀ¼>/BrowserEclipse��
ȥ��tests���̵Ĺ�ѡ��ť����ʱ����tests���̡�
���������̣�ѡ�񹤳̣�����Ҽ��˵�-Refactor-Rename������BrowserEclipse��
��ʱ�������л��кܶ������ʱ������ǡ�

3.��ӿ��ļ���
�ӱ���ͨ����android4.0Դ���outĿ¼�п�����Ӧ���ļ���BrowserEclipse��systemlib·���£��ļ����£�
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\android-common_intermediates\classes.jar
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\android-support-v13_intermediates\classes.jar
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\android-support-v4_intermediates\classes.jar
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\core_intermediates\classes.jar
BrowserEclipse\systemlib\out\target\common\obj\JAVA_LIBRARIES\framework_intermediates\classes.jar

��eclispe��ˢ���¹��̣���ѡ�񹤳̣�����Ҽ��˵�-Build Path-Configure Build Path����Librariesҳ���У�ѡ��Add Library-User Libraries-New�����������systemlib������ѡ���������ġ�System Library����

�ص�User Libraries���ڣ�ѡ���½�����systemlib�������ť��Add JARs������systemlib\�ļ�����������classes.jar����ӽ�ȥ��

һ·OK��ť���ص�Java Build Path���棬ѡ��Order and Exportҳ�棬ѡ���½���systemlib�����Top��ť��������һλ��OK��

4.����һЩ���롣
������3���裬�ص�eclipse�༭���棬ˢ�¹��̣���ʱ�󲿷ֵĴ����Ѿ��������ʣ�����������󣬰���Щ����ط����ε������ɣ�
����EventLogTags��ص��У�
BrowserEclipse\src\com\android\browser\LogTag.java��
����VisibleForTesting��ص��У�
BrowserEclipse\src\com\android\browser\BrowserActivity.java
BrowserEclipse\src\com\android\browser\provider\BrowserProvider2.java
BrowserEclipse\src\com\android\browser\autocomplete\SuggestedTextController.java
��ʱ��Ӧ��û�б�������ˡ�

5.����һ��java�ļ�����������ʱ����:
BrowserEclipse\src\com\android\common\content\SyncStateContentProviderHelper.java
����android4.0Դ�룺
frameworks\ex\common\java\com\android\common\content\SyncStateContentProviderHelper.java

6.�޸�BrowserEclipse\AndroidManifest.xml������<uses-sdk android:minSdkVersion="14"/>

7.ж��ϵͳӦ��Broser.apk����װBrowserEclipse.apk��
������Ҫ�Ȱѻ���root�����ܽ��У����apkֻ����android4.0��ϵͳ��������������4.1�в������С�
�ȱ���/system/app/Browser.apk��Browser.odex��������/sdcard���ɡ�
ɾ��/system/app/Browser.apk��Browser.odex������������
��װBrowserEclipse.apk���鿴Ч����