# 版本控制
## 简介
版本控制（Revision control）是一种在开发的过程中用于管理我们对文件、目录或工程等内容的修改历史，方便查看更改历史记录，备份以便恢复以前的版本的软件工程技术。
简单说就是用于管理多人协同开发项目的技术。

- 实现跨区域多人协同开发
- 追踪和记载一个或者多个文件的历史记录
- 组织和保护你的源代码和文档
- 统计工作量
- 并行开发、提高开发效率
- 跟踪记录整个软件的开发过程
- 减轻开发人员的负担，节省时间，同时降低人为错误
```markdown
没有进行版本控制或者版本控制本身缺乏正确的流程管理，在软件开发过程中将会引入很多问题，如软件代码
的一致性、软件内容的冗余、软件过程的事物性、软件开发过程中的并发性、软件源代码的安全性，以及软件
的整合等问题。
```
## 版本控制工具

- **Git**
- **SVN**（Subversion）
- **CVS**（Concurrent Versions System）
- **VSS**（Micorosoft Visual SourceSafe）
- **TFS**（Team Foundation Server）
- Visual Studio Online
## 版本控制分类
### **本地版本控制 **RCS
记录文件每次的更新，可以对每个版本做一个快照，或是记录补丁文件，适合个人用
### **集中版本控制  SVN**
所有的版本数据都保存在服务器上，协同开发者从服务器上同步更新或上传自己的修改
```markdown
所有的版本数据都存在服务器上，用户的本地只有自己以前所同步的版本，如果不连网的话，用户就看不到历史
版本，也无法切换版本验证问题，或在不同分支工作。而且，所有数据都保存在单一的服务器上，有很大的风险
这个服务器会损坏，这样就会丢失所有的数据，当然可以定期备份。代表产品：SVN、CVS、VSS
```
### 分布式版本控制 Git
所有版本信息仓库全部同步到本地的每个用户，这样就可以在本地查看所有版本历史，可以离线在本地提交，只需在连网时push到相应的服务器或其他用户那里。由于每个用户那里保存的都是所有的版本数据，只要有一个用户的设备没有问题就可以恢复所有的数据，但这增加了本地存储空间的占用。
```markdown
每个人都拥有全部的代码！安全隐患！
不会因为服务器损坏或者网络问题，造成不能工作的情况！
```
## Git与SVN的主要区别
### SVN
SVN是集中式版本控制系统，版本库是集中放在中央服务器的，而工作的时候，用的都是自己的电脑，所以首先要从中央服务器得到最新的版本，然后工作，完成工作后，需要把自己做完的活推送到中央服务器。集中式版本控制系统是必须联网才能工作，对网络带宽要求较高。
### GIT
Git是分布式版本控制系统，没有中央服务器，每个人的电脑就是一个完整的版本库，工作的时候不需要联网了，因为版本都在自己电脑上。协同的方法是这样的：比如说自己在电脑上改了文件A，其他人也在电脑上改了文件A，这时，你们两之间只需把各自的修改推送给对方，就可以互相看到对方的修改了。Git可以直接看到更新了哪些代码和文件！
# GIT基础
## 历史
Linux 内核开源项目有着为数众广的参与者。绝大多数的 Linux 内核维护工作都花在了提交补丁和保存归档的繁琐事务上(1991－2002年间)。到 2002 年，整个项目组开始启用一个专有的分布式版本控制系统 BitKeeper 来管理和维护代码。Linux社区中存在很多的大佬！破解研究 BitKeeper ！
到了 2005 年，开发 BitKeeper 的商业公司同 Linux 内核开源社区的合作关系结束，他们收回了 Linux 内核社区免费使用 BitKeeper 的权力。这就迫使 Linux 开源社区(特别是 Linux 的缔造者 Linus Torvalds)基于使用 BitKeeper 时的经验教训，开发出自己的版本系统。（2周左右！） 也就是后来的 Git！
**Git是目前世界上最先进的分布式版本控制系统。Git是免费、开源的，最初Git是为辅助 Linux 内核开发的，来替代 BitKeeper！**
## 安装
### 下载
[GIT官网](https://git-scm.com/)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650457904002-a8fea3ab-2046-4cd9-a9dd-1842515e0724.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=467&id=u8853050b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=964&originWidth=1254&originalType=binary&ratio=1&rotation=0&showTitle=false&size=492348&status=done&style=none&taskId=u0d62f785-e6cd-4520-8c25-bfe1964c53e&title=&width=608)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458001075-cd4be26a-f9b0-4087-ab62-c6b2aa6210a8.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=441&id=u744ed538&margin=%5Bobject%20Object%5D&name=image.png&originHeight=513&originWidth=715&originalType=binary&ratio=1&rotation=0&showTitle=false&size=55858&status=done&style=none&taskId=u747e8ba2-e29c-4e9a-9884-08eb3d3474b&title=&width=614)
### 安装
#### 安装包
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458155706-4a09fc77-55a5-4ae9-9e4e-4c5e1f379cf1.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=22&id=udc5103fb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=22&originWidth=607&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2961&status=done&style=none&taskId=u9c89f312-358a-485c-b7e3-8ae23a70b54&title=&width=607)
#### 许可声明
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458320012-ea7d8d41-b6b3-4325-896e-db64fb8ae867.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=367&id=u66d07f87&margin=%5Bobject%20Object%5D&name=image.png&originHeight=389&originWidth=495&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28410&status=done&style=none&taskId=u69646d8d-46f8-423f-a5d1-b2f9670d781&title=&width=467)
#### 安装路径
#### ![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458379628-c190c57f-a273-4edd-90b6-f698ffa4dd1e.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=366&id=u20060013&margin=%5Bobject%20Object%5D&name=image.png&originHeight=389&originWidth=500&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20427&status=done&style=none&taskId=ud882419a-410a-4f47-9bfc-36ea47b8eb8&title=&width=470)
#### 选择组件
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458480997-51bc0027-2954-4b46-918f-a4ca19fb31a7.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=363&id=uf2cc72f6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=397&originWidth=500&originalType=binary&ratio=1&rotation=0&showTitle=false&size=30041&status=done&style=none&taskId=ub8bee57a-5424-4ce7-bf90-9f8bd02c65f&title=&width=457)
#### 创建在开始菜单中的名称
创建开始菜单中的名称，不需要修改，直接点“Next”按钮
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458522292-a15c7d4e-eec6-4ec9-b3a0-664462fbc592.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=356&id=u2fa43f36&margin=%5Bobject%20Object%5D&name=image.png&originHeight=399&originWidth=513&originalType=binary&ratio=1&rotation=0&showTitle=false&size=34219&status=done&style=none&taskId=uee3c5ecb-0e6e-44ea-ab81-1bf5630b38d&title=&width=458)
#### Git文件默认的编辑器
默认Vim即可，直接点“Next”按钮进入下一个界面
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458539766-77bd472b-964a-4dc7-9ad0-22a2f71d18ee.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=348&id=u10d5b110&margin=%5Bobject%20Object%5D&name=image.png&originHeight=390&originWidth=498&originalType=binary&ratio=1&rotation=0&showTitle=false&size=26835&status=done&style=none&taskId=u7130dd7f-2c79-47cc-a380-acc436f4a53&title=&width=444)
#### 新存储库中初始分支的名称
设置新存储库中初始分支的名称，默认是“master”
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458561854-f86b3e06-2d65-4280-b995-d0f05160958d.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=348&id=ue5bf3b5b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=396&originWidth=500&originalType=binary&ratio=1&rotation=0&showTitle=false&size=32258&status=done&style=none&taskId=u99f7bfcc-c120-4f68-a213-e0aaa730c2d&title=&width=440)
#### 调整Path环境
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458583138-721bbea2-5d41-40bb-a6c2-af2b3d3a11e3.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=336&id=uab7dc6bc&margin=%5Bobject%20Object%5D&name=image.png&originHeight=390&originWidth=502&originalType=binary&ratio=1&rotation=0&showTitle=false&size=38007&status=done&style=none&taskId=u32ea6cc5-f884-4b76-968e-6078f2f3dca&title=&width=432)
第一种配置是“仅从Git Bash使用Git”。这是最安全的选择，因为您的PATH根本不会被修改。你只能使用 Git Bash 的 Git 命令行工具。但是这将不能通过第三方软件使用。
第二种配置是“从命令行以及第三方软件进行Git”。该选项被认为是安全的，因为它仅向PATH添加了一些最小的Git包装器，以避免使用可选的Unix工具造成环境混乱。
你将能够从Git Bash，命令提示符和Windows PowerShell以及在PATH中寻找Git的任何第三方软件中使用Git。这也是推荐的选项。
第三种配置是“从命令提示符使用Git和可选的Unix工具”。警告：这将覆盖Windows工具，如 “ find 和 sort ”。只有在了解其含义后才使用此选项。
#### 选择SSH可执行文件
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458595885-5c4ce895-b5d3-4556-9204-a0520eb670a2.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=396&id=u8639a301&margin=%5Bobject%20Object%5D&name=image.png&originHeight=396&originWidth=503&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25865&status=done&style=none&taskId=ua3195697-f848-4bc6-b8ee-9a74a7d4f2d&title=&width=503)
#### 选择HTTPS后端传输
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458606031-ce09b416-8fc6-4171-b824-cbd21709ed3b.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=391&id=u0f1bf8c4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=391&originWidth=500&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23252&status=done&style=none&taskId=u46272134-ad3a-4195-84aa-709f5a82ec1&title=&width=500)
第一个选项是“使用 OpenSSL 库”。服务器证书将使用ca-bundle.crt文件进行验证。这也是我们常用的选项。
第二个选项是“使用本地 Windows 安全通道库”。服务器证书将使用Windows证书存储验证。此选项还允许您使用公司的内部根CA证书，例如通过Active Directory Domain Services 。
#### 配置行尾符号转换
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458619402-7d23114d-9b07-4944-abb9-163458cbd7df.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=390&id=u28fdb7e1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=390&originWidth=501&originalType=binary&ratio=1&rotation=0&showTitle=false&size=35454&status=done&style=none&taskId=ua2380ae4-c494-4232-b7a5-879be777c45&title=&width=501)
第一个选项是“签出Windows风格，提交Unix风格的行尾”。签出文本文件时，Git会将LF转换为CRLF。提交文本文件时，CRLF将转换为LF。对于跨平台项目，这是Windows上的推荐设置(“ core.autocrlf”设置为“ true”)
第二个选项是“按原样签出，提交Unix样式的行尾”。签出文本文件时，Git不会执行任何转换。 提交文本文件时，CRLF将转换为LF。对于跨平台项目，这是Unix上的建议设置(“ core.autocrlf”设置为“ input”)
第三种选项是“按原样签出，按原样提交”。当签出或提交文本文件时，Git不会执行任何转换。不建议跨平台项目选择此选项(“core.autocrlf”设置为“ false”)
#### 配置用于Git Bash的终端模拟器
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458631439-3493a595-592f-4d23-b678-73f8f56929e4.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=391&id=uf8e38bbe&margin=%5Bobject%20Object%5D&name=image.png&originHeight=391&originWidth=495&originalType=binary&ratio=1&rotation=0&showTitle=false&size=31060&status=done&style=none&taskId=uf4161a4b-cdf3-4bce-84a3-8abbbbdd892&title=&width=495)
第一个选项是“使用MinTTY(MSYS2的默认终端)”。Git Bash将使用MinTTY作为终端模拟器，该模拟器具有可调整大小的窗口，非矩形选择和Unicode字体。Windows控制台程序(例如交互式Python)必须通过“ winpty”启动才能在MinTTY中运行。
第二个选项是“使用Windows的默认控制台窗口”。Git将使用Windows的默认控制台窗口(“cmd.exe”)，该窗口可以与Win32控制台程序(如交互式Python或node.js)一起使用，但默认的回滚非常有限，需要配置为使用unicode 字体以正确显示非ASCII字符，并且在Windows 10之前，其窗口不能自由调整大小，并且只允许矩形文本选择。
#### 选择git pull的默认行为
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458641279-07dd4d82-9292-4e83-a824-a101169ad2e0.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=391&id=ua6751bf0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=391&originWidth=499&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25017&status=done&style=none&taskId=u450f6bd0-4050-4a91-9f90-05cc3ff87c8&title=&width=499)
第一个选项：默认值(快进或合并)
这是“git pull”的标准行为：尽可能将当前分支快速转发到获取的分支，否则创建合并提交
第二个选项：复位
将当前分支复位到获取的分支上。如果没有要重新设置基础的本地提交，这相当于快进。
第三个选项：只有快进
快进到获取的分支。如果不能获取，则失败。
#### 配置凭证管理器
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458651747-495a85a2-e3fb-4eb2-b21d-c6370489a4cc.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=396&id=u8b10b6d1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=396&originWidth=501&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27221&status=done&style=none&taskId=u7fa3a679-1bcd-4191-a304-c537c57eaa1&title=&width=501)
第一个选择项：Git凭证管理器
第一个选择项：无，不要使用凭证管理器
#### 配置额外选项
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458660310-6d7c5b4d-8aff-46db-9906-30ba4cc41eef.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=394&id=u5c84376d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=394&originWidth=498&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25010&status=done&style=none&taskId=u9d2fb817-b747-4aa6-9f7b-8c2f155017e&title=&width=498)
第一个选项：“启用文件系统缓存”。文件系统数据将被批量读取并缓存在内存中用于某些操作(“core.fscache”设置为“true”)。 这提供了显著的性能提升。
第二个选项：“启用符号链接”。启用符号链接(需要SeCreateSymbolicLink权限)。请注意，现有存储库不受此设置的影响。
#### 配置实验选项
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458678464-9303789f-1677-40d5-8ef8-c7ceca667ab2.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=389&id=u1cf9fb15&margin=%5Bobject%20Object%5D&name=image.png&originHeight=389&originWidth=498&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24094&status=done&style=none&taskId=u17ddc220-e450-471a-9904-1a1b0cfd32a&title=&width=498)
第一个选项：启用对伪控制台的实验性支持。
(新增!)这允许在git bash窗口中运行Node或Python之类的本机控制台程序，而无需使用winpty，但它仍然存在已知的bug。
第二个选项：启用实验性内置文件系统监视器
(新增!)自动运行内置的文件系统监视程序，以加速包含许多文件的工作树中的常见操作，如“git status”、“git add”、“git commit”等。
#### git自动根据配置开始安装
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650458688156-0593474e-3012-4102-80df-108d5334acca.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=391&id=u94d1875a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=391&originWidth=499&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16227&status=done&style=none&taskId=u6c97a6ec-0419-454b-b095-df66e666d01&title=&width=499)
#### 安装完成
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650459116840-763f1f56-102d-468a-ad4a-5f84276fa7ef.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=393&id=ub6e735e9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=393&originWidth=499&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18925&status=done&style=none&taskId=u75aa25df-c734-4078-8db2-eaf3b207c7a&title=&width=499)
### 测试
#### Git Bash
使用最多  Linux命令格式
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650459625323-725b861d-d1d5-4ac1-91f8-11cfbf82629e.png#clientId=u2e3db38d-0059-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=310&id=ue161b0dd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=369&originWidth=577&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11200&status=done&style=none&taskId=uf4f09efe-a336-402c-a205-cd8e77a6d6d&title=&width=485)
#### Git CMD(Deprecated)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650459657494-1b6c7dbd-2a46-48a8-bb12-24f206919cd2.png#clientId=u2e3db38d-0059-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=257&id=u0a287c4a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=450&originWidth=859&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11967&status=done&style=none&taskId=uefb88690-2a38-4409-9859-ee0d82ff00f&title=&width=491)
#### Git GUI
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650459699960-a0abffd0-404e-4795-a2fa-797242b96676.png#clientId=u2e3db38d-0059-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=259&id=u24ef3eb2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=262&originWidth=495&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11086&status=done&style=none&taskId=u2b7e508c-f406-4391-830c-7617a35dbfa&title=&width=489)
## 卸载
### 清除环境变量
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650457694040-5e405e8e-b81a-48fc-9a2f-16bd663bdc9c.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=564&id=u5edd31e1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=564&originWidth=525&originalType=binary&ratio=1&rotation=0&showTitle=false&size=45643&status=done&style=none&taskId=uda6601a9-7c86-4683-bcc6-52b662516eb&title=&width=525)
### 卸载软件
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650457732636-b01393ce-58ba-4aa7-a880-4a7b4f18cd7b.png#clientId=u3e5ffbaf-67c7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=540&id=u81a86194&margin=%5Bobject%20Object%5D&name=image.png&originHeight=540&originWidth=1123&originalType=binary&ratio=1&rotation=0&showTitle=false&size=82487&status=done&style=none&taskId=ua4cc3886-4471-4d6b-9cc5-fa8fd1079d6&title=&width=1123)
## 配置
### 查看配置
```markdown
# 查看配置 
git config -l

# 查看系统config
git config --system --list
　　
# 查看当前用户（global）配置
git config --global  --list
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650461506046-31507432-0be2-467a-8042-fe7721e3b826.png#clientId=u2e3db38d-0059-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=319&id=ue7ad7988&margin=%5Bobject%20Object%5D&name=image.png&originHeight=319&originWidth=561&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23321&status=done&style=none&taskId=ue17a4b63-feeb-456e-992c-742f68bd409&title=&width=561)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650461541117-56a72353-814a-47d0-a461-2c403ffac10d.png#clientId=u2e3db38d-0059-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=242&id=u62f52958&margin=%5Bobject%20Object%5D&name=image.png&originHeight=236&originWidth=497&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17328&status=done&style=none&taskId=u469410de-a2e2-4e43-ad27-1aff66bd252&title=&width=509)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650461567350-510abcec-839b-4411-bf61-77f28f59e5fd.png#clientId=u2e3db38d-0059-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=114&id=u2ced853c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=124&originWidth=556&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9017&status=done&style=none&taskId=uaf91f7a7-6e2f-442f-8a35-edcddec0df8&title=&width=509)
### **相关的配置文件**
```markdown
Git\etc\gitconfig  ：Git 安装目录下的 gitconfig     --system 系统级
```
```markdown
C:\Users\Lenovo\ .gitconfig    只适用于当前登录用户的配置  --global 全局
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650461772106-909d90ad-f768-4a70-9750-3159224f7eba.png#clientId=u2e3db38d-0059-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=509&id=u496f043b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=509&originWidth=779&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28778&status=done&style=none&taskId=u4ee3ab1e-cbd0-418e-8082-b97b954a25a&title=&width=779)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650461867815-51ccd8ec-7301-46e4-97ca-f8c9b54a45c8.png#clientId=u2e3db38d-0059-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=271&id=ub825ec2c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=271&originWidth=799&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16110&status=done&style=none&taskId=u0376f712-2945-4bdd-b762-2bbfb4d9645&title=&width=799)
### 配置用户名和邮箱
```markdown
git config --global user.name "pepsi-wyl"  #名称
git config --global user.email 2322535585@qq.com   #邮箱
```
当你安装Git后首先要做的事情是设置你的用户名称和e-mail地址。
这是非常重要的，因为每次Git提交都会使用该信息，它被永远的嵌入到了你的提交中
# GIT基本理论
## 本地区域
下面这个图展示了工作区、版本库中的暂存区和版本库之间的关系：![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650520129616-c72c32e8-78cc-4b3c-8859-0532581a147e.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=399&id=u4f1eda89&margin=%5Bobject%20Object%5D&name=image.png&originHeight=399&originWidth=775&originalType=binary&ratio=1&rotation=0&showTitle=false&size=263486&status=done&style=none&taskId=u5428f7e6-8a92-42df-b73b-75dd35ab833&title=&width=775)

