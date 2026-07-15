# 一、什么是 AI Agent？
随着大语言模型（LLM，Large Language Model）的发展，AI 已经不仅仅能够"回答问题"，而是开始能够**主动完成任务**。

传统的大语言模型更像一个"知识渊博的助手"，用户提出问题，它根据训练数据生成答案。

例如：

```plain
用户：
帮我写一个 Python 爬虫。

LLM：
返回一段 Python 代码。
```

整个过程中，大模型只是负责**生成文本**，不会真正去创建文件、运行程序或修改项目。

而 **AI Agent（智能体）** 则是在大模型基础上的进一步发展。

AI Agent 可以理解为：

**大语言模型（LLM） + 工具（Tools） + 记忆（Memory） + 推理（Reasoning） + 行动（Action）**

它不仅能理解用户需求，还可以：

+  自动分析任务 
+  制定执行计划 
+  调用各种工具 
+  修改代码 
+  执行命令 
+  根据执行结果继续下一步 

因此，它更像一个能够自主完成工作的"数字员工"。

---

# 二、部署ClaudeCode&运用
#### 1.先安装claudecode的环境
访问官网：[https://nodejs.org](https://nodejs.org/zh-cn/download)

<!-- 这是一张图片，ocr 内容为：验证你的身份 HTTPS://NODEJS.ORG/ZH-CN 其他收液 在任何地方运行 CREATE AN HTTP SERVER WRITE TESTS READ AND HASH A FILE STREAMS PIPELINE ELINEWOR JAVASCRIPT // SERVER.MJS IMPORT ￥ CREATESERVER ? FROM 'NODE:HTTP'; NODE.JS@是一个免费,开源,跨平台的 CONST SERVER - CREATESERVER((REQ, RES) -> @ JAVASCRIPT运行时环境,它让开发人员能够创建服 RES.WRITEHEAD(200, & 'CONTENT-TYPE'; 'TEXT/PLAIN' 3);  RES.END('HELLO WORLD!\N'); 务器,WEB应用,命令行工具和脚本. 子); // STARTS A SIMPLE HTTP SERVER LOCALLY ON PORT 3000 获取NODE.JSR 10 SERVER.LISTEN(3000,'127.0.0.1',() :>> CONSOLE.LOG('LISTENING ON 127.0.0.1:3000'); 11 12 子); 获取安全支持 13 对于不受支持的NODEJS版本(EOL) 14 WITH   NODE SER.MJS' RUNW 复制到剪贴板 JAVASCRIPT -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784085686352-a235d8c7-786a-4452-bb9d-71ee43f3cd2e.png)

点击安装程序**.msl：**[https://nodejs.org/zh-cn/download](https://nodejs.org/zh-cn/download)点击安装程序**.msl**

<!-- 这是一张图片，ocr 内容为：获得适用于 的 NODE.JSR 且使用 和 LTS WINDOWS V24.18.0 DOCKER NPM 提示 WANT NEW FEATURES SOONER? GET THE LATEST NODEJS VERSION INSTEAD AND TRY THE LATEST IMPROVEMENTS! ,非 DOCKER 对每个操作系统都有特定的安装指导. # 请参考 HTTPS://DOCKER.COM/GET-STARTED/给出的官方文档 非 拉取 NODE.IS DOCKER 镜像: DOCKER PULL NODE:24-ALPINE 非 创建 NODE.IS 容器并启动一个 SHELL 会话: DOCKER RUN -IT --IM --ENTRYPOINT SH NODE:24-ALPINE 1 -IT  非验证NODEJS版本: 10 1 11 NO NODE -V # SHOULD PRINT "V24.18.0". 12 NPM 版本: 13非验证 NPM -V # SHOULD PRINT "1.16.0". 14 复制到剪贴板 POWERSHELL DOCKER是一个容器化平台.如果送到任何问题,请访问DOCKER的网站 平台的NODE.JSR构建. 或者获得适用于 WINDOWS X64 独立文件(.ZIP) WINDOWS安装程序(MSI) -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784085776505-ad29e58a-eff9-4e85-8a5a-34c9c97d75ba.png)

我们可以新建一个空文件夹来保存。

<!-- 这是一张图片，ocr 内容为：ANWA... > AL-AGENT 在AI-AGENT中搜索 夹 修改日期 名称 没有与搜索条件匹配的项. HODE-V24.18.0-X64.MSI WINDOWS INSTALLER PACKAGE(*.MSI) -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784085821818-c79d7bcc-abf0-46d8-a133-70d86ef86ade.png)

双击打开安装程序，这里一直点击下一步即可：

<!-- 这是一张图片，ocr 内容为：名称 NODE.JS SETUP NODE-V24.18.0-X64.MSI END-USER LICENSE AGREEMENT PLEASE READ THE FOLLOWING LICENSE AGREEMENT CAREFULLY NODE.JS IS LICENSED FOR USE AS FOLLOWS: COPYRIGHT NODE.JS CONTRIBUTORS. ALL RIGHTS RESERVED. PERMISSION IS HEREBY GRANTED, FREE OF CHARGE,TO ANY PERSON OBTAINING LA COPY OF THIS SOFTWARE AND ASSOCIATED DOCUMENTATION FILES (THE "SOFTWARE"),TO DEAL IN THE SOFTWARE WITHOUT RESTRICTION,INCLUDING WITHOUT LIMITATION THE RIGHTS TO USE, COPY,MODIFY,MERGE,PUBLISH, DISTRIBUTE,SUBLICENSE, AND/OR SELL COPIES OF THE SOFTWARE, AND TO NIT PERSONS TO WHOM THE SOFTWARE IS FURNISHED TO DO SO, SUBJECT TO PERMIT PERS THE FOLLOWING CONDIFIONS' I ACCEPT THE TERMS IN THE LICENSE AGREEMENT BACK PRINT NEXT CANCEL -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784085977609-3d88360d-4741-49a2-a1a9-38d3bead253e.png)

2.验证node.js环境是否安装成功

安装完成后需要检验node.js

win搜索cmd，然后**以管理员身份运行**<!-- 这是一张图片，ocr 内容为：命令提示符 系统 命令提示符 应用 系统 GIT CM NODE.JS COMMAND PROMPT 打开 以管理员身份运行 VCTL的命令提示符 打开文件位置 搜索WEB11+ 固定到"开始"屏幕 CMD-查看更多搜索结果 固定到任务栏 -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784086131379-bf6fbd37-da32-4f70-9008-a4018b39b484.png)

