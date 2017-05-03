<div class="post">
	<h1 class="postTitle"><a class="postTitle2" id="cb_post_title_url" href="http://www.cnblogs.com/zeroone/archive/2013/01/13/2858837.html">C# Process.Start()方法详解</a></h1>
	<div id="cnblogs_post_body"><p>System.Diagnostics.Process.Start(); 能做什么呢？它主要有以下几个功能：</p>
<p>1、打开某个链接网址（弹窗）。</p>
<p>2、定位打开某个文件目录。</p>
<p>3、打开系统特殊文件夹，如“控制面板”等。</p>
<p>那么它是怎么实现这几个功能的呢？在讲应用前，我们先来看看Process.Star()的构造方法。</p>
<p>&nbsp;</p>
<table class="memberListTable " style="width: 100%;" border="1" cellspacing="2" cellpadding="5">
<tbody>
<tr><th align="left" style="border-right-style: none;">名称</th><th align="left" style="border-left-style: none;">说明</th></tr>
<tr valign="top">
<td><a href="http://blog.csdn.net/czw2010/article/details/M_System_Diagnostics_Process_Start.htm">Process.Start () </a></td>
<td>启动（或重用）此 Process 组件的 <a href="http://blog.csdn.net/czw2010/article/details/P_System_Diagnostics_Process_StartInfo.htm">StartInfo</a> 属性指定的进程资源，并将其与该组件关联。</td>
</tr>
<tr valign="top">
<td><a href="http://blog.csdn.net/czw2010/article/details/M_System_Diagnostics_Process_Start_1_203c13b0.htm">Process.Start (ProcessStartInfo)</a></td>
<td>启动由包含进程启动信息（例如，要启动的进程的文件名）的参数指定的进程资源，并将该资源与新的 Process 组件关联。</td>
</tr>
<tr valign="top">
<td><a href="http://blog.csdn.net/czw2010/article/details/M_System_Diagnostics_Process_Start_1_16219e3a.htm">Process.Start (String)</a></td>
<td>通过指定<span style="color: #3333ff;">文档或应用程序文件的名称</span>来启动进程资源，并将资源与新的 Process 组件关联。</td>
</tr>
<tr valign="top">
<td><a href="http://blog.csdn.net/czw2010/article/details/M_System_Diagnostics_Process_Start_1_d460c748.htm">Process.Start (String, String)</a></td>
<td>通过指定<span style="color: #3333ff;">应用程序的名称和一组命令行参数</span>来启动一个进程资源，并将该资源与新的 Process 组件相关联。</td>
</tr>
<tr valign="top">
<td><a href="http://blog.csdn.net/czw2010/article/details/M_System_Diagnostics_Process_Start_2_c5c60ac7.htm">Process.Start (String, String, SecureString, String)</a></td>
<td>通过指定<span style="color: #3333ff;">应用程序的名称、用户名、密码和域</span>来启动一个进程资源，并将该资源与新的 Process 组件关联起来。</td>
</tr>
<tr valign="top">
<td><a href="http://blog.csdn.net/czw2010/article/details/M_System_Diagnostics_Process_Start_2_c4ca9475.htm">Process.Start (String, String, String, SecureString, String)</a></td>
<td>通过指定<span style="color: #3333ff;">应用程序的名称和一组命令行参数、用户名、密码和域</span>来启动一个进程资源，并将该资源与新的 Process 组件关联起来。</td>
</tr>
</tbody>
</table>
<p><span style="color: #3333ff;"><a href="http://write.blog.csdn.net/postedit/T_System_Diagnostics_Process.htm">(1) public</a><a href="http://write.blog.csdn.net/postedit/T_System_Diagnostics_Process.htm">bool</a> Start ()</span><br>
</p>
<p>System.Diagnostics.Process process = new System.Diagnostics.Process();</p>
<p>process.StartInfo.FileName = "iexplore.exe";&nbsp;&nbsp; //IE浏览器，可以更换<br>
</p>
<p>process.StartInfo.Arguments = "http://www.baidu.com";</p>
<p>process.Start();</p>
<p><br>
</p>
<p><span style="color: #3333ff;"><a href="http://blog.csdn.net/czw2010/article/details/T_System_Diagnostics_Process.htm"><span class="keyword">(2) public</span><span class="keyword">static</span></a><a href="http://blog.csdn.net/czw2010/article/details/T_System_Diagnostics_Process.htm">Process</a><span class="identifier">Start</span>
 (<a href="http://blog.csdn.net/czw2010/article/details/T_System_Diagnostics_ProcessStartInfo.htm">ProcessStartInfo</a><span class="parameter">startInfo)</span></span><br>