- 图中左侧为工作区，右侧为版本库。在版本库中标记为 "index" 的区域是暂存区（stage/index），标记为 "master" 的是 master 分支所代表的目录树。
- 图中我们可以看出此时 "HEAD" 实际是指向 master 分支的一个"游标"。所以图示的命令中出现 HEAD 的地方可以用 master 来替换。
- 图中的 objects 标识的区域为 Git 的对象库，实际位于 ".git/objects" 目录下，里面包含了创建的各种对象及内容。

- 当对工作区修改（或新增）的文件执行 **git add** 命令时，暂存区的目录树被更新，同时工作区修改（或新增）的文件内容被写入到对象库中的一个新的对象中，而该对象的ID被记录在暂存区的文件索引中。
- 当执行提交操作（git commit）时，暂存区的目录树写到版本库（对象库）中，master 分支会做相应的更新。即 master 指向的目录树就是提交时暂存区的目录树。
- 当执行 **git reset HEAD** 命令时，暂存区的目录树会被重写，被 master 分支指向的目录树所替换，但是工作区不受影响。
- 当执行 **git rm --cached <file>** 命令时，会直接从暂存区删除文件，工作区则不做出改变。
- 当执行 **git checkout .** 或者 **git checkout -- <file>** 命令时，会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区中的改动。
- 当执行 **git checkout HEAD .** 或者 **git checkout HEAD <file>** 命令时，会用 HEAD 指向的 master 分支中的全部或者部分文件替换暂存区和以及工作区中的文件。这个命令也是极具危险性的，因为不但会清除工作区中未提交的改动，也会清除暂存区中未提交的改动。
## 四个区域
Git本地有三个工作区域