输入 **node -v**

以及 **npm -v**

<!-- 这是一张图片，ocr 内容为：MICROSOFT WINDOWS IN WS [版本10.0.26200.6584] MICROSOFT CORPORATION.保留所有权利. C:\WINDOWS\SYSTEM32>NODE, APOU -V -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784086264686-f84e83b9-f297-47df-8aa3-f9d4623addd8.png)

<!-- 这是一张图片，ocr 内容为：C:\WINDOWS|SYSTEM32>NPM. NPM -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784086294754-1202cc42-264b-4ffd-b411-d7e52c7a1a91.png)

会显示两者的版本信息（version）就说明安装成功，注意环境是自动在C:/盘不必担心，因为刚刚选择的安装路径是自己选的比如D:/盘

<!-- 这是一张图片，ocr 内容为：C:\WINDOWS\SYSTEM32>N >NODE -V V24.18.0 C:\WINDOWS\SYST SYSTEM32/NPM -V 11.16.0 -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784086307572-731dd04d-0951-42b2-b1b5-8a7551ad51e3.png)

#### 3.接下来设置国内镜像源(方便国内网络的安装)，利用npm下载国内镜像，目的是安装第三方依赖
输入这个命令：

**npm config set registry **[**https://registry.npmmirror.com/**](https://registry.npmmirror.com/)

<!-- 这是一张图片，ocr 内容为：IC:\WINDOWS\SYSTEM32\NPM CONFIG SET REGISTRY HTTPS://REGISTRY.NPMMIRROR.COM (WINDOWELSVETOM22> -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784086639253-5a536351-d3b9-4839-bbc3-2ec07e2f0ac0.png)

#### 4.接下来安装git
找到官网：

[https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)

（我们这里是用Windows安装，往上翻可以找到macOS、Linux安装链接）点击这个链接下载。

<!-- 这是一张图片，ocr 内容为：SUMMARY ABOUT LEARN BOOK CHEAT SHEET VIDEOS EXTERNAL LINKS TOOLS CONTINUE GOBACK REFERENCE INSTALL FIGURE 7.GIT MACOS INSTALLER, COMMUNITY 你也可以将它作为GITHUBFORMACOS的一部分来安装.它们的图形化GIT工具有一个安装命令行工具的选. 项.你可以从GITHUBFORMACOS网站下载该工具,网址为HTTPS://MAC.GITHUB.COM. 在WINDOWS上安装 THIS BOOK IS AVAILABLE IN ENGLISH. 在WINDOWS上安装GIT也有几种安装方法.官方版本可以在GIT官方网站下载.打开HTPS://GIT FULL TRANSLATION AVAILABLE IN SCM.COM/DOWNLOAD/WIN,下载会自动开始.要注意这是一个名为GITFORWINDOWS的项目(也叫做  AZARBAYCAN DILI, MSYSGIT),和GIT 是分别独立的项目;更多信息请访问HTTP://MSYSGIT.GITHUB.IO/. 6B/IAPCKH E3HK 要进行自动安装,你可以使用GITCHOCOLATEY包.注意CHOCOLATEY包是由社区维护的. DEUTSCH. DP.该安装程序包含图形化和命令行版本的GIT.它也能支持 另一个简单的方法是安装GITHUBDESKTOP. 该 ESPANOL, POWERSHELL,提供了稳定的凭证缓存和健全的换行设皆.稍后我们会对这方面有更多了解,现在只要一句 -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784086963757-eefaad49-dc2f-415c-8326-6eff745e625f.png)

这里我们选择Windows x64（默认大部分）

注意：这里可能需要使用到**挂代理（VPN）**否则会卡住。

<!-- 这是一张图片，ocr 内容为：INSTALL LATEST VERSION:2.55.0 (RELEASE NOTES) ABOUT LEARN WINDOWS  BUILDFROM SOURCE LINUX MACOS TOOLS CLICK HERE TO DOWNLOAD THE LATEST(2.55.0(2))X64 VERSION OF GIT FOR WINDOWS.THIS IS THIS IS THE REFERENCE MOST RECENT MAINTAMED BUILD. IT WAS RELEASED 13 DAYS AGO, ON 2026-07-02. INSTALL OTHER GIT FOR WINDOWS DOWNLOADS COMMUNITY STANDALONE INSTALLER  GIT FOR WINDOWS/X64 SETUP. GIT FOR WINDOWS/ARM64 SETUP. THE ENTIRE PRO GIT BOOK  PORTABLE("THUMBDRIVE EDITION") WRITTEN BY SCOTT CHACON AND BEN STRAUB IS AVAILABLE TO READ GIT FOR WINDOWS/X64 PORTABLE. ONLINE FOR FREE. DEAD TREE VERSIONS ARE AVAILABLE ON GIT FOR WINDOWS/ARM64 PORTABLE. AMAZON.COM USING WINGET TOOL INSTALL WINGET TOOL IF YOU DON'T ALREADY HAVE IT, THEN TYPE THIS COMMAND IN COMMAND PROMPT OR POWERSHELL. WINGET INSTALL --ID GIT.GIT -E --SOURCE WINGET THE CURRENT SOURCE CODE RELEASE IS VERSION 2.55.0.IF YOU WANT THE NEWER VERSION,YOU CAN BUILD IT  FROM THE SOURCE CODE. -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784087124748-068dcbe9-7541-4930-b705-4b0b0a191d70.png)

我们依旧是选择之前的node.js所在的文件夹下安装

<!-- 这是一张图片，ocr 内容为：在AI-AGENT中搜索 D(D:)A AL-AGENT 夹 类型 名称 修改日期 没有与搜索条件匹配的项. GIT-2.55.0.2-64-BIT.EXE APPLICATION(*.EXE) -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784087245638-64fba81d-5a9e-4615-8d08-effbe24a1441.png)

