> ⚠️作者主页：【[GhostDavid的博客](https://ghostdavid.github.io/)】【[DNTech的CSDN主页](https://blog.csdn.net/weixin_63749061)】
⚠️若本文所采用图片或相关引用侵犯了您的合法权益，请联系我进行删除
⚠️本文采用 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh-hans) 许可协议进行授权，著作权归作者所有。转载或引用本文时请遵守许可协议，注明出处，并包含以上声明内容
# 下载最新win11 iso镜像
前往MSDN的新版网站：https://next.itellyou.cn/
注册登录后，在windows11的分类下找到consumer editions x64版本并下载
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/4a0f4ce6ca934ee28601a6f5e1b081ca.png)
# 下载tiny11builder
前往tiny11builder的github仓库：https://github.com/ntdevlabs/tiny11builder​
在release页选择最新版本的压缩包下载，下载后解压缩备用
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/96df1b660acd423e84550b085911970f.png)
在仓库主页中可以看到，tiny11builder精简的软件内容，个人推荐普通精简。另外，精简后的镜像将绕过系统初始化时的Microsoft账户登录
>普通精简：
Clipchamp
News
Weather
Xbox (although Xbox Identity provider is still here, so it should be possible to be reinstalled with no issues)
GetHelp
GetStarted
Office Hub
Solitaire
PeopleApp
PowerAutomate
ToDo
Alarms
Mail and Calendar
Feedback Hub
Maps
Sound Recorder
Your Phone
Media Player
QuickAssist
Internet Explorer
Tablet PC Math
Edge
OneDrive

>更完全的核心精简（core）：
all of the above +
Windows Component Store (WinSxS)
Windows Defender (only disabled, can be enabled back if needed)
Windows Update (Windows Update wouldn't work anyway without WinSxS, so enabling it would only put the system in a state where it would try to update but fail spectacularily)
WinRE

# 开始精简
## 右键iso文件装载镜像
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/78b46f98e1b34a30b8fbd409ffb18752.png)
## 管理员身份运行Windows PowerShell
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/e1476fc546ce48f1bd40f50d4b5b5391.png)
输入`Set-ExecutionPolicy unrestricted`以解除组策略脚本的运行限制
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/fd396ec140d84bea8e6376903800f632.png)
## 运行精简脚本
下载回来的tiny11builder压缩包里有两个精简脚本，分别对应普通精简和core精简。按需选择，右键使用powershell运行
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/dc580b03da32404283e07a65048c98c8.png)
输入iso文件装载的盘符，此处示例是E盘
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/f19d7b11980f4574ace416bbfc33ad32.png)
等待片刻后会显示iso镜像中含有的Windows版本，选择所需的版本（其他版本会被删除），个人建议选专业版就足够了
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/6a20b6c073eb4631b601416590e95167.png)
等待精简过程，不会太久，精简期间建议电脑不要做其他复杂操作，否则会有概率会导致部分精简脚本运行失败或报错
最后提示Done.Creation completed! Press any key to exit the script...时就说明完成了
随便敲个键，回车退出（一定要做，因为脚本最后一步是清理c盘缓存，路径在C盘根目录的tiny11文件夹）
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/9420aeb280db408894343233abe29b7f.png)
精简后的tiny11.iso文件在脚本所在路径下。精简后的iso文件大小并不会比精简前小太多，但系统安装后的C盘会小不少
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/cee3c77aecb446109d3ab157f2092e3e.png)

# 进一步精简（可选，推荐）
以下是系统安装后执行的精简工具，分别是
windows defender移除：https://github.com/ionuttbara/windows-defender-remover
microsoft edge浏览器移除：https://github.com/ShadowWhisperer/Remove-MS-Edge