- 工作区(Working Directory) 

      平时存放项目代码的地方

- 暂存区(Stage/Index)

      用于临时存放你的改动 (它只是一个文件，保存即将提交到文件列表信息)

- 版本库(Repository或Git Directory)

      安全存放数据的位置，这里面有你提交到所有版本的数据
Git远程有一个工作区域

- git仓库(Remote Directory)

      远程仓库，托管代码的服务器
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650519741592-f6d5980e-72f7-4e85-9714-4b82c6a17a34.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=428&id=UZPyh&margin=%5Bobject%20Object%5D&name=image.png&originHeight=428&originWidth=459&originalType=binary&ratio=1&rotation=0&showTitle=false&size=55676&status=done&style=none&taskId=uec98d1a5-45d2-4caa-9e92-2a31b3efff3&title=&width=459)
## 工作流程
在工作目录中添加、修改文件
将需要进行版本管理的文件放入暂存区域
将暂存区域的文件提交到git仓库
git管理的文件有三种状态：已修改（modified）,已暂存（staged）,已提交(committed)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650520537446-3306eb9f-e625-45a7-9d7a-e9a1f41d4178.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=508&id=u29848ec0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=508&originWidth=657&originalType=binary&ratio=1&rotation=0&showTitle=false&size=161950&status=done&style=none&taskId=u8225761f-d6e1-4d65-b10d-430a820c5f3&title=&width=657)
# GIT基本操作
## 创建仓库
### 创建全新仓库
在执行完成 **git init** 命令后，Git 仓库会生成一个 .git 目录，该目录包含了资源的所有元数据，其他的项目目录保持不变。
```markdown
# 使用当前目录作为Git仓库
git init

# 指定目录作为Git仓库
git init newrepo
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650521233070-f4bfa277-d5cd-4dd4-892c-cc3ca04a08e9.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=113&id=u23bc57b0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=113&originWidth=472&originalType=binary&ratio=1&rotation=0&showTitle=false&size=7003&status=done&style=none&taskId=ubc07234e-306d-4cb8-ac4d-e689337292c&title=&width=472)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650521239609-f11856d5-e16d-4b53-8801-310e63f62c48.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=92&id=u0764cc01&margin=%5Bobject%20Object%5D&name=image.png&originHeight=92&originWidth=601&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5365&status=done&style=none&taskId=u59f6d5f8-bbfb-4b33-8b78-3dba0b380a6&title=&width=601)
### 克隆远程仓库
```markdown
# 使用当前目录作为Git仓库
git clone git@github.com:pepsi-wyl/Spring.git

# 指定目录作为Git仓库
git clone git@github.com:pepsi-wyl/Spring.git  newrepo
```
SSH URL
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650521092249-28dcc3ef-2e84-487c-9d8f-ad674d84aac9.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=297&id=u443e405e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=630&originWidth=1114&originalType=binary&ratio=1&rotation=0&showTitle=false&size=100866&status=done&style=none&taskId=u69032bcb-3394-4cad-a53b-3294bfb6031&title=&width=526)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650521116133-b816e31c-8bc6-4412-8925-35d289e22a96.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=120&id=u21f28fbf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=122&originWidth=538&originalType=binary&ratio=1&rotation=0&showTitle=false&size=12392&status=done&style=none&taskId=u97643754-bc60-4f2d-9967-b7ecd12e961&title=&width=529)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650521165874-753058ba-af61-414f-a6bb-7c993740cd54.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=213&id=u84ef07d1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=266&originWidth=662&originalType=binary&ratio=1&rotation=0&showTitle=false&size=21852&status=done&style=none&taskId=u6b00cc63-5249-499c-87b7-a31a47ed9e2&title=&width=531)
## 提交日志
```markdown
# 查看历史提交记录
git log

# 查看历史提交记录 (精简)
git reflog
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650530866122-828e8bdc-2010-4539-86e4-9acb3217c7d6.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=87&id=nAliI&margin=%5Bobject%20Object%5D&name=image.png&originHeight=110&originWidth=512&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9177&status=done&style=none&taskId=u1a523182-cb60-483a-8579-0b4d3f306e3&title=&width=406)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650533880454-c727d738-686a-43ec-a3b9-be048c6502d9.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=68&id=dly1C&margin=%5Bobject%20Object%5D&name=image.png&originHeight=78&originWidth=467&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8817&status=done&style=none&taskId=u324b1b45-fff8-4166-8e3e-3b871943459&title=&width=408)
## 提交与修改
### 查看仓库状态
```markdown
# 查看所有文件状态
git status

# 查看指定文件状态
git status [filename]
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650530461765-b52db29b-be23-42f8-bc20-6449fb9c70b0.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=176&id=ueec3082f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=196&originWidth=482&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11484&status=done&style=none&taskId=u50d5d8a6-5d01-480f-8849-4312d9969b9&title=&width=434)
### 文件添加暂存区
```markdown
# 添加当前目录下的所有文件到暂存区
git add .

# 添加指定目录到暂存区，包括子目录
git add [dir]

# 添加一个或多个文件到暂存区
git add [file1] [file2] ...
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650530487401-3b64e323-00ce-4081-8723-f9d6ba583f99.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=193&id=uc51d321c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=193&originWidth=398&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13349&status=done&style=none&taskId=u22cfe1c2-6d66-4fa5-abc0-7ca52a5dddc&title=&width=398)
### 暂存区添加本地仓库
```markdown
# 提交暂存区到本地仓库中
git commit -m [message]

# 交暂存区的指定文件到仓库区
git commit [file1] [file2] ... -m [message]
```
```markdown
# 参数设置修改文件后不需要执行 git add 命令，直接来提交
git commit -a
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650530519046-b263b067-0e8d-4334-9065-e23961f2264a.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=174&id=u6105ac05&margin=%5Bobject%20Object%5D&name=image.png&originHeight=162&originWidth=392&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11869&status=done&style=none&taskId=uf77bfe10-01dc-4317-a70a-3fcd44cbf52&title=&width=421)
### 版本穿梭
```markdown
# 版本切换
git reset --hard 版本号
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650533959512-664a162e-53a4-4a4c-9217-6f7666e4f6ff.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=201&id=QLIIz&margin=%5Bobject%20Object%5D&name=image.png&originHeight=233&originWidth=488&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23886&status=done&style=none&taskId=u8960631f-3636-48a1-ab82-51b9b72e1fa&title=&width=422)
### 删除,移动,重命名文件
```markdown
# 将文件从暂存区和工作区中删除
git rm [file]  

# 删除之前修改过并且已经放到暂存区域的话，则必须要用强制删除选项 -f
git rm -f [file]   

# 文件从暂存区域移除，但工作区保留
git rm --cached [file]  
```
```markdown
## 必须要在暂存区或者文件commit之后才能进行rename

# 用于移动或重命名一个文件、目录或软连接
git mv [file] [newfile]

# 新文件名已经存在，但还是要重命名它，可以使用 -f 参数
git mv -f [file] [newfile]
```
## 分支管理
### ![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650537788118-c9a47d2b-91cd-4bfa-a238-88b13d66ced0.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=292&id=u77faa014&margin=%5Bobject%20Object%5D&name=image.png&originHeight=314&originWidth=791&originalType=binary&ratio=1&rotation=0&showTitle=false&size=61197&status=done&style=none&taskId=u4378b9e1-c395-4786-a979-d244756c38c&title=&width=736)
### 简介
在版本控制过程中，同时推进多个任务，为每个任务，我们就可以创建每个任务的单独分支。
使用分支意味着程序员可以把自己的工作从开发主线上分离开来， 开发自己分支的时候，不会影响主线分支的运行。
好处

- 同时并行推进多个功能开发，提高开发效率
- 各个分支在开发过程中，如果某一个分支开发失败，不会对其他分支有任何影响。失败的分支删除重新开始即可

对于初学者而言，分支可以简单理解为副本，一个分支就是一个单独的副本。（分支底层其实也是指针的引用）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650537944428-b1e4d0a0-658d-4b4a-9dbc-093aa10e0311.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=367&id=ud8a19c2c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=367&originWidth=779&originalType=binary&ratio=1&rotation=0&showTitle=false&size=66834&status=done&style=none&taskId=u2a602724-5c96-4acd-b877-ce534acc446&title=&width=779)
### 基本操作
#### 查看分支
```markdown
# 查看分支
git branch

# 查看分支 带版本号
git branch -v
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650538555956-b18670d6-c116-4c09-a9fd-86107030e838.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=51&id=u2a6058ed&margin=%5Bobject%20Object%5D&name=image.png&originHeight=51&originWidth=400&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5085&status=done&style=none&taskId=u86a7aedc-4c38-409d-9db6-bdeab7a9e4d&title=&width=400)
#### 创建分支
```markdown
# 创建分支 依然停留在当前分支
git branch 分支名