下载完之后双击安装：

<!-- 这是一张图片，ocr 内容为：2026/7/1511:24 WINDOWS INSTALLER ... 32,104 KB NODE-V24.18.0-X64.MSI 应用程序 63,916 KB 2026/7/1511:48 GIT-2.55.0.2-64-BIT.EXE -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784087380538-90b543fa-9ede-41f5-9a80-74df208897a2.png)

依旧一路“绿灯”，一直点击下一步。

#### 5.同样验证git是否安装成功
同样cmd”**以管理员身份运行**“，输入命令**git -v，**如果依旧会显示版本信息。说明安装成功。

<!-- 这是一张图片，ocr 内容为：管理员:命令提示符 MICROSOFT WINDOWS [版本 10.0.26200.8655] (C)MICROSOFT CORPORATION.保留所有权利. C:\WINDOWS SYSTEM32>NODE -Y V24.18.0 C:\WINDOWS/SYSTEM32>NPM -Y 11.16.0 IC:\WINDOWS\SYSTEM32>NPM CONFIG SET REGISTRY HTTPS://REGISTRY.NPMMIRROR.COM/ C:\WINDOWS\SYSTEM32>GIT -V GIT VERSION 2.55.0.WINDOWS.2 C:\WINDOWS\SYSTEM32> -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784087517366-579651e2-4701-449a-9ed9-cb3ce4d5f51f.png)

#### 6.继续安装一个软件CC -switch
这个软件不是像上面的安装环境，而是一个：可以把自己选的模型接入到Claude Code智能体中的基础载体。

打开github搜索**cc switch**：[https://github.com/search?q=cc%20switch&type=repositories](https://github.com/search?q=cc%20switch&type=repositories)

<!-- 这是一张图片，ocr 内容为：GITHUB.COM/SEARCH?Q-CC%20SWITCH&TYPEREPOSITORIES CC SWITCH ILTER BY  SORT BY: BEST MATCH 1.2K RESULTS(287 MS) SAVE <> CODE 184M FARION1231/CC-SWITCH STAR SPONSOR 1.2K REPOSITORIES A CROSS-PLATFORM DESKTOP ALL-IN-ONE ASSISTANT FOR CLAUDE CODE, CODEX,OPENCODE,OPENCLAW, GEMINI CLI & HERMES ISSUES 266K AGENT.ONLY OFFICIAL WEBSIT... PULL REQUESTS 357K DESKTOP-APP TYPESCRIPT OPEN-SOURCE RUST DISCUSSIONS 8K SKILLS 5 83 USERS Y 117K - UPDATED 3 HOURS AGO RUST AAARO -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784096521224-836cdc3f-8bdf-4dcb-81a8-88ca070e1a4a.png)