</p>
<p>System.Diagnostics.ProcessStartInfo processStartInfo = new System.Diagnostics.ProcessStartInfo();</p>
<p>processStartInfo.FileName = "explorer.exe";&nbsp; //资源管理器<br>
</p>
<p>processStartInfo.Arguments = @"D:\";</p>
<p>System.Diagnostics.Process.Start(processStartInfo);</p>
<p><br>
</p>
<p><span style="color: #3333ff;"><a href="http://write.blog.csdn.net/postedit/M_System_Diagnostics_Process_Start_1_16219e3a.htm"><span class="keyword">(3) public</span><span class="keyword">static</span></a><a href="http://blog.csdn.net/czw2010/article/details/T_System_Diagnostics_Process.htm">Process</a><span class="identifier">Start</span>
 (string<span class="parameter">fileName)</span></span></p>
<p>System.Diagnostics.Process.Start(@"D:\Program Files\Tencent\QQ\Bin\QQ.exe");&nbsp; //直接调用打开文件</p>
<p><a href="http://write.blog.csdn.net/postedit/M_System_Diagnostics_Process_Start_1_d460c748.htm"><br>
</a></p>
<p><span style="color: #3333ff;"><a href="http://write.blog.csdn.net/postedit/M_System_Diagnostics_Process_Start_1_d460c748.htm">(4) Process.Start (String</a><a href="http://write.blog.csdn.net/postedit/M_System_Diagnostics_Process_Start_1_d460c748.htm"><span class="parameter">fileName</span></a>,
 String<span class="parameter">arguments</span>)&nbsp;</span></p>