# 新建一个分支 并切换到该分支
git checkout -b 分支名
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650538568648-ebd1d5c3-deea-4ee6-af5d-ca10994ff89e.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=127&id=udc8daf92&margin=%5Bobject%20Object%5D&name=image.png&originHeight=127&originWidth=396&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11060&status=done&style=none&taskId=u83203174-83cc-4689-87da-ae3b1def4a8&title=&width=396)
#### 切换分支
```markdown
# 切换分支
git checkout 分支名
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650538579485-c0658520-ec0f-40ae-88d4-72c89b823162.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=137&id=u1adca4cb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=137&originWidth=405&originalType=binary&ratio=1&rotation=0&showTitle=false&size=12609&status=done&style=none&taskId=u3d5e8ed5-63e5-4749-8756-72cd631546c&title=&width=405)
#### 合并分支
```markdown
# 合并分支
git merge 分支名
```
在 master 分支上合并 hot-fix 分支（将hot-fix的合并到master）
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650538895829-1856f9b9-0e9f-47ce-b8de-4f52445bbc24.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=110&id=u718e8b55&margin=%5Bobject%20Object%5D&name=image.png&originHeight=110&originWidth=454&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8717&status=done&style=none&taskId=u2f6e684f-ec4d-4d8f-8947-5517fd0eaaa&title=&width=454)
#### 合并冲突
两个分支在同一个文件的同一个位置有两套完全不同的修改,Git 无法替我们决定使用哪一个

1.mater分支进行修改 t.c 并且提交
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650539936902-75809011-8f3f-494b-a788-f6f47a650929.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=180&id=u796e46ee&margin=%5Bobject%20Object%5D&name=image.png&originHeight=180&originWidth=406&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13932&status=done&style=none&taskId=u27a81d0b-6a31-4be1-a8f2-70b1a30b002&title=&width=406)
2.hot-fix分支进行修改 t.c 并且提交
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650539967849-26b2aae9-d4ba-4f39-8be5-2814b50bc100.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=98&id=u3f52f1bd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=102&originWidth=454&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9279&status=done&style=none&taskId=u9c572a47-e430-451c-a5b6-0d2650e5b5f&title=&width=438)![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650539975714-0e809a44-7cee-45c6-a9e5-6ee1cb2d22a4.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=114&id=u4f436b60&margin=%5Bobject%20Object%5D&name=image.png&originHeight=123&originWidth=472&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10728&status=done&style=none&taskId=ube0efbe9-d5bf-40b3-a8fd-8e56d7e1f27&title=&width=438)
3.合并冲突
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650540008454-bcbe9b3a-78db-43a5-a72a-ef85963cc0b6.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=92&id=u567469dc&margin=%5Bobject%20Object%5D&name=image.png&originHeight=94&originWidth=595&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10347&status=done&style=none&taskId=u9c7dfc71-dfd1-4169-84eb-fc9cfbb15e4&title=&width=582)
4.解决合并冲突 人文编辑该文件
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650540076363-12803d6e-a11b-462b-bbb5-de3b99e7ed0e.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=41&id=u6caa79fb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=41&originWidth=464&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4107&status=done&style=none&taskId=udfbaea11-1c5e-4ecd-a798-5fbe6c0c13d&title=&width=464)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650540095565-6ce8a17f-976e-4f64-862a-8a9da944274f.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=153&id=ubd124d5f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=132&originWidth=398&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4276&status=done&style=none&taskId=u7416f4ee-540e-47bb-bded-095ff366081&title=&width=460)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650539719687-50ef9d11-b382-497a-b339-33a94abb2882.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=163&id=u300b7790&margin=%5Bobject%20Object%5D&name=image.png&originHeight=120&originWidth=340&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3264&status=done&style=none&taskId=u9cb1b803-69dc-461d-93a3-02772a72ab1&title=&width=463)
5.合并成功
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650540118687-86132ef0-eed8-4f69-9194-e5c7dd0b35e9.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=181&id=uf3016327&margin=%5Bobject%20Object%5D&name=image.png&originHeight=181&originWidth=601&originalType=binary&ratio=1&rotation=0&showTitle=false&size=19343&status=done&style=none&taskId=uffdf636b-5156-4f01-95dc-476fd500a74&title=&width=601)
#### 删除分支
```markdown
# 删除分支
git branch -d 分支名
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650540363520-98f1c576-283b-450f-b59f-5215c8df6134.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=124&id=u4761f562&margin=%5Bobject%20Object%5D&name=image.png&originHeight=124&originWidth=394&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10429&status=done&style=none&taskId=u27bfb0e7-2b24-42e9-a6f2-25a54975283&title=&width=394)
## 远程操作
### SSHKey 
**GitHub配置SSH Key的目的是为了帮助我们在通过git提交代码时候，不需要繁琐的验证过程，简化操作流程。**
#### 生成SSHKey
```markdown
# 四次回车  默认在用户目录下，如：C:\User\xxx\.ssh\
ssh-keygen -t rsa -C "2322535585@qq.com"
```
#### 查看SSHKey
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650547212600-31c228ea-31a9-4e59-aced-7216b7198e55.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=24&id=UAijS&margin=%5Bobject%20Object%5D&name=image.png&originHeight=31&originWidth=801&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3467&status=done&style=none&taskId=u4f7c083e-ab56-4e15-bbd8-eca07291a79&title=&width=626)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650547220168-caa06eae-0ccd-478b-ac7e-d464581bdcc0.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=24&id=HcjOY&margin=%5Bobject%20Object%5D&name=image.png&originHeight=23&originWidth=603&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2852&status=done&style=none&taskId=u7dc73a21-836a-49c9-a0f5-8c9041adfa2&title=&width=626)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650547266825-5384c4d9-1004-43a5-9096-5ef537283016.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=207&id=EQuf9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=314&originWidth=954&originalType=binary&ratio=1&rotation=0&showTitle=false&size=81121&status=done&style=none&taskId=u2d243f7f-b303-411c-ae2f-b64958411ea&title=&width=628)
#### GitHub配置
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650547388481-456ea2ee-2d83-4169-b7cb-8a30abed494d.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=678&id=SAIiy&margin=%5Bobject%20Object%5D&name=image.png&originHeight=678&originWidth=1582&originalType=binary&ratio=1&rotation=0&showTitle=false&size=83551&status=done&style=none&taskId=u6af051a7-f040-4562-a795-4b8a720d944&title=&width=1582)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650547331268-4ae13e45-98a2-4f06-956e-a00a696fdaaf.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=602&id=dHyGt&margin=%5Bobject%20Object%5D&name=image.png&originHeight=602&originWidth=1514&originalType=binary&ratio=1&rotation=0&showTitle=false&size=87762&status=done&style=none&taskId=u8ccd0d00-2b96-4145-ba04-c7aaf477dd7&title=&width=1514)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650547603463-a5f7ae89-8f00-46b0-91c7-47fdf64b01ce.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=287&id=aGUlq&margin=%5Bobject%20Object%5D&name=image.png&originHeight=287&originWidth=416&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16676&status=done&style=none&taskId=uaff69a79-0dba-4c38-b234-78b34826556&title=&width=416)
#### Gitee配置
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650617143003-b50faaa5-e746-44fd-8c66-f6660d2bd431.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=302&id=u7cf6bd79&margin=%5Bobject%20Object%5D&name=image.png&originHeight=576&originWidth=1243&originalType=binary&ratio=1&rotation=0&showTitle=false&size=71414&status=done&style=none&taskId=u96ec47c9-b949-44e7-a39f-bd3efe98700&title=&width=652)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650617271081-8715f290-b6e0-45c1-97e0-64364afa2a88.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=59&id=uf08a68b6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=88&originWidth=970&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8581&status=done&style=none&taskId=u9cad644f-00d7-4957-a74f-9872e82304f&title=&width=645)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650617241888-3b1bc50c-189a-4e57-aa13-07b9d5e0ecc6.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=167&id=u7630b3b3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=202&originWidth=554&originalType=binary&ratio=1&rotation=0&showTitle=false&size=21547&status=done&style=none&taskId=u675ba440-b183-4677-932d-b0bf3863174&title=&width=457)