选择编译好的版本：

<!-- 这是一张图片，ocr 内容为：83  CONTRIBUTING CHORE: TOUCH CONFIG FILES TO NORMALIZE COMMIT MESSAGES 4 MONTHS AGO NODE-VERSION SECURITYPOLICY CHORE(RELEASE):V3.17.0 CHANGELOG.MD 2 DAYS AGO 117K STARS DOCS: ADD CONTRIBUTING.MD, SECURITY.MD, AND CODE OF... 3 MONTHS AGO CODE OF CONDUCT.MD 207WATCHING 3 MONTHS AGO CONTRIBUTING.MD DOCS: ADD CONTRIBUTING.MD, SECURITY.MD, AND CODE OF... 品 7.9K FORKS LICENSE 11 MONTHS AGO FEAT ADD PRETTIER FORMATTER AND MIT LICENSE REPORT REPOSITORY 15 HOURS AGO DOCS(README):ADD SUBROUTER SPONSOR ENTRY ACROSS FOUR LOC... README.MD RELEASES 46 DOCS(README): ADD SUBROUTER SPONSOR ENTRY ACROSS FOUR LOC... 15 HOURS AGO README DE.MD CC SWITCH V3.17.0 LATEST 2 DAYS AGO DOCS(README):ADD SUBROUTER SPONSOR ENTRY ACROSS FOUR LOC... 15 HOURS AGO README JA.MD 45 RELEASES README ZH.MD DOCS(README):ADD SUBROUTER SPONSOR ENTRY ACROSS FOUR LOC... 15 HOURS AGO DOCS: ADD CONTRIBUTING.MD, SECURITY.MD, AND CODE OF... SECURITY.MD 3 MONTHS AGO SPONSOR THIS PROJECT SUPPORT.MD DOCS: ADD SUPPORT.MD AND FUNDING.YML 3 MONTHS AGO HTTPS://GITHUB.COM/FARION1231/CC-S... CHORE: TOUCH CONFIG FILES TO NORMALIZE COMMIT MESSAGES 4 MONTHS AGO COMPONENTS. JSON DEPLOYMENTS 5 FEAT/DEEPLINK MULTI ENDPOINTS (#597) 6 MONTHS AGO DEPLINK.HTML RELEASE INACTIVE 2 DAYS AGO CHORE(RELEASE):V3.17.0 PACKAGE.JSON -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784096595798-ebf3051d-19de-45ac-9532-c4376b595f4f.png)

这里我们选择windows.msi

<!-- 这是一张图片，ocr 内容为：CC-SWITCH-V3.17.0-LINUX-X86_64.APPLMAGE.SIG 2 DAYS AGO SHA256:7EE37237FE519A88... 424 BYTES RELEASE LIST CC-SWITCH-V3.17.0-LINUX-X86_64.DEB 12.1 MB SHA256:1D457532C5BC39FD.. 2 DAYS AGO CC SWITCH V3.17.0 CC SWITCH V3.16.5 12.1 MB SHA256:B40296D11DD4D81A... 2 DAYS AGO CC-SWITCH-V3.17.0-LINUX-X86_64.RPM CC SWITCH V3.16.4 2 DAYS AGO 25 MB CC-SWITCH-V3.17.0-MACOS.DMG  SHA256:18647EF31CC8A3A2. CC SWITCH V3.16.3 SHA256:A6959CDE3BD901A5."  CC-SWITCH-V3.17.0-MACOS.TAR.GZ 2 DAYS AGO 25.6 MB CC SWITCH V3.16.2 408 BYTES CC SWITCH V3.16.1 2 DAYS AGO  SHA256:C373E0D1B33ED4BA. CC-SWITCH-V3.17.0-MACOS.TAR.GZ.SIG CC SWITCH V3.16.0 SHA256:579EBE794E429177.. CC-SWITCH-V3.17.0-MACOS.ZIP 25MB 2 DAYS AGO CC SWITCH V3.15.0 CC-SWITCH-V3.17.0-WINDOWS-ARM64-PORTABLE.ZIP 2 DAYS AGO SHA256:8A5D28A8F7DB96CE 114 MB CC SWITCH V3.14.1  SHA256:E3B5C01D4D12914F.. CC-SWITCH-V3.17.0-WINDOWS-ARM64.MSI 2 DAYS AGO 11.4 MB CC SWITCH V3.14.0 CC-SWITCH-V3.17.0-WINDOWS-ARM64.MSI.SIG 2 DAYS AGO SHA256:DCB1296DA5632FDB_ 424 BYTES PREVIOUS NEXT 2 DAYS AGO SHA256:5B42F100EC654C60.. CC-SWITCH-V3.17.0-WINDOWS-PORTABLE.ZIP 12 MB 2 DAYS AGO 12 MB SHA256:C541E1981023CC5C... CC-SWITCH-V3.17.0-WINDOWS.MSI EHA356,0693D0NB6F050F01 L O CE C.UIT -2170ULIMD,USSIS -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784096657795-7228eb27-0d0a-4bd2-8739-9c81a7bd58ca.png)