<p>System.Diagnostics.Process.Start("explorer.exe", "D:\\Readme.txt");&nbsp;&nbsp; //直接打开文件Readme.txt</p>
<p><br>
</p>
<p>上面已经举例了用process.start()打开网站的方法，现在讲讲用processs.star()定位到某个文件的方法。</p>
<p>这种定位方法类似于快捷方式上的查找目标：//explorer /select,"D:\Program Files\Tencent\QQ\Bin\QQ.exe"<br>
</p>
<p><span style="color: #993300;">String path = @"D:\Program Files\Tencent\QQ\Bin\QQ.exe";</span><br>
</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("explorer.exe", "/select</span><span style="color: #993300;">," +path);&nbsp;</span> //定位打开D:\Program Files\Tencent\QQ\Bin文件目录并选中了QQ.exe<br>
</p>
<p><span style="color: #ff0000;">注意：/select后还有个逗号(,)。</span><br>
</p>
<p><br>
</p>
<p>接下来来讲讲通过调用rundll32.exe来打开一些系统特定文件，先简单介绍下rundll32.exe的功能和作用。</p>
<p>顾名思义，rundll32就是"执行32位的dll文件"，也就是执行dll文件中的内部函数，可以以命令行的形式调用windows32位的动态链接库。</p>
<p>同理，rundll.exe就是"执行16位的dll文件"，调用的是16位的动态链接库。我们通过rundll32.exe执行指令来完成一些功能。</p>
<p>举个例子：</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("rundll32.exe","user.exe,restartwindows");&nbsp;&nbsp;</span>&nbsp;&nbsp;&nbsp; //系统重启命令<br>
</p>
<div>
<h3><strong><span style="color: #ff0000;">rundll32命令大全</span></strong></h3>


</div>
<hr>
<p>
命令列:rundll32.exe user.exe,restartwindows <br>
功能: <span style="color: #ff6600;"><span style="color: #3333ff;">系统重启</span><br>
</span><br>
命令列:rundll32.exe user.exe,exitwindows<br>
功能: <span style="color: #ff6600;"><span style="color: #3333ff;">关闭系统</span><br>
</span><br>
命令列: rundll32.exe shell32.dll,Control_RunDLL <br>
功能: <span style="color: #3333ff;">显示控制面板 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL access.cpl,,1 <br>
功能: <span style="color: #3333ff;">显示“控制面板－辅助选项－键盘”选项视窗 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL access.cpl,,2 <br>
功能: <span style="color: #3333ff;">显示“控制面板－辅助选项－声音”选项视窗 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL access.cpl,,3 <br>
功能: <span style="color: #3333ff;">显示“控制面板－辅助选项－显示”选项视窗 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL access.cpl,,4 <br>
功能: <span style="color: #3333ff;">显示“控制面板－辅助选项－滑鼠”选项视窗 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL access.cpl,,5 <br>
功能: <span style="color: #3333ff;">显示“控制面板－辅助选项－传统”选项视窗 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL sysdm.cpl @1 <br>
功能: <span style="color: #3333ff;">执行“控制面板－添加新硬体”向导。 </span><br>
</p>
<p>命令列: rundll32.exe shell32.dll,SHHelpShortcuts_RunDLL AddPrinter <br>
功能: <span style="color: #3333ff;">执行“控制面板－添加新印表机”向导。 </span><br>
</p>
<p><br>
</p>
<p>命令列: rundll32.exe shell32.dll,Control_RunDLL appwiz.cpl,,1<br>
功能: <span style="color: #3333ff;"><span style="color: #3333ff;">显示 “控制面板－添加/删除程式” 面板</span>。</span><br>
</p>
<p><br>
</p>
<p>命令列: rundll32.exe shell32.dll,Control_RunDLL appwiz.cpl,,1 <br>
</p>
<p>

功能: <span style="color: #3333ff;">显示 “控制面板－添加/删除程式－安装/卸载” 面板。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL appwiz.cpl,,2 <br>
功能: <span style="color: #3333ff;">显示 “控制面板－添加/删除程式－安装Windows” 面板。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL appwiz.cpl,,3 <br>
功能: <span style="color: #3333ff;">显示 “控制面板－添加/删除程式－启动盘” 面板。 </span><br>
<br>
命令列: rundll32.exe syncui.dll,Briefcase_Create <br>
功能: <span style="color: #3333ff;">在桌面上建立一个新的“我的公文包”。 </span><br>
<br>
命令列: rundll32.exe diskcopy.dll,DiskCopyRunDll <br>
功能: <span style="color: #3333ff;">显示复制软碟视窗 <br>
</span><br>
命令列: rundll32.exe apwiz.cpl,NewLinkHere ％1 <br>
功能: <span style="color: #3333ff;">显示“建立快捷方式”的对话框，所建立的快捷方式的位置由％1参数决定。</span> <br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL timedate.cpl,,0 <br>
功能: <span style="color: #3333ff;">显示“日期与时间”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL timedate.cpl,,1 <br>
功能: <span style="color: #3333ff;">显示“时区”选项视窗。 </span><br>
<br>
命令列: rundll32.exe rnaui.dll,RnaDial [某个拨号连接的名称] <br>
功能: <span style="color: #3333ff;">显示某个拨号连接的拨号视窗。如果已经拨号连接，则显示目前的连接状态的视窗。 </span><br>
<br>
命令列: rundll32.exe rnaui.dll,RnaWizard <br>
功能: <span style="color: #3333ff;">显示“新建拨号连接”向导的视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL desk.cpl,,0 <br>
功能: <span style="color: #3333ff;">显示“显示属性－背景”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL desk.cpl,,1 <br>
功能: <span style="color: #3333ff;">显示“显示属性－萤屏保护”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL desk.cpl,,2 <br>
功能: <span style="color: #3333ff;">显示“显示属性－外观”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL desk.cpl,,3 <br>
功能: <span style="color: #3333ff;">显示显示“显示属性－属性”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,SHHelpShortcuts_RunDLL FontsFolder <br>
功能: <span style="color: #3333ff;">显示Windows的“字体”档案夹。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL main.cpl @3 <br>
功能: <span style="color: #3333ff;">同样是显示Windows的“字体”档案夹。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,SHFormatDrive <br>
功能: <span style="color: #3333ff;">显示格式化软碟对话框。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL joy.cpl,,0 <br>
功能: <span style="color: #3333ff;">显示“控制面板－游戏控制器－一般”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL joy.cpl,,1 <br>
功能: <span style="color: #3333ff;">显示“控制面板－游戏控制器－进阶”选项视窗。 </span><br>
<br>
命令列: rundll32.exe mshtml.dll,PrintHTML (HTML文档) <br>
功能: <span style="color: #3333ff;">列印HTML文档。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL mlcfg32.cpl <br>
功能: <span style="color: #3333ff;">显示Microsoft Exchange一般选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL main.cpl @0 <br>
功能:<span style="color: #3333ff;"> 显示“控制面板－滑鼠” 选项 。 <br>
</span><br>
命令列: rundll32.exe shell32.dll,Control_RunDLL main.cpl @1 <br>
功能:<span style="color: #3333ff;"> 显示 “控制面板－键盘属性－速度”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL main.cpl @1,,1 <br>
功能: <span style="color: #3333ff;">显示 “控制面板－键盘属性－语言”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL main.cpl @2 <br>
功能: <span style="color: #3333ff;">显示Windows“印表机”档案夹。</span> <br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL main.cpl @4 <br>
功能: <span style="color: #3333ff;">显示“控制面板－输入法属性－输入法”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL modem.cpl,,add <br>
功能: <span style="color: #3333ff;">执行“添加新调制解调器”向导。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL mmsys.cpl,,0 <br>
功能: <span style="color: #3333ff;">显示“控制面板－多媒体属性－音频”属性页。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL mmsys.cpl,,1 <br>
功能: <span style="color: #3333ff;">显示“控制面板－多媒体属性－视频”属性页。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL mmsys.cpl,,2 <br>
功能: <span style="color: #3333ff;">显示“控制面板－多媒体属性－MIDI”属性页。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL mmsys.cpl,,3 <br>
功能: <span style="color: #3333ff;">显示“控制面板－多媒体属性－CD音乐”属性页。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL mmsys.cpl,,4 <br>
功能: <span style="color: #3333ff;">显示“控制面板－多媒体属性－设备”属性页。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL mmsys.cpl @1 <br>
功能: <span style="color: #3333ff;">显示“控制面板－声音”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL netcpl.cpl <br>
功能:<span style="color: #3333ff;"> 显示“控制面板－网路”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL odbccp32.cpl <br>
功能:<span style="color: #3333ff;"> 显示ODBC32资料管理选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,OpenAs_RunDLL {drive:/path/filename} <br>
功能:<span style="color: #3333ff;"> 显示指定档案(drive:/path/filename)的“打开方式”对话框。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL password.cpl <br>
功能:<span style="color: #3333ff;"> 显示“控制面板－密码”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL powercfg.cpl <br>
功能: <span style="color: #3333ff;">显示“控制面板－电源管理属性”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,SHHelpShortcuts_RunDLL PrintersFolder <br>
功能:<span style="color: #3333ff;"> 显示Windows“印表机”档案夹。(同rundll32.exe shell32.dll,Control_RunDLL main.cpl @2)</span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL intl.cpl,,0 <br>
功能: <span style="color: #3333ff;">显示“控制面板－区域设置属性－区域设置”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL intl.cpl,,1 <br>
功能: <span style="color: #3333ff;">显示“控制面板－区域设置属性－数字”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL intl.cpl,,2 <br>
功能: <span style="color: #3333ff;">显示“控制面板－区域设置属性－货币”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL intl.cpl,,3 <br>
功能: <span style="color: #3333ff;">显示“控制面板－区域设置属性－时间”选项视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL intl.cpl,,4 <br>
功能:<span style="color: #3333ff;"> 显示“控制面板－区域设置属性－日期”选项视窗。 </span><br>
<br>
命令列: rundll32.exe desk.cpl,InstallScreenSaver [萤屏保护档案名] <br>
功能: <span style="color: #3333ff;">将指定的萤屏保护档案设置为Windows的屏保，并显示萤屏保护属性视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL sysdm.cpl,,0 <br>
功能: <span style="color: #3333ff;">显示“控制面板－系统属性－传统”属性视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL sysdm.cpl,,1 <br>
功能<span style="color: #3333ff;">: 显示“控制面板－系统属性－设备管理器”属性视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL sysdm.cpl,,2 <br>
功能: <span style="color: #3333ff;">显示“控制面板－系统属性－硬体配置档案”属性视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL sysdm.cpl,,3 <br>
功能:<span style="color: #3333ff;"> 显示“控制面板－系统属性－性能”属性视窗。 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL telephon.cpl <br>
功能: <span style="color: #3333ff;">显示“拨号属性”选项视窗 </span><br>
<br>
命令列: rundll32.exe shell32.dll,Control_RunDLL themes.cpl </p>
<p>功能:<span style="color: #3333ff;"> 显示“桌面主题”选项面板</span></p>
<p><br>
</p>
<p>命令列: rundll32.exe shell32.dll,Control_RunDLL firewall.cpl<span style="color: #3333ff;"><br>
</span>功能: <span style="color: #3333ff;">显示“Windows防火墙"面板<br>
<br>
</span>命令列: rundll32.exe shell32.dll,Control_RunDLL NetSetup.cpl,@0,WNSW<span style="color: #3333ff;"><br>
</span>功能:<span style="color: #3333ff;"> 显示“无线网络设置"面板</span></p>
<p>更多的命令请到这里下载：<a href="http://download.csdn.net/detail/czw2010/4530206">http://download.csdn.net/detail/czw2010/4530206</a><br>
</p>
<hr>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("notepad.exe"); &nbsp;</span>&nbsp; &nbsp; &nbsp; -- 打开记事本<br>
</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("calc.exe ");&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>&nbsp; &nbsp; &nbsp; &nbsp; -- 打开计算器</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("regedit.exe "); &nbsp;</span> &nbsp; &nbsp; &nbsp;&nbsp;&nbsp; -- 打开注册表<span style="color: #8000;"><br>
</span></p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("mspaint.exe "); &nbsp; &nbsp;</span><span style="color: #8000;"> &nbsp; &nbsp;</span>-- 打开<span style="color: #000000;">画图板</span></p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("write.exe "); &nbsp; &nbsp;</span>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; --<span style="color: #000000;">&nbsp;</span><span style="color: #000000;">打开写字板</span><br>
</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("mplayer2.exe ");&nbsp; &nbsp;</span> &nbsp; &nbsp; --<span style="color: #000000;">打开播放器</span><br>
</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("taskmgr.exe ");&nbsp; &nbsp; &nbsp;</span>&nbsp; &nbsp;&nbsp; --<span style="color: #000000;">打开任务管理器</span></p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("eventvwr.exe ");&nbsp;&nbsp;&nbsp;</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; --<span style="color: #000000;">打开事件查看器</span></p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("winmsd.exe "); &nbsp; &nbsp;</span> &nbsp; &nbsp; &nbsp; --<span style="color: #000000;">打开系统信息</span></p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("winver.exe ");&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span> --<span style="color: #000000;">打开Windows版本</span>信息</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("mailto: "+ address);&nbsp;</span><span style="color: #8000;">&nbsp;&nbsp;</span> -- 发邮件<span style="color: #8000;"><br>
</span></p>
<hr>
<p><span style="color: #993300;">shutdown.exe：</span></p>
<p><span style="color: #993300;">参数：-s 关机&nbsp;&nbsp; -r重启&nbsp;&nbsp; -f强行 &nbsp; -t 时间&nbsp;&nbsp;&nbsp; -a 取消关机 &nbsp; -l 注销 &nbsp;&nbsp; -i 显示用户界面</span><span style="color: #8000;"><br>
</span></p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("shutdown.exe","-r");&nbsp;&nbsp;</span>&nbsp;&nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- 关闭并重启计算机</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("shutdown.exe","-s -f");&nbsp;&nbsp;</span> &nbsp; &nbsp; &nbsp;&nbsp; -- 关闭计算机</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("shutdown.exe","-s -f 30");&nbsp;&nbsp;</span>&nbsp;&nbsp; -- 30s后关闭计算机</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("shutdown.exe","-l");&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;
</span>&nbsp;&nbsp;&nbsp; --注销计算机</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start("shutdown.exe","-a");&nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span>&nbsp; --撤销关闭计算机</p>
<hr>
<p><a href="http://blog.csdn.net/czw2010/article/details/T_System_Environment_SpecialFolder.htm">SpecialFolder</a>枚举成员：<br>
</p>
<p>&nbsp;</p>
<table style="width: 895px; height: 829px;" border="1" cellspacing="2" cellpadding="5">
<tbody>
<tr><th align="left">成员名称</th><th align="left">说明</th>
</tr>
<tr valign="top">
<td>ApplicationData</td>
<td>目录，它用作当前漫游用户的应用程序特定数据的公共储存库。
<p>漫游用户在网络上的多台计算机上工作。漫游用户的配置文件保存在网络服务器上，当用户登录到某个系统上时，它会加载到该系统。</p>


</td>


</tr>
<tr valign="top">
<td>CommonApplicationData</td>
<td>目录，它用作所有用户使用的应用程序特定数据的公共储存库。</td>


</tr>
<tr valign="top">
<td>CommonProgramFiles</td>
<td>用于应用程序间共享的组件的目录。</td>


</tr>
<tr valign="top">
<td>Cookies</td>
<td>用作 Internet Cookie 的公共储存库的目录。</td>


</tr>
<tr valign="top">
<td>Desktop</td>
<td>逻辑桌面，而不是物理文件系统位置。</td>


</tr>
<tr valign="top">
<td>DesktopDirectory</td>
<td>用于物理上存储桌面上的文件对象的目录。
<p>不应将此目录与桌面文件夹本身混淆，后者是虚拟文件夹。</p>


</td>


</tr>
<tr valign="top">
<td>Favorites</td>
<td>用作用户收藏夹项的公共储存库的目录。</td>


</tr>
<tr valign="top">
<td>History</td>
<td>用作 Internet 历史记录项的公共储存库的目录。</td>


</tr>
<tr valign="top">
<td>InternetCache</td>
<td>用作 Internet 临时文件的公共储存库的目录。</td>


</tr>
<tr valign="top">
<td>LocalApplicationData</td>
<td>目录，它用作当前非漫游用户使用的应用程序特定数据的公共储存库。</td>


</tr>
<tr valign="top">
<td>MyComputer</td>
<td>“我的电脑”文件夹。
<div class="alert">
<table style="width: 100%;" cellspacing="0" cellpadding="0">
<tbody>
<tr><th align="left">注意</th>
</tr>
<tr>
<td>
<p>由于没有为“我的电脑”文件夹定义路径，因此 MyComputer 常数将始终生成空字符串 ("")。</p>


</td>


</tr>


</tbody>


</table>


</div>


</td>


</tr>
<tr valign="top">
<td>MyDocuments</td>
<td>“我的电脑”文件夹。</td>


</tr>
<tr valign="top">
<td>MyMusic</td>
<td>“My Music”文件夹。</td>


</tr>
<tr valign="top">
<td>MyPictures</td>
<td>“My Pictures”文件夹。</td>


</tr>
<tr valign="top">
<td>Personal</td>
<td>用作文档的公共储存库的目录。</td>


</tr>
<tr valign="top">
<td>ProgramFiles</td>
<td>“Program files”目录。</td>


</tr>
<tr valign="top">
<td>Programs</td>
<td>包含用户程序组的目录。</td>


</tr>
<tr valign="top">
<td>Recent</td>
<td>包含用户最近使用过的文档的目录。</td>


</tr>
<tr valign="top">
<td>SendTo</td>
<td>包含“发送”菜单项的目录。</td>


</tr>
<tr valign="top">
<td>StartMenu</td>
<td>包含“开始”菜单项的目录。</td>


</tr>
<tr valign="top">
<td>Startup</td>
<td>对应于用户的“启动”程序组的目录。
<p>每当用户登录、启动 Windows NT 或更高版本或启动 Windows 98 时，系统均会启动这些程序。</p>


</td>


</tr>
<tr valign="top">
<td>System</td>
<td>“System”目录。</td>


</tr>
<tr valign="top">
<td>Templates</td>
<td>用作文档模板的公共储存库的目录。</td>


</tr>


</tbody>


</table>
<p>通过Environment.GetFolderPath(Environment.SpecialFolder.XXXXX);我们可以轻松地获得系统特殊文件夹的具体路径，然后用Process.Start()方法打开该文件夹。</p>
<p>例如：<br>
</p>
<p><span style="color: #993300;">System.Diagnostics.Process.Start(Environment.GetFolderPath(Environment.SpecialFolder.System));&nbsp;&nbsp;</span> //打开系统文件夹(System32文件夹)<br>
</p>
<hr>
<p>&nbsp;</p>
<p>&nbsp;[System.Runtime.InteropServices.DllImportAttribute("user32.dll")]<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private static extern int FindWindow(string ClassName, string WindowName);</p>
<p>[System.Runtime.InteropServices.DllImport("user32.dll")]<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private static extern int ShowWindow(int handle, int cmdShow);</p>
<p>[System.Runtime.InteropServices.DllImport("winmm.dll", EntryPoint = 
"mciSendString", CharSet = System.Runtime.InteropServices.CharSet.Auto)]<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private static extern int mciSendString(string lpstrCommand, 
string lpstrReturnstring, int uReturnLength, int hwndCallback);<br>
</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private const int SW_HIDE = 0;//API参数表示隐藏窗口<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; private const int SW_SHOW = 5;//API参数表示用当前的大小和位置显示窗口</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color: #993300;"> ShowWindow(FindWindow("Shell_TrayWnd", null), SW_HIDE);&nbsp;&nbsp;</span>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; -- 隐藏隐藏任务栏</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style="color: #993300;">ShowWindow(FindWindow("Shell_TrayWnd", null), SW_SHOW);&nbsp;</span>&nbsp;&nbsp;&nbsp;&nbsp; --&nbsp; 显示任务栏<br>
</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style="color: #993300;">mciSendString("set CDAudio door open", null, 127, 0); &nbsp;</span> &nbsp;&nbsp;&nbsp; -- 弹出光驱</p>
<p>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span style="color: #993300;">mciSendString("set CDAudio door closed", null, 127, 0);&nbsp;</span> &nbsp;&nbsp; --关闭光驱</p></div><div id="MySignature"></div>
<div class="clear"></div>

</div>
<div class="clear"></div>

</div>
</div>