### GitHub创建远程库
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650541076127-cdd186ac-76be-447f-bd80-eddd73fdb769.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=438&id=u379b4453&margin=%5Bobject%20Object%5D&name=image.png&originHeight=438&originWidth=1249&originalType=binary&ratio=1&rotation=0&showTitle=false&size=65745&status=done&style=none&taskId=ucea34cc4-dcc5-4963-8460-79a4da827ed&title=&width=1249)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650541148913-fe9d74c4-353f-4e60-883e-1f39410ef995.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=516&id=u6f7420f4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=516&originWidth=996&originalType=binary&ratio=1&rotation=0&showTitle=false&size=50310&status=done&style=none&taskId=uaa6c5af0-18e1-46db-9c87-801e68d3893&title=&width=996)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650541277533-c63bbfbc-5eae-49b4-800f-c9f5a9312beb.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=168&id=u2770a6bb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=168&originWidth=1191&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24740&status=done&style=none&taskId=ub1aff628-850f-4eca-8863-39d372bd3da&title=&width=1191)
### 添加远程库
可以指定一个简单的名字，以便将来引用  尽量命名为本地库的名称
```markdown
# 查看当前所有远程地址别名
git remote -v 

# 创建远程地址别名
git remote add 别名 远程仓库链接
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650541331426-84d1ba67-a8b5-4eab-aaae-dd5271c3d19f.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=113&id=u907bb470&margin=%5Bobject%20Object%5D&name=image.png&originHeight=141&originWidth=543&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14641&status=done&style=none&taskId=ud520e7e8-9171-4566-86aa-6e01493b585&title=&width=434)
### 删除远程库
```markdown
# 删除远程库
git remote rm [别名]
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650543418371-0cb5eb08-f18f-46ab-9f2f-0fff7f071522.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=92&id=ud1c9684b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=92&originWidth=430&originalType=binary&ratio=1&rotation=0&showTitle=false&size=7978&status=done&style=none&taskId=u8a3ddfad-32b8-480a-acd1-21baf300bb7&title=&width=430)
### 推送远程库
提交代码至远程库
```markdown
# 推送远程库
git push [远程库url 或 远程库别名] 分支名
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650541779204-c409b44f-e1ae-42cc-a188-5c232f248cac.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=201&id=u3bb85dea&margin=%5Bobject%20Object%5D&name=image.png&originHeight=201&originWidth=539&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23076&status=done&style=none&taskId=u5c21b696-7ae6-4f29-ada3-99861a9396f&title=&width=539)
### 拉取远程库
远程GitHub修改代码  本地需要同步
```markdown
# 拉取远程库
git pull [远程库url 或 远程库别名] 分支名
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650542627170-6664f6e1-ba90-406e-9383-aee87017ad98.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=353&id=u1adce867&margin=%5Bobject%20Object%5D&name=image.png&originHeight=353&originWidth=550&originalType=binary&ratio=1&rotation=0&showTitle=false&size=32414&status=done&style=none&taskId=u5ae17efd-c820-42e4-8af3-b76074ad625&title=&width=550)
### 克隆远程库
```markdown
# 克隆远程库
git clone 远程库地址

# clone 会做如下操作
- 拉取代码   
- 初始化本地仓库  
- 创建别名
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650542992898-5d12e77f-d964-4cf1-a3c0-f63c352c6888.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=143&id=ud34521cd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=130&originWidth=491&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13379&status=done&style=none&taskId=u57914edf-4e00-4400-8bd2-e6ef062232e&title=&width=541)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650543121409-702c9fa3-d2ff-4989-bebc-388356114234.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=64&id=u89519804&margin=%5Bobject%20Object%5D&name=image.png&originHeight=57&originWidth=485&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6268&status=done&style=none&taskId=u63ddbe27-3b11-4abe-b24f-1f160e12187&title=&width=545)
### 团队合作
团队内的成员才可以对 远程库进行push
#### 添加成员
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650544456694-aa685c8f-2956-4854-9c72-5476ab215756.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=440&id=u2320491d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=822&originWidth=1230&originalType=binary&ratio=1&rotation=0&showTitle=false&size=100753&status=done&style=none&taskId=u85e3777d-411e-4166-9503-fa2b9822735&title=&width=659)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650544523473-f2fc61ad-6caf-455e-9dde-99c53346e0a3.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=394&id=u359232ab&margin=%5Bobject%20Object%5D&name=image.png&originHeight=394&originWidth=659&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29189&status=done&style=none&taskId=u4ed41720-05f2-4d7a-bfbf-c85aafb8a92&title=&width=659)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650544545845-211963fb-2059-487b-9b02-20f9a41cae33.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=261&id=u70c2347e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=346&originWidth=876&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25892&status=done&style=none&taskId=u8cf2467a-4cf3-4df2-97fa-5d8526e7bb9&title=&width=661)
```markdown
# 邀请函
https://github.com/pepsi-wyl/Git/invitations
```
#### 成员同意
```markdown
# 复制邀请函至浏览器
https://github.com/pepsi-wyl/Git/invitations
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650544812543-fc0e6d1a-30ef-4aad-b40f-0e574955f6d2.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=288&id=u530f5f41&margin=%5Bobject%20Object%5D&name=image.png&originHeight=288&originWidth=442&originalType=binary&ratio=1&rotation=0&showTitle=false&size=59370&status=done&style=none&taskId=u8254efdd-17e8-4df8-a842-e190a0079c1&title=&width=442)
### 跨团队合作
跨团队需要 fork项目   可以聊天
#### 修改人
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650546006845-7c490915-9cf0-4fef-9e36-91054503c242.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=671&id=uf7e24a64&margin=%5Bobject%20Object%5D&name=image.png&originHeight=671&originWidth=1615&originalType=binary&ratio=1&rotation=0&showTitle=false&size=74600&status=done&style=none&taskId=u65bdb235-f41b-44e7-904b-de20fd00329&title=&width=1615)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650546030709-39a36fa7-84a4-48c9-8aff-bb67366f33bd.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=99&id=u45ac1245&margin=%5Bobject%20Object%5D&name=image.png&originHeight=99&originWidth=1074&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9785&status=done&style=none&taskId=u7d2006a9-5217-4d67-a6a3-d7340a045b3&title=&width=1074)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650546189109-6539b38b-b6de-4d34-9b7e-48bc545c44cd.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=586&id=u15d257e5&margin=%5Bobject%20Object%5D&name=image.png&originHeight=586&originWidth=1513&originalType=binary&ratio=1&rotation=0&showTitle=false&size=58599&status=done&style=none&taskId=u7e0f90bf-92cf-453c-a356-c311e47db40&title=&width=1513)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650546216858-a67a20ca-def4-4114-b48b-814cb8ddbe21.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=753&id=u325603db&margin=%5Bobject%20Object%5D&name=image.png&originHeight=753&originWidth=1421&originalType=binary&ratio=1&rotation=0&showTitle=false&size=90596&status=done&style=none&taskId=uc87e0352-c3a0-4c23-9c0b-f9f08ef7316&title=&width=1421)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650546266060-62ef0f23-0408-4d97-8acf-35382a294285.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=685&id=u0d20c15b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=685&originWidth=1427&originalType=binary&ratio=1&rotation=0&showTitle=false&size=80130&status=done&style=none&taskId=u0a735491-07a9-4f76-9303-451b627bded&title=&width=1427)
#### 被修改人
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650545816487-3cef917f-a022-4bdb-9984-898efa61e4b6.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=119&id=u48a828cf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=119&originWidth=1055&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27573&status=done&style=none&taskId=uae3d6532-7d98-41b8-86d5-4beafcffa7c&title=&width=1055)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650545917340-ab5ba7fc-353f-4239-b21f-a339a1db7429.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=280&id=u809a754e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=280&originWidth=845&originalType=binary&ratio=1&rotation=0&showTitle=false&size=54470&status=done&style=none&taskId=ua7c7effd-f5ca-451c-bce4-683dd57ad18&title=&width=845)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650545928222-3a924ba5-6dc7-4969-9c3e-9864f75d4405.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=267&id=uea4c5a58&margin=%5Bobject%20Object%5D&name=image.png&originHeight=267&originWidth=788&originalType=binary&ratio=1&rotation=0&showTitle=false&size=56795&status=done&style=none&taskId=u76000ace-20e7-47f5-b77c-399a8861cd5&title=&width=788)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650545946488-1beb532f-4c35-4654-b36a-4b731f7fa139.png#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=266&id=ue7aa3efb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=266&originWidth=826&originalType=binary&ratio=1&rotation=0&showTitle=false&size=50991&status=done&style=none&taskId=u2f9fc1b2-9a1d-4b66-8be4-94d601c71cf&title=&width=826)
## 常用命令大全
![011500266295799.jpg](https://cdn.nlark.com/yuque/0/2022/jpeg/23219042/1650531112721-bf75d117-d037-4a2c-8f4a-fb9a2122f1b7.jpeg#clientId=u1f433071-cfa7-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ue6f6c4fc&margin=%5Bobject%20Object%5D&name=011500266295799.jpg&originHeight=1466&originWidth=2076&originalType=binary&ratio=1&rotation=0&showTitle=false&size=178854&status=done&style=none&taskId=u2820c89b-ed35-4f02-942f-cbab63072e3&title=)
```markdown
git init                                                  # 初始化本地git仓库（创建新仓库）
git config --global user.name "xxx"                       # 配置用户名
git config --global user.email "xxx@xxx.com"              # 配置邮件
git config --global color.ui true                         # git status等命令自动着色
git config --global color.status auto
git config --global color.diff auto
git config --global color.branch auto
git config --global color.interactive auto
git config --global --unset http.proxy                    # remove  proxy configuration on git
git clone git+ssh://git@192.168.53.168/VT.git             # clone远程仓库
git status                                                # 查看当前版本状态（是否修改）
git add xyz                                               # 添加xyz文件至index
git add .                                                 # 增加当前子目录下所有更改过的文件至index
git commit -m 'xxx'                                       # 提交
git commit --amend -m 'xxx'                               # 合并上一次提交（用于反复修改）
git commit -am 'xxx'                                      # 将add和commit合为一步
git rm xxx                                                # 删除index中的文件
git rm -r *                                               # 递归删除
git log                                                   # 显示提交日志
git log -1                                                # 显示1行日志 -n为n行
git log -5
git log --stat                                            # 显示提交日志及相关变动文件
git log -p -m
git show dfb02e6e4f2f7b573337763e5c0013802e392818         # 显示某个提交的详细内容
git show dfb02                                            # 可只用commitid的前几位
git show HEAD                                             # 显示HEAD提交日志
git show HEAD^                                            # 显示HEAD的父（上一个版本）的提交日志 ^^为上两个版本 ^5为上5个版本
git tag                                                   # 显示已存在的tag
git tag -a v2.0 -m 'xxx'                                  # 增加v2.0的tag
git show v2.0                                             # 显示v2.0的日志及详细内容
git log v2.0                                              # 显示v2.0的日志
git diff                                                  # 显示所有未添加至index的变更
git diff --cached                                         # 显示所有已添加index但还未commit的变更
git diff HEAD^                                            # 比较与上一个版本的差异
git diff HEAD -- ./lib                                    # 比较与HEAD版本lib目录的差异
git diff origin/master..master                            # 比较远程分支master上有本地分支master上没有的
git diff origin/master..master --stat                     # 只显示差异的文件，不显示具体内容
git remote add origin git+ssh://git@192.168.53.168/VT.git # 增加远程定义（用于push/pull/fetch）
git branch                                                # 显示本地分支
git branch --contains 50089                               # 显示包含提交50089的分支
git branch -a                                             # 显示所有分支
git branch -r                                             # 显示所有原创分支
git branch --merged                                       # 显示所有已合并到当前分支的分支
git branch --no-merged                                    # 显示所有未合并到当前分支的分支
git branch -m master master_copy                          # 本地分支改名
git checkout -b master_copy                               # 从当前分支创建新分支master_copy并检出
git checkout -b master master_copy                        # 上面的完整版
git checkout features/performance                         # 检出已存在的features/performance分支
git checkout --track hotfixes/BJVEP933                    # 检出远程分支hotfixes/BJVEP933并创建本地跟踪分支
git checkout v2.0                                         # 检出版本v2.0
git checkout -b devel origin/develop                      # 从远程分支develop创建新本地分支devel并检出
git checkout -- README                                    # 检出head版本的README文件（可用于修改错误回退）
git merge origin/master                                   # 合并远程master分支至当前分支
git cherry-pick ff44785404a8e                             # 合并提交ff44785404a8e的修改
git push origin master                                    # 将当前分支push到远程master分支
git push origin :hotfixes/BJVEP933                        # 删除远程仓库的hotfixes/BJVEP933分支
git push --tags                                           # 把所有tag推送到远程仓库
git fetch                                                 # 获取所有远程分支（不更新本地分支，另需merge）
git fetch --prune                                         # 获取所有原创分支并清除服务器上已删掉的分支
git pull origin master                                    # 获取远程分支master并merge到当前分支
git mv README README2                                     # 重命名文件README为README2
git reset --hard HEAD                                     # 将当前版本重置为HEAD（通常用于merge失败回退）
git rebase
git branch -d hotfixes/BJVEP933                           # 删除分支hotfixes/BJVEP933（本分支修改已合并到其他分支）
git branch -D hotfixes/BJVEP933                           # 强制删除分支hotfixes/BJVEP933
git ls-files                                              # 列出git index包含的文件
git show-branch                                           # 图示当前分支历史
git show-branch --all                                     # 图示所有分支历史
git whatchanged                                           # 显示提交历史对应的文件修改
git revert dfb02e6e4f2f7b573337763e5c0013802e392818       # 撤销提交dfb02e6e4f2f7b573337763e5c0013802e392818
git ls-tree HEAD                                          # 内部命令：显示某个git对象
git rev-parse v2.0                                        # 内部命令：显示某个ref对于的SHA1 HASH
git reflog                                                # 显示所有提交，包括孤立节点
git show HEAD@{5}
git show master@{yesterday}                               # 显示master分支昨天的状态
git log --pretty=format:'%h %s' --graph                   # 图示提交日志
git show HEAD~3
git show -s --pretty=raw 2be7fcb476
git stash                                                 # 暂存当前修改，将所有至为HEAD状态
git stash list                                            # 查看所有暂存
git stash show -p stash@{0}                               # 参考第一次暂存
git stash apply stash@{0}                                 # 应用第一次暂存
git grep "delete from"                                    # 文件中搜索文本“delete from”
git grep -e '#define' --and -e SORT_DIRENT
git gc
git fsck
```
# [IntelliJIDEA](https://www.jetbrains.com/zh-cn/idea/)集成GIT
## 配置Git
菜单栏File->Setting->Version Control->Git  配置Git
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650593406946-ca0befda-6a73-4a1d-a3f1-20a401d8f285.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=529&id=WplbL&margin=%5Bobject%20Object%5D&name=image.png&originHeight=712&originWidth=955&originalType=binary&ratio=1&rotation=0&showTitle=false&size=72278&status=done&style=none&taskId=uf37bd203-8bf6-4e0a-8e78-cfe57004727&title=&width=710)
## 初始化Git仓库
菜单栏VCS ->  Create Git Repository
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650593852161-31985f2b-f0bf-443c-b63e-b3762a488683.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=349&id=u0a3c6ab8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=394&originWidth=809&originalType=binary&ratio=1&rotation=0&showTitle=false&size=335601&status=done&style=none&taskId=u1c2cd08a-e978-429a-93a7-7ac0f9aa25a&title=&width=717)
选择要创建 Git 本地仓库的工程，直接OK即可
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650593870898-a38f1ac6-b84c-4734-b913-478ad66bf375.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=287&id=u27d09969&margin=%5Bobject%20Object%5D&name=image.png&originHeight=358&originWidth=428&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18406&status=done&style=none&taskId=ue93e270d-3a58-4701-aca5-805f04117d9&title=&width=343)
成功之后会有一个.git的文件
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650593897553-3bab91bf-88f7-4bec-9f93-132ab01646f3.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=244&id=u58f9b438&margin=%5Bobject%20Object%5D&name=image.png&originHeight=244&originWidth=775&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20865&status=done&style=none&taskId=u0a9d3cd8-a0b6-4ea6-8151-fa5b9c4c20b&title=&width=775)
## .gitignore
与项目的实际功能无关，不参与服务器上部署运行  把它们忽略掉能够屏蔽 IDE 工具之间的差异
### 安装插件 .ignore 
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650602734593-960165a5-0c11-45b5-9097-8922d5bbcf58.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=616&id=JIMHa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=616&originWidth=952&originalType=binary&ratio=1&rotation=0&showTitle=false&size=75652&status=done&taskId=u4d517034-764a-4e54-8d3f-bdb45a6841a&title=&width=952)
### 配置插件Git模板
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650603189328-1c1da499-1d3f-4c43-ac5a-b5009447b2b3.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=713&id=VbLA4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=713&originWidth=952&originalType=binary&ratio=1&rotation=0&showTitle=false&size=70566&status=done&style=none&taskId=ufadbf491-67d2-42a5-ac3a-c5e2db28d9c&title=&width=952)
```java
# Compiled class file
*.class

# Log file
*.log

# BlueJ files
*.ctxt

# Mobile Tools for Java (J2ME)
.mtj.tmp/

# Package Files #
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar

# virtual machine crash logs, see http://www.java.com/en/download/help/error_hotspot.xml
hs_err_pid*
.classpath
.project
.settings
target
.idea
*.iml
```
### 使用插件创建忽略文件
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650603487399-dda43e91-fecf-49af-8bd6-3bd854f22404.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=479&id=uc3f54cb0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=820&originWidth=1133&originalType=binary&ratio=1&rotation=0&showTitle=false&size=301187&status=done&style=none&taskId=u34e2faac-7c69-4c3e-8620-22c1215c06a&title=&width=662)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650603507654-78cf81c5-0605-4ffb-a59e-444a87854a99.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=375&id=u3d14ab88&margin=%5Bobject%20Object%5D&name=image.png&originHeight=584&originWidth=829&originalType=binary&ratio=1&rotation=0&showTitle=false&size=54159&status=done&style=none&taskId=ue9bf158a-429f-4118-9816-1862e78cd0b&title=&width=532)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650603527740-a3cb15cb-c393-4dc4-abd7-1cffb0f4cd23.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=489&id=ua9a49a3c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=622&originWidth=839&originalType=binary&ratio=1&rotation=0&showTitle=false&size=642505&status=done&style=none&taskId=u0ce19ddd-2ef3-45db-813c-f5dd56f420b&title=&width=659)
## 文件添加暂存区
### add添加
Git->Add
添加成功后，文件名会从红色变成绿色
三种范围的添加