由于是未识别，所以会弹出告警，没关系，我们“仍要运行”

<!-- 这是一张图片，ocr 内容为：WINDOWS 已保护你的电脑 名称 MICROSOFT DEFENDER SMARTSCREEN阻止了无法识别的应用启动.运行此应用 GIT-2.55.0.2-64-BIT.EXE 可能会导致你的电脑存在风险. 更多信息 NODE-V24.18.0-X64.MSI CC-SWITCH-V3.17.0-WINDOWS.M -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784096719740-f89d5814-5edd-4538-b0f3-7470986edb3a.png)

这里默认是安装包所在路径，可以切换到刚刚新文件夹下

<!-- 这是一张图片，ocr 内容为：CC SWITCH SETUP DESTINATION FOLDER CLICK NEXT TO INSTALL TO THE DEFAULT FOLDER OR CLICK CHANGE TO CHOOSE ANOTHER. INSTALL CC SWITCH TO: D:/ANWANG\AI-AGENT\CC SWITCH\ CHANGE... CANCEL BACK NEXT -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784096775525-51b8c745-cb65-4991-a8fc-c72bae76312a.png)

打开后是这个样子，可以进行接入我们的LLM。

<!-- 这是一张图片，ocr 内容为：X O CC SWITCH 米 CC SWITCH 不使用项目 CLAUDE OFFICIAL 不支持路由 HTTPS://WWW.ANTHROPIC.COM/CLAUDE-CODE -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784096850983-1ca05acf-3e39-4be5-8f35-fcc67c835062.png)



#### 7.接下来正是安装Claude Code


**npm install -g @anthropic-ai/claude-code**

（注意，这里不要切目录，默认打开cmd下目录直接安装，否则环境会出问题）

<!-- 这是一张图片，ocr 内容为：管理员:命令提示符 MICROSOFT WINDOWS [版本 10.0.26200.8655] (C)MICROSOFT CORPORATION.保留所有权利. IC:\WINDOWS\SYSTEM32>NPM INSTALL -G @ANTHROPIC-AI/CLAUDE-CODE ADDED 2 PI 2 PACKAGES IN 3S ALLOW-SCRIPTS 1 PACKAGE HAS INSTALL SCRIPTS NOT YET COVERED BY ALLOWSCRIPTS: NPM WARN QANTHROPIC-AI/CLAUDE-CODE@2.1.210 (POSTINSTALL:NODE INSTALL.CJS) ALLOW-SCRIPTS NPM WARN NPM WARN ALLOW-SCRIPTS NPM APPROVE-SCRIPTS --ALLOW-SCRIPTS-PENDING TO REVIEW, NPM APPROVE-SCRIPTS <PKG> TO AL ALLOW-SCRIPTS RUN OR NPM WARN OW. C:\WINDOWS\SYSTEM32> -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784097444463-c77bfc69-dcea-4d19-a163-705537856ec1.png)

显示安装路径：

**npm config get prefix**

<!-- 这是一张图片，ocr 内容为：C:\WINDOWS\SYSTEM32>N ONPM CONFIG GET PREFIX C:\USERS\86187\APPDATA\ROAMING\NPM -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784097483544-c6519164-e490-4174-8471-3067ae798022.png)

验证是否安装成功，会依旧弹出版本信息。

**claude --version**

<!-- 这是一张图片，ocr 内容为：C:\WINDOWS\SYSTEM32>CLAUDE --VERSION 2.1.210 (CLAUDE CODE) -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784097516028-5037bdfc-5a46-45ee-a3eb-970a3c9e2123.png)



#### 8.启动claude！
cmd输入claude会提示我们修改配置信息：

**claude**

<!-- 这是一张图片，ocr 内容为：C:\WINDOWS\SYSTEM32>CLAUDE WELCOME TO CLAUDE CODE ODE V2.1.210 水 水 水 水 UNABLE TO CONNECT TO ANTHROPIC SERVICES I FAILED TO CONNECT TO API. ANTHROPIC.COM: ERR BAD REQUEST PLEASE CHECK YOUR INTERNET CONNECTION AND NETWORK SETTINGS. NOTE: CLAUDE CODE MIGHT NOT BE AVAILABLE IN YOUR COUNTRY. CHECK SUPPORTED COUNTRIES AT HTTPS://ANTHROPIC.COM/SUPPORTED-COUNTRIES -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784097566944-f16ce498-6587-4e74-becc-0845a08bff19.png)

在文件管理器中路径输入框输入我们的当前用户名。

win+L看锁屏是哪个名称就是哪个。

<!-- 这是一张图片，ocr 内容为：在九位 九亿 九亿 建 -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784097738154-a83b803c-5a8c-40c9-b75a-8fc90389babf.png)

这里我们要打开隐藏文件显示。

<!-- 这是一张图片，ocr 内容为：个排序 查看 名称 大小 类型 超大图标 文件夹 .ANDROID 大图标 文件夹 .BIGNOX 中图标 文件夹 .BITO OO 小图标 00 文件夹 .CACHE 列表 文件夹 .CC-SWITCH 详细信息 文件夹 .CLAUDE 8二平铺 文件夹 .CODEGEEX 内容 文件夹 .CONDA 文件夹 .CONFIG 详细信息窗格 文件夹 .CONTINUE 预览窗格 .COPILOT 显示 导航窗格 DOCKER GUCULUICO TUIOJ 紧凑视图 2023/10/2019:31 DOUYU CHANNEL 项目复选框 2024/3/5 ECLIPSE 2026/7/415:21 .FITTEN 文件扩展名 2026/6/2415:34 .FSCAN 隐藏的项目 文件夹 2026/7/1010:47 GHCP-APPMOD -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784097794366-9d98e4e8-f99e-461c-af86-e71640707cbf.png)

找到这个.claude.json文件打开进行修改

<!-- 这是一张图片，ocr 内容为：联系人 2025/10/23 14:31 文件夹 文件夹 链接 2025/10/23 14:31 文件夹 视频 2026/1/210:29 搜索 文件夹 2025/10/23 14:31 文件夹 2025/10/23 14:31 图片 文件夹 文档 2026/7/149:24 文件夹 下载 2026/7/1420:14 音乐 文件夹 2025/10/23 14:31 文件夹 2026/7/15 14:26 桌面 1 KB BASH_HISTORY文件 2026/7/3 10:06 BASH HISTORY JSON源文件 1 KB 2026/7/15 14:39 .CLAUDE.JSON NPMRC文件 1 KB 2026/7/1511:37 NPMRC 2026-06-06-09-36-13.031-ABOXHEADLESS.E... TEXT DOCUMENT 1 KB 2026/6/617:36 7Z文件 1 KB 2026/6/8 20:11 D4AC4633EBD6440FA397B84F1BC94A3C.7Z 文件 2026/4/1114:27 O KB HTML -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784097828440-335bd8a3-629c-4f2e-8076-3b45dc22c17a.png)

记事本或代码环境打开：

(用全英文包括标点符号)在最后一行加入"hasCompletedOnboarding":true

！并且别忘了在上一行也就是原本没修改之前的最后一行末尾加上"**,**"英文逗号。

<!-- 这是一张图片，ocr 内容为：好 .CLAUDE.JSON C >USERS>86187>F1 CLAUDEJSON >&Z HASCOMPLETEDONBOARDING 丁 1 "FIRSTSTARTTIME"; 2 3 "MACHINEID" 'OPUSPROMIGRATIONCOMPLETE": 4 5 SONNET1M45MIGRATIONCOMPLETE 好 CATIONS 9 SEENNOTIFI 7 HASRESETAUTOMODEOPT 8 MIGRATIONVERSION 9 USERID": CHANGELOGLASTFETCHED''; 10 "HASCOMPLETEDONBOARDING";TRUE 11 12 -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784097951740-03586d52-0937-4a90-9653-e3694330779b.png)

然后重新在cmd输入**claude**启动我们的ClaudeCode

这里我们选择1.相信这个文件夹（相当于claude在这个文件夹下启动，后续换文件夹也会弹出，但是如果运行过的一次就不需要了），回车确定。

<!-- 这是一张图片，ocr 内容为：QUICK SAFETY CHECK: THIS P TEA PROJECT,OR WORK FROM YOUR T CLAUDE CODE 'LL BE AB1 TO READ SECURITY GUIDE > 1.YES,I TRUST THIS FOLDER 2.NO,EXIT -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784098390239-d164976e-93dd-4140-b2e4-c81461acc548.png)

然后可以看到我们的😀启动了，但是这是智能体，我们需要通过cc switch接入LLM来让agent能识别并接入调用。

<!-- 这是一张图片，ocr 内容为：-CLAUDE CODE TIPS FOR GETTING STARTED CLAUDE.MD FILE WITH INSTRUCTIONS FOR CLAUDE /INIT TO WELCOME BACK! RUN O CREATE A CL WHAT'S NEW ADDED A LIVE ELAPSED-TIME COUNTER TO THE COLLAPSED TOOL SUMMARY LIN Y LIN. ADDED A STARTUP WARNING FOR NOTEBOOKEDIT (PATH), WRITE(PATH) ),AN' 1 GIT-MUTAT... SUBAGENTS BEING ABLE TO RUN GI FIXED ISOLATION: WORKTREE' API USAGE BILLING OPUS 4.8 (1M CONTEXT) RELEASE-NOTES FOR MORE C:\WINDOWS SYSTEM32 LOGGED IN * RUN /LOGIN NOT FORSHORTCUTS FOR MANUAL MODE ON AGENTS -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784098416415-5ae0223c-84e1-4396-b332-2c873cfe36d6.png)