- 类添加
- 包添加
- 项目添加

![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650606413734-452c63ab-8299-4765-a810-839a5d01dd2a.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=812&id=u2bb5925c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=812&originWidth=769&originalType=binary&ratio=1&rotation=0&showTitle=false&size=254072&status=done&style=none&taskId=u1548a8a2-2f02-4f2c-8038-532a55c4dac&title=&width=769)
### 自动添加
创建文件时候询问
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650606796159-7dc4b47a-44d7-4490-af09-e479c3fa5275.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=450&id=u9b8a1baa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=450&originWidth=867&originalType=binary&ratio=1&rotation=0&showTitle=false&size=449088&status=done&style=none&taskId=u4fb7a573-14bd-4fc9-aa80-d776dc70f6a&title=&width=867)
## 暂存区添加本地仓库
Git->Commit Directory
添加成功后，文件名会从绿色变成黑色
三种范围的添加

- 类添加
- 包添加
- 项目添加

![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650606502657-23ee7f21-aa58-4d94-bb29-7372329cbf88.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=750&id=u685dd9c1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=827&originWidth=733&originalType=binary&ratio=1&rotation=0&showTitle=false&size=255530&status=done&style=none&taskId=ud0263d6a-555d-4c2e-95f3-5226e589d84&title=&width=665)
添加提交信息提交
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650606618368-ef92b510-4909-4f05-ade4-f237b06ca12d.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=240&id=ub356b99b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=442&originWidth=1225&originalType=binary&ratio=1&rotation=0&showTitle=false&size=692226&status=done&style=none&taskId=ud86dac1c-02fa-4af7-a782-b530239889f&title=&width=664)
添加成功 查看版本信息
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650606720908-fbe8c1d1-b241-4495-9451-0c6eedcd3df8.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=252&id=ue066b604&margin=%5Bobject%20Object%5D&name=image.png&originHeight=466&originWidth=1232&originalType=binary&ratio=1&rotation=0&showTitle=false&size=611400&status=done&style=none&taskId=u2add6c1f-8338-4344-b07c-b37ef48d57f&title=&width=666)
## 版本穿梭
在 IDEA 的左下角，点击 Git，然后点击 Log 查看版本
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650607090865-809daa74-7489-4624-9196-54abe5bc931d.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=468&id=u33af26ac&margin=%5Bobject%20Object%5D&name=image.png&originHeight=468&originWidth=1265&originalType=binary&ratio=1&rotation=0&showTitle=false&size=763361&status=done&style=none&taskId=uaf89a3ba-1091-4627-88fc-4c698c77715&title=&width=1265)
右键选择要切换的版本，然后在菜单里点击 Checkout Revision
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650607199450-a76e7ce1-8c2f-4590-822e-5a8c52651c42.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=416&id=u65406625&margin=%5Bobject%20Object%5D&name=image.png&originHeight=416&originWidth=529&originalType=binary&ratio=1&rotation=0&showTitle=false&size=177519&status=done&style=none&taskId=u73f16160-d8d8-4075-825e-9ceeb13cf3a&title=&width=529)
## 创建分支和切换分支
### 创建分支
右下角分支
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650607641925-d192a63f-70ad-49bb-8b4d-8590378b7fac.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=51&id=u25acbd85&margin=%5Bobject%20Object%5D&name=image.png&originHeight=51&originWidth=404&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24320&status=done&style=none&taskId=u5a1d566e-a351-4b25-a8b8-b9a8e0a238e&title=&width=404)
点击New Branch
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650607519301-0807ea30-38bf-4da7-a324-fc9b8d4e00dc.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=286&id=u53a320e7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=286&originWidth=597&originalType=binary&ratio=1&rotation=0&showTitle=false&size=185207&status=done&style=none&taskId=u975958f6-9e11-44ee-86a0-2dedd30b93a&title=&width=597)
创建分支
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650607568808-5482479c-f066-42e3-b146-bdc8b6f56e03.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=167&id=u791625db&margin=%5Bobject%20Object%5D&name=image.png&originHeight=167&originWidth=282&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11027&status=done&style=none&taskId=u2ecb7f50-d9e8-4ca3-8727-3151b31be5d&title=&width=282)
### 切换分支
右下角分支
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650607730514-d19a4c34-d963-4411-b8ec-09bc2bb55ff6.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=62&id=uca17bf0b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=62&originWidth=297&originalType=binary&ratio=1&rotation=0&showTitle=false&size=19695&status=done&style=none&taskId=u3a2ca08b-3620-4794-bafd-fe004916afe&title=&width=297)
选择要切换的分支 checkout    右下角的hot-fix会变为master
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650607776358-a3585741-103b-4683-b878-123a1d232c15.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=266&id=udf8c9b24&margin=%5Bobject%20Object%5D&name=image.png&originHeight=266&originWidth=530&originalType=binary&ratio=1&rotation=0&showTitle=false&size=134238&status=done&style=none&taskId=u49792358-9df6-42f7-8bb4-9c2e9ece278&title=&width=530)
或者在Git的Log窗口直接切换
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650607825093-92390338-5a27-48a8-8778-29a49df2e794.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=391&id=udcafff69&margin=%5Bobject%20Object%5D&name=image.png&originHeight=391&originWidth=937&originalType=binary&ratio=1&rotation=0&showTitle=false&size=443374&status=done&style=none&taskId=ub5310ac4-9ebb-4963-bfc5-449950f6ecc&title=&width=937)
## 合并分支
### 正常合并
切换hot-fix分支修改GitT类，并将其提交
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650608034428-f092e6b6-4423-44cb-a1fa-e840f317c8b3.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=717&id=u20a34256&margin=%5Bobject%20Object%5D&name=image.png&originHeight=717&originWidth=1141&originalType=binary&ratio=1&rotation=0&showTitle=false&size=996696&status=done&style=none&taskId=u6b8aa04f-3823-4413-a8d4-b465ec383aa&title=&width=1141)
切换分支master   右下角的hot-fix会变为master
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650608084227-2149430e-df25-4265-8fa6-33acbfe97aab.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=336&id=u74f038c0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=336&originWidth=357&originalType=binary&ratio=1&rotation=0&showTitle=false&size=97532&status=done&style=none&taskId=ucebe049f-0472-41ca-92d6-32966e17de9&title=&width=357) 
选择hot-fix->Merge into Current
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650608172782-ab465efd-d518-4015-bf3e-2b4546023956.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=360&id=uefff2465&margin=%5Bobject%20Object%5D&name=image.png&originHeight=360&originWidth=442&originalType=binary&ratio=1&rotation=0&showTitle=false&size=150235&status=done&style=none&taskId=u43409e69-6ad3-4bf1-8c30-d7b0ef0653a&title=&width=442)
合并成功
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650608307905-6ae6484a-8860-4e64-825a-393cbf0b9a2a.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=208&id=u0d230f2d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=208&originWidth=531&originalType=binary&ratio=1&rotation=0&showTitle=false&size=160584&status=done&style=none&taskId=ub28092f0-1b2b-4f76-a098-1d533674220&title=&width=531)
### 合并冲突
mater 分支修改GitT并且提交
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650608546130-34049dce-cebf-453f-baf5-17719fd4fe13.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=528&id=uf621d26b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=528&originWidth=950&originalType=binary&ratio=1&rotation=0&showTitle=false&size=653701&status=done&style=none&taskId=u59d272eb-1201-4c9b-82e0-a5333c095a5&title=&width=950)hot-fix 分支修改GitT并且提交![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650608587795-e1016a83-8038-4f58-bc9f-27b2cd17aadc.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=589&id=u5c010f66&margin=%5Bobject%20Object%5D&name=image.png&originHeight=589&originWidth=1056&originalType=binary&ratio=1&rotation=0&showTitle=false&size=817543&status=done&style=none&taskId=u308d040b-f6fb-4220-8e53-3a7c7b8f339&title=&width=1056)
切换到master 分支 将hot-fix分支进行合并
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650608662825-98dcc5f0-9d95-433d-af0d-efa5386d4f25.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=344&id=uaf26a637&margin=%5Bobject%20Object%5D&name=image.png&originHeight=344&originWidth=319&originalType=binary&ratio=1&rotation=0&showTitle=false&size=85356&status=done&style=none&taskId=u5e04c0b8-c5a6-485a-ac81-1af8faa16ba&title=&width=319)
产生冲突需要人工合并
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650608695776-39a196ee-29fd-4962-b316-ebb8d4d37da9.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=538&id=u6d1c65d4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=538&originWidth=807&originalType=binary&ratio=1&rotation=0&showTitle=false&size=165697&status=done&style=none&taskId=ufcaedf4f-8545-4cb6-9f62-4de8018675f&title=&width=807)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650609326418-da0bc4fe-41dc-42d8-a1fb-d008b4be0a19.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=578&id=uf6878075&margin=%5Bobject%20Object%5D&name=image.png&originHeight=578&originWidth=1634&originalType=binary&ratio=1&rotation=0&showTitle=false&size=88477&status=done&style=none&taskId=uab4c5e5f-f1bf-4c3f-af0f-19a5ab14bbe&title=&width=1634)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650609125288-b4a99d19-29d6-4dfc-bf53-524d8baabcea.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=892&id=ua2033c5d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=892&originWidth=1630&originalType=binary&ratio=1&rotation=0&showTitle=false&size=104847&status=done&style=none&taskId=u92d25a18-cce0-4e43-8890-f418fbe9c1a&title=&width=1630)
分支合并成功
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650609172091-332d83c6-a044-4d5d-a703-001e33c6d8b7.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=290&id=u8224f768&margin=%5Bobject%20Object%5D&name=image.png&originHeight=290&originWidth=1146&originalType=binary&ratio=1&rotation=0&showTitle=false&size=452387&status=done&style=none&taskId=u7c495eb3-2cff-4d5b-8bf4-27e157b0b51&title=&width=1146)
# [IntelliJIDEA](https://www.jetbrains.com/zh-cn/idea/)集成GitHub
## GitHub插件安装
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650609962394-fd47fd98-3fc0-4112-991c-aa49098c6a7d.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=712&id=u9395b127&margin=%5Bobject%20Object%5D&name=image.png&originHeight=712&originWidth=959&originalType=binary&ratio=1&rotation=0&showTitle=false&size=67950&status=done&style=none&taskId=u17abbe95-b1f1-459f-8e7a-0280b9267fd&title=&width=959)
## 登陆GitHub
### 创建Token
Settings------>Developer settings------>Personal access tokens   点击creat new token
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650610416392-b77ba73a-7ed8-47c7-a698-475fc34e387d.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=271&id=u0de8260a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=271&originWidth=1049&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25627&status=done&style=none&taskId=u06218867-419a-47ec-9083-e8dbc633a15&title=&width=1049)
填写Token信息 授予时间和权限等
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650610510094-da0a68ad-a160-40e1-bdbd-5b639bcb0428.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=794&id=u35247c69&margin=%5Bobject%20Object%5D&name=image.png&originHeight=794&originWidth=790&originalType=binary&ratio=1&rotation=0&showTitle=false&size=78313&status=done&style=none&taskId=uc8921011-2719-4f2b-9382-7660f77524e&title=&width=790)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650610529124-8a95c2dd-f68d-4727-bb67-e1b1a190d8e3.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=334&id=u0194c054&margin=%5Bobject%20Object%5D&name=image.png&originHeight=334&originWidth=869&originalType=binary&ratio=1&rotation=0&showTitle=false&size=31534&status=done&style=none&taskId=uc72b3f4e-9180-4fe3-a782-21cdfa215ab&title=&width=869)
切记 一定要保存toekn信息
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650610605213-0036ca30-0ae2-4b5b-ab70-ea8cdc3e0fe5.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=319&id=u96130d72&margin=%5Bobject%20Object%5D&name=image.png&originHeight=319&originWidth=771&originalType=binary&ratio=1&rotation=0&showTitle=false&size=30010&status=done&style=none&taskId=u6f1e9783-8f0b-43ee-aecb-2ed13f1b941&title=&width=771)
### Token登陆
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650610651433-62e72d9f-2d1a-4a85-a41e-b78d73b3ba5b.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=707&id=u55cb1b59&margin=%5Bobject%20Object%5D&name=image.png&originHeight=707&originWidth=953&originalType=binary&ratio=1&rotation=0&showTitle=false&size=57398&status=done&style=none&taskId=udab7f3c8-a159-4f06-82d6-8e143fc2481&title=&width=953)
登陆成功
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650610679378-067c74dc-4f7f-4875-aa9a-874b24b22965.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=141&id=ucf2ab604&margin=%5Bobject%20Object%5D&name=image.png&originHeight=141&originWidth=733&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10264&status=done&style=none&taskId=uaff93367-d0dc-42f9-96e4-76ae514865b&title=&width=733)
## 分享项目到远程库
share project on GitHub
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650611230467-7aa5852e-d36b-4430-b2d0-930ac6fd9787.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=451&id=ude84e506&margin=%5Bobject%20Object%5D&name=image.png&originHeight=451&originWidth=782&originalType=binary&ratio=1&rotation=0&showTitle=false&size=167590&status=done&style=none&taskId=ubca6161b-f691-4b28-bc65-008b65099e6&title=&width=782)
设置分享的参数
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650611369574-21e328b3-cae7-49a7-a4b8-6f91be86d804.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=389&id=uba2f59d0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=389&originWidth=673&originalType=binary&ratio=1&rotation=0&showTitle=false&size=142877&status=done&style=none&taskId=u65e7955c-c95f-4bfb-aaa0-c3d46342ac7&title=&width=673)
分享成功
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650611378695-0beda8b0-c98f-49e3-af7e-371a0219b83c.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=61&id=u198a3dcf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=61&originWidth=342&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2596&status=done&style=none&taskId=u47bb56dc-2864-4815-83d4-8fd6d124233&title=&width=342)
## 推送代码到远程库
修改本地代码
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650611986638-55d833d7-078e-42e1-847a-bed1606e81f8.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=370&id=u84408c04&margin=%5Bobject%20Object%5D&name=image.png&originHeight=659&originWidth=1082&originalType=binary&ratio=1&rotation=0&showTitle=false&size=831779&status=done&style=none&taskId=u52ee17df-4e42-4396-8070-9a235ccdbae&title=&width=608)
push代码
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612036523-a5699f72-76d8-45ca-b9cb-2dda1e86373c.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=874&id=ub30fc0f4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1029&originWidth=612&originalType=binary&ratio=1&rotation=0&showTitle=false&size=413034&status=done&style=none&taskId=ue00f2fdd-8243-40c8-8369-01ed01453f5&title=&width=520)
设置SSH推送
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612140685-5f7d2077-5d69-419e-bbb8-b39bb2e356f6.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=169&id=u426aa164&margin=%5Bobject%20Object%5D&name=image.png&originHeight=169&originWidth=337&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6570&status=done&style=none&taskId=u85cfe9e4-e082-4e93-b65f-910ae9812fc&title=&width=337)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612095892-4484504e-24da-49c4-ad62-db1534df4ac3.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=332&id=uc26f7701&margin=%5Bobject%20Object%5D&name=image.png&originHeight=412&originWidth=801&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24223&status=done&style=none&taskId=u2f51e17a-11ad-4f30-86da-354947423f5&title=&width=645)
选择SSH推送并且提交
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612278279-1d8204c9-b70e-49f4-bfba-6318c35df5a1.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=324&id=u54fc8e8d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=403&originWidth=805&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24166&status=done&style=none&taskId=uf9226d82-74c2-4297-a39a-2ed7e042975&title=&width=648)
推送成功
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612288757-07cca4b3-98d7-46d6-b36e-6e810cba28d9.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=40&id=u8759dca0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=40&originWidth=339&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3118&status=done&style=none&taskId=u6aa7ebcd-2bbb-436f-bfef-d073954dbca&title=&width=339)
注意： 
push 是将本地库代码推送到远程库，如果本地库代码跟远程库代码版本不一致，push 的操作是会被拒绝的。
要想 push 成功，一定要保证本地库的版本要比远程库的版本高！
因此一个成熟的程序员在动手改本地代码之前，一定会先检查下远程库跟本地代码的区别！如果本地的代码版本已经落后，切记要先 pull 拉取一下远程库的代码，将本地代码更新到最新以后，然后再修改，提交，推送！
## 拉取远程库的代码
远程库修改  远程拉取到本地库
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612690219-c3e04b57-8f63-4502-8d8c-ec16fa2d0499.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=442&id=u175df6bb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=599&originWidth=714&originalType=binary&ratio=1&rotation=0&showTitle=false&size=36098&status=done&style=none&taskId=u98fb1651-90ac-49ba-9093-7b103a201e0&title=&width=527)
pull代码
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612782996-e78ed202-2aba-47a5-a497-7f2d9708add0.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=812&id=ub8dfb298&margin=%5Bobject%20Object%5D&name=image.png&originHeight=963&originWidth=619&originalType=binary&ratio=1&rotation=0&showTitle=false&size=393865&status=done&style=none&taskId=u9f8c9044-8010-4550-900d-7a80e798416&title=&width=522)
选择SSH拉取
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612734989-48f92e7e-4f26-4f68-806b-c468dbef4792.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=103&id=u3cd715c9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=103&originWidth=451&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6831&status=done&style=none&taskId=u7710dc69-c387-4b53-9559-f793140ee9f&title=&width=451)
拉取成功
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650612928800-eaa085b4-3857-4e4c-b6d6-9173448323fd.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=55&id=ufb1f9e75&margin=%5Bobject%20Object%5D&name=image.png&originHeight=55&originWidth=338&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2343&status=done&style=none&taskId=u8508dc29-dcfc-42d5-827c-282983979e5&title=&width=338)
注意
pull 是拉取远端仓库代码到本地，如果远程库代码和本地库代码不一致，会自动合并，
如果自动合并失败，还会涉及到手动解决冲突的问题。