#### 9.接入自己选的模型
我们打开cc switch，点击默认主页面的右上角加号➕添加新的LLM。

<!-- 这是一张图片，ocr 内容为：添加新供应商 CLAUDE供应商 统一供应商 个是 预设供应商 胜算云 自定义配置 KIMI CLAUDE OFFICIAL KIMI FOR CODING 火山AGENTPLAN PATEWAYAI BYTEPLUS CCSUB DOUBAOSEED 七牛云 UNITY2.AI FENNOAI ZETAAPI SUBROUTER GEMINI NATIVE DEEPSEEK OPENCODE GO TEAMOROUTER AMUX BAILIAN FOR CO... BAIDU QIANFAN ZHIPU GLM EN ZHIPUGLM BAILIAN 与LS STEPFUN MODELSCOPE STEPFUN EN KAT-CODER LONGCAT MINIMAX EN MINIMAX BAILING IN CHERRYIN AIHUBMIX -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784099203104-034ccd7e-5f3b-46ea-91a2-91e5b7d286ea.png)

我们选择deepseek

<!-- 这是一张图片，ocr 内容为：添加新供应商 乐 备注 供应商名称 例如:公司专用账号 官网链接 HTTPS://EXAMPLE.COM  (可选) API KEY 请求地址 完整URL 管理与测速 Q HTTPS:// 选择预设后,请在下方填写APIKEY等字段 添加 取消 -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784099473707-7237d0e3-fde1-42ca-8bd4-f3964cff9901.png)

这里填写请求地址：如果是官网会直接在获取API时给个apikey，网址就是官网地址；如果是中转站则填写相应url，但是注意不要专门https://**.**/v1专门填写个v1，因为测试过会自动在后端加，并且不要以"**/**"结尾。

点击请求地址右侧的“管理与测速”看看配置的是否能联通。

<!-- 这是一张图片，ocr 内容为：1个端点 测速 自动选择 HTT 123MS -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784099496835-2cb26c9d-3c71-46ab-ab18-d7b8df3d051c.png)

要把下面的不同类型模型都换成这个。

<!-- 这是一张图片，ocr 内容为：添加新供应商 一斑攻直 侯坐映射 状取娱坐列衣 显示名称只影响/MODEL 菜单;1M 只是给 CLAUDE CODE的上下文能力声明. 模型角色 实际请求模型 显示名称 声明支持1M DEEPSEEK-V4-FLASH 1M DEEPSEEK-V4-FLASH SONNET OPUS 1M DEEPSEEK-V4-FLASH DEEPSEEK-V4-FLASH FABLE DEEPSEEK-V4-FLASH 1M DEEPSEEK-V4-FLASH DEEPSEEK-V4-FLASH DEEPSEEK-V4-FLASH HAIKU 不显示在/MODEL菜单 SUBAGENT 1M DEEPSEEK-V4-FLASH 默认兜底模型 1M DEEPSEEK-V4-FLASH 用于来明确系列SONNAL,OPUS,FABLE,HAKU角色的语来,使用碧三方(中转输点时建议执与;香则这些语来(含HAID' 模型名透传给上游,可能因上游无此模型而报错.官方端点可留空. 添加 选择预设后,请在下方填写APIKEY等字段 取消 -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784099457976-d3c5c5cb-bebc-465d-9eb1-538315f1b3be.png)

接下来回到claudecode，输入**/model，**可以看到当前部署的是哪个模型。

/model

<!-- 这是一张图片，ocr 内容为：MODEL SELECT MODEL I CLAUDE MODELS. YOUR PICK BECOMES THE DEFAULT FOR NEW SESSIONS. FOR OTHER/PREVIOUS MODEL NAMES SWITCH BETWEEN CLAT SPECIFY WITH --MODEL. USE THE DEFAULT MODEL (CURRENTLY DEEPSEEK-V4-FLASH[LM]) 1. DEFAULT (RECOMMENDED) 2. DEEPSEEK-V4-FLASH CUSTOM OPUS MODEL 3. DEEPSEEK-V4-FLASH CUSTOM FABLE MODEL DEEPSEEK-V4-FLASH 4. ! CUSTOM SONNET MODEL 5. DEEPSEEK-V4-FLASH CUSTOM HAIKU MODEL 6. DEEPSEEK-V4-FLASH CUSTOM MODEL HIGHEFFORT (DEFAULT) -/ TO ADJUST -->
![](https://cdn.nlark.com/yuque/0/2026/png/66872828/1784099584274-dfffe627-b66a-4979-a3ec-ce0723b7dcf5.png)



#### 10.使用claude做实操
1.可以作为编程人员做项目：创建个文本，然后在文本所在目录打开cmd，启动claude，可以告诉他要对这个文本做什么事，比如写个JS+Html并且进行css美化。

2.其他可拓展的边界，我这里是尝试测试对于漏洞的边界在哪里......



# 三、AI Agent 与 LLM 的区别
| 对比项 | LLM（大语言模型） | AI Agent（智能体） |
| --- | --- | --- |
| 本质 | 语言生成模型 | 基于 LLM 构建的智能执行系统 |
| 是否主动 | 否 | 是 |
| 是否能执行命令 | × | √ |
| 是否能调用工具 | 很少 | √ |
| 是否具备记忆 | 有限 | 可以长期记忆 |
| 是否能够完成复杂任务 | 一般 | 可以 |
| 是否会规划步骤 | 不会 | 会 |


例如：

让它开发一个博客系统。

### LLM
```plain
帮你写首页代码。

结束。
```

下一步需要用户继续提问。

---

### AI Agent
```plain
① 分析需求

② 创建项目

③ 安装依赖

④ 编写前后端

⑤ 创建数据库

⑥ 测试

⑦ 修复 Bug

⑧ 运行项目
```

整个过程几乎无需人工干预。

---

### AI Agent 是如何衍生出来的？
AI Agent 并不是一种新的模型。

它是在 **LLM 的基础上增加了多个能力模块**。

```plain
用户需求
               │
               ▼
        大语言模型（LLM）
               │
        理解任务、推理
               │
    ┌──────────┼──────────┐
    │          │          │
 Tools      Memory    Planning
工具调用      记忆        任务规划
    │          │          │
    └──────────┼──────────┘
               │
            Action
            执行动作
               │
               ▼
         返回最终结果
```

因此可以认为：

**AI Agent = LLM + Tool + Memory + Planning + Action**

LLM 是 Agent 的"大脑"。

Agent 是让大脑真正能够工作的"身体"。

---

# 四、什么是 Claude Code？
Claude Code 是 Anthropic 推出的 **Agentic Coding Tool（智能编码 Agent）**。

它并不是一个新的大模型。

它底层依然使用 Claude 系列模型（如 Claude Opus、Claude Sonnet）作为推理核心。

Claude Code 更像：

一个拥有终端、文件系统、Git、编辑器等能力的软件工程 Agent。

它可以：

+  阅读整个项目 
+  理解代码结构 
+  自动修改多个文件 
+  执行 Shell 命令 
+  Git Commit 
+  修复 Bug 
+  编写测试 
+  自动运行测试 
+  根据测试结果继续修改代码 

例如：

```plain
帮我把 Flask 项目改成 FastAPI。
```

Claude Code 会：

```plain
分析项目

↓

读取所有代码

↓

修改 requirements

↓

修改 import

↓

修改路由

↓

更新配置

↓

运行测试

↓

修复错误

↓

完成迁移
```

整个过程基本无需人工参与。

这就是 Agent 与普通聊天机器人的最大区别。

---

# 五、Claude Code 的特点
### ① 理解整个代码仓库
不是只看一个文件。

它能够：

+  阅读所有目录 
+  建立代码关系 
+  分析依赖 
+  理解项目架构 

---

### ② 自动修改代码
例如：

```plain
把登录模块改成 JWT。
```

Claude Code 会：

修改：

```plain
auth.py

login.py

config.py

requirements.txt

README.md
```

甚至自动补充测试。

---

### ③ 自动执行终端命令
例如：

```plain
npm install

pytest

git status

docker compose up
```

Claude Code 都可以自动完成。

---

### ④ 多步推理
例如：

```plain
Bug：
登录失败
```

Claude Code 会：

```plain
查看日志

↓

分析代码

↓

定位 Bug

↓

修改代码

↓

重新运行

↓

确认成功
```

不像普通聊天模型只告诉你：

"可能是 XX 原因。"

---

# 六、DeepSeek 在 AI Agent 中的应用
DeepSeek 是由深度求索（DeepSeek）推出的大语言模型。

它本身**不是 AI Agent**，而是可以作为 Agent 的底层模型。

很多开源 Agent 框架都支持接入 DeepSeek，例如：

+  OpenHands 
+  OpenManus 
+  Strix 
+  AutoGen 
+  LangGraph 
+  CrewAI 

在这些框架中：

```plain
Agent
      │
      ▼
 DeepSeek-V3
 DeepSeek-R1
```

DeepSeek 负责：

+  推理 
+  代码生成 
+  问题分析 

而 Agent 框架负责：

+  工具调用 
+  文件修改 
+  命令执行 
+  工作流控制 

因此：

**DeepSeek 提供智能，Agent 提供行动能力。**

---

# 七、Claude Code 与 DeepSeek 的关系
很多人容易误解：

Claude Code 和 DeepSeek 是竞争关系。

实际上：

Claude Code 是一个 **Agent 产品**。

DeepSeek 是一个 **LLM**。

两者不是同一层面的产品。

可以理解为：

```plain
Claude Code
    │
    ├── Claude Sonnet
    └── Claude Opus

OpenHands
    │
    ├── DeepSeek
    ├── Qwen
    ├── GPT
    └── Gemini
```

Claude Code 深度绑定 Claude 模型；而像 OpenHands 等开源 Agent 框架则可以根据配置切换不同的大模型，包括 DeepSeek。