## 克隆项目到本地库
新建项目
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1649422429893-5b0b2b24-c280-44c1-a3ac-0fab113fe853.png#clientId=u84b90b81-d84e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=117&id=ue8a2aeaf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=117&originWidth=498&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13753&status=done&style=none&taskId=u6fcdd771-bf2f-4c1a-983b-ce46e25c491&title=&width=498)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1649422465596-e5b4b22f-3de0-4038-b577-132cc0723bf2.png#clientId=u84b90b81-d84e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=166&id=u78f793ed&margin=%5Bobject%20Object%5D&name=image.png&originHeight=211&originWidth=809&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17848&status=done&style=none&taskId=ud6d4e2b6-f394-48ad-9cc0-01332478d02&title=&width=635)
获取clone的URL
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1649422450216-9331002a-1b06-461d-bce7-0618bd0821c2.png#clientId=u84b90b81-d84e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=386&id=u5d1dfb3e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=544&originWidth=897&originalType=binary&ratio=1&rotation=0&showTitle=false&size=76358&status=done&style=none&taskId=ucf7b2837-d8b4-41d9-bdca-1740d3eaa2a&title=&width=637)
克隆成功
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1649422476287-c4eec451-d161-4b90-999e-c5d2495ce7b8.png#clientId=u84b90b81-d84e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=480&id=u64df84f6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=805&originWidth=1067&originalType=binary&ratio=1&rotation=0&showTitle=false&size=432864&status=done&style=none&taskId=u8a967853-e075-4a6e-bee2-cbc321b8deb&title=&width=636)
# [IntelliJIDEA](https://www.jetbrains.com/zh-cn/idea/)集成Gitee
## Gitee插件安装
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650615981722-83ad9e57-22ba-493b-a8c5-e62b8cee6ab4.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=532&id=u269e437a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=532&originWidth=1009&originalType=binary&ratio=1&rotation=0&showTitle=false&size=54851&status=done&style=none&taskId=u6f9a7164-debb-4c95-a17a-2ec859ab972&title=&width=1009)
## 登陆Gitee
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650616273961-f8215699-da5a-4206-ae9f-42b3d99158f2.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=587&id=u98c82cb3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=587&originWidth=697&originalType=binary&ratio=1&rotation=0&showTitle=false&size=45054&status=done&style=none&taskId=ufb62efd5-eced-4a2f-92bb-79906cdd97b&title=&width=697)
## 分享代码到远程库
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650616415474-8eb262b9-3bf9-4a1f-9a27-92ac703d7861.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=441&id=u115f69f7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=441&originWidth=384&originalType=binary&ratio=1&rotation=0&showTitle=false&size=128920&status=done&style=none&taskId=u313594a9-2666-4c8d-897e-02d03652e0d&title=&width=384)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650616456031-94500d85-4c55-47e1-956a-d3d2645d0d62.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=244&id=ufde8ebd8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=244&originWidth=453&originalType=binary&ratio=1&rotation=0&showTitle=false&size=96387&status=done&style=none&taskId=u8aed2615-78c2-46e9-a3ae-42241eb788a&title=&width=453)
## 导入GitHub项目
选择要导入的协议及其链接
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650617906081-abb2b85b-5c3f-4202-8fab-f2c042237bd3.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=181&id=ua2fba3f5&margin=%5Bobject%20Object%5D&name=image.png&originHeight=247&originWidth=543&originalType=binary&ratio=1&rotation=0&showTitle=false&size=25445&status=done&style=none&taskId=uebe3356c-ec68-4b92-9c1f-b63b09a1f1d&title=&width=398)
新建仓库
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650617762927-38502882-018a-4d70-925a-5845be39c74f.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=232&id=uc4164db4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=456&originWidth=973&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29120&status=done&style=none&taskId=u3c2ba723-17e6-4285-a227-00f1ce6fb4c&title=&width=496)
导入仓库
![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650617878329-628b962d-b4c2-4869-89cf-f7afbc44f5b0.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=432&id=u5dd51a59&margin=%5Bobject%20Object%5D&name=image.png&originHeight=816&originWidth=937&originalType=binary&ratio=1&rotation=0&showTitle=false&size=47163&status=done&style=none&taskId=u56610e8a-11fb-4c20-b3a5-39863c1b92b&title=&width=496)
导入成功![image.png](https://cdn.nlark.com/yuque/0/2022/png/23219042/1650617951107-c195c526-5f37-4607-a63c-a11e566fc40f.png#clientId=u8827b4e5-31ec-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=287&id=u9547f101&margin=%5Bobject%20Object%5D&name=image.png&originHeight=396&originWidth=931&originalType=binary&ratio=1&rotation=0&showTitle=false&size=35124&status=done&style=none&taskId=u2ef48705-1e2e-44dc-ba83-a741f15957f&title=&width=675)
