# Why Do You Need The Command Line

这节课我们来聊聊一个让很多纯新手感到畏惧，但咱们做 DevOps 和后端开发绝对离不开的“黑框框”——**命令行（Command Line）**。

讲师专门为 PC（Windows）用户录制了这节前置课，主要目的是打破大家对终端的恐惧，并解释为什么学习 Python 必须掌握基础的命令行操作。如果你已经熟悉如何在终端里创建文件和切换目录，完全可以跳过这一部分，直接进入环境配置章节。

---

## GUI 与命令行的降维打击
* **图形用户界面 (GUI)**：也就是我们从小习惯的操作系统界面，靠鼠标“双击打开文件夹”、“拖拽移动文件”来工作。它很直观，但效率存在天花板。
* **命令行接口 (CLI)**：基于纯文本的交互界面。虽然看起来没有图形界面漂亮，甚至有些枯燥，但它速度更快、权限更高、功能更强大。讲师在视频中演示了一个简单的指令，瞬间就能列出电脑后台运行的数百个隐藏进程，这是普通图形界面很难高效做到的。
* **极客属性**：它就像是电影里黑客们运指如飞、屏幕上疯狂滚动文本的那个界面。

## 为什么学 Python 必须死磕命令行？
* **最核心的目的：执行代码**。在这门课中，我们不需要你成为系统底层的命令行大师。学习命令行的核心刚需只有一个：**我们需要它来运行 Python 脚本**。
* **标准工作流**：在后续的课程中，你的工作流往往是这样的：先在代码编辑器里写好代码，保存为文件放在某个文件夹下（比如桌面）。然后，你需要通过命令行“导航”到那个文件夹，最后敲下类似 `python myfile.py` 的命令来执行它。
* **拒绝“玩具”环境**：讲师坚持教命令行，是因为这是真实工业界里开发者的日常工作方式，比使用一些屏蔽了底层逻辑的傻瓜式图形界面工具更有利于你建立扎实的工程素养。

## 给新手的心理建设与学习目标
* **不要被吓到**：真正需要我们掌握的只是很小的一个子集。主要目标就是三个：基本的目录导航、文件的创建/操作，以及最关键的——用 Python 执行文件。
* **先慢后快**：对于高度依赖鼠标的新手来说，初期用键盘敲命令绝对会觉得繁琐、没有效率。但请保持耐心，这是成长为一名合格工程师（特别是 DevOps/SRE 领域）的必经之路，习惯之后它的效率会远超图形界面。



# Using Powershell

这节课正式带我们进入终端实操环节。由于讲师在后续课程中使用的是 Mac 环境，为了让 Windows (PC) 用户能够无缝跟练，他专门介绍了 **PowerShell**。作为 DevOps 工程师，我们非常清楚不同操作系统底层内核的差异，而 PowerShell 就是用来弥合这种差异的绝佳工具。

---

## 操作系统底层的“门派之争”
* **Unix 系的统一战线**：Mac 和大部分 Linux 操作系统底层都基于 Unix 架构，这意味着它们共享着几乎完全相同的终端命令行语法（比如创建文件、列出目录等）。
* **Windows 的历史包袱**：Windows 拥有完全不同的内核架构。在过去，它一直使用自己独有的一套命令行语法（即基于 MS-DOS 的 Command Prompt / cmd），这导致 Windows 的命令和 Mac/Linux 完全不互通。

## 破局者：为什么是 PowerShell？
* **跨平台体验的桥梁**：为了解决这种系统割裂感，讲师要求 PC 用户使用 PowerShell。它的核心优势在于**允许你在 Windows 上使用类似 Unix 的命令**。
* **无缝跟练**：因为讲师全程使用 Mac 授课，如果 Windows 用户使用 PowerShell，就可以直接照抄讲师屏幕上的基础指令。这也是目前绝大多数在 Windows 上做开发的程序员的首选终端工具（除非你折腾虚拟机或 WSL）。
* **开箱即用**：好消息是，从 Windows 7 开始，所有现代 Windows 系统都已经默认内置了 PowerShell，无需任何繁琐的额外安装过程。

## 首次点亮终端：实操演示
* **如何启动**：操作非常简单，直接点击 Windows 左下角的开始菜单，搜索“PowerShell”并点击运行即可。
* **严格的指令校验**：如果你在终端里随便敲一通乱码并回车，系统会立刻返回红字报错，提示不认识该指令。这说明命令行只接受符合规范的特定关键词。
* **你的第一个命令：`ls`**
    * 在 PowerShell 中输入 `ls`（List 的缩写）并回车，它会列出你当前所在目录（通常是你的用户主文件夹）下的所有内容，你会看到 Desktop（桌面）、Downloads（下载）等熟悉的文件夹。
    * **强烈的对比**：讲师演示了如果你在老式的 Command Prompt (cmd) 里输入 `ls`，系统会直接报错。这直观地证明了为什么要抛弃老旧的 cmd，全面拥抱 PowerShell。

## 准备进入正题
搞定统一的终端环境后，操作系统的壁垒就被彻底打通了。接下来，课程将正式告别前置准备，迅速进入真正的 Python 安装与编码环节。





# Paths, LS, and PWD

本节课我们继续深挖命令行操作，重点讲解了文件系统结构（Paths）、以及两个最常用的定位命令：`pwd` 和 `ls`。

讲师通过“家谱树”的比喻，向大家普及了操作系统是如何层级化管理文件和文件夹的。如果你已经对绝对路径（Absolute Path）、相对路径（Relative Path）以及根目录（Root Directory）的概念了然于胸，这节课同样可以快速刷过。但对于没有系统概念的新手，这是未来能顺利找到并执行 Python 代码的核心基础。

## 操作系统文件结构与路径 (Paths)

* **树状层级结构**：无论是 Mac 还是 PC，操作系统都以树状结构（Hierarchy/Tree structure）来组织数据，包含父目录和子目录的嵌套关系。
* **根目录 (Root Directory)**：这是文件系统的最顶层。在 Windows PC 上，它通常用反斜杠 `\` 来表示。
* **绝对路径 (Absolute Path)**：从根目录开始，完整描述一个文件或文件夹位置的路径。例如 `\Users\Colt`，每进入下一层级都需要用反斜杠隔开。

## 认识主目录 (Home Directory)

* **什么是主目录**：在 PC 上，它通常指的是你当前登录的用户账户专属文件夹（User Account Directory）。
* **专属符号 `~` (Tilde)**：在命令行中，波浪号 `~`（通常在键盘 Tab 键的上方）是主目录的专属代称。
* **默认起点**：每当你打开一个新的 PowerShell 窗口时，系统默认都会把你放置在这个主目录中。

## 核心命令：pwd (Print Working Directory)

* **功能**：它的全称是 Print Working Directory（打印工作目录）。当你迷失在错综复杂的文件夹树中时，输入 `pwd` 并回车，系统会输出你当前所在的完整绝对路径。
* **使用场景**：虽然 PowerShell 的提示符（Prompt）通常已经默认显示了当前路径，但在某些其他终端或极简环境下，`pwd` 是你确认自己“身在何处”的最可靠手段。

## 核心命令：ls (List)

* **功能**：列出（List）当前所在目录下的所有内容（包括文件和子文件夹）。
* **配合使用**：通常我们通过 `pwd` 确认自己在哪里，然后用 `ls` 看看当前目录下都有什么，这是在没有图形界面时，我们在系统里“睁开眼睛”看世界的最佳组合。

## 下节预告

目前我们还被困在主目录里，只能“看”不能“动”。在下一节课中，我们将学习如何使用命令来切换和移动目录，真正实现系统内的自由穿梭。



# Using The CD Command

本节课详细讲解了如何使用 `cd` (Change Directory) 命令在文件系统中前进和后退。配合上一节课的 `pwd` 和 `ls`，这三个命令构成了终端操作的“导航三剑客”。讲师对比了绝对路径与相对路径的使用场景，并传授了 Tab 键补全、快捷返回上级目录等极大提升终端效率的实战技巧。

---

## 核心命令：cd (Change Directory)
* **核心功能**：它的作用是改变当前所在的工作目录。你可以把它理解为图形界面里的“双击进入文件夹”或“点击返回上一层”。
* **斜杠的系统差异 (Mac vs PC)**：讲师在 Mac 上演示时使用的是正斜杠 `/`，而在 Windows PC 的绝对路径中，传统上使用的是反斜杠 `\`。不过在 PowerShell 中，为了兼容性，通常两者都能被正确识别，但理解这个历史差异对排查路径报错很有帮助。

## 绝对路径 vs 相对路径的导航艺术
* **绝对导航 (Absolute Navigation)**：无论你当前身在文件系统的哪个角落，直接输入从根目录开始的完整路径进行跳转。例如：`cd \Users\Colt`。这种方式绝对精准，但在深层嵌套的目录里敲起来会非常繁琐。
* **相对导航 (Relative Navigation)**：基于你**当前所在的位置**进行跳转，这是我们在终端中最常用的方式。
* **返回上一级 (`..`)**：如果你在 `stuff` 文件夹里，想要退回到上一级的 `Colt` 文件夹，不需要敲一长串绝对路径，只需输入 `cd ..` 即可。“`..`” 是一个特殊的系统级符号，代表上一级（父）目录。你可以连续使用，比如不断输入 `cd ..` 直到退回系统的根目录。

## 提升效率的终端神技
* **Tab 键自动补全 (Auto-complete)**：这是所有程序员最爱的按键。比如你要进入 `Desktop` 目录，只需输入 `cd d` 或者 `cd des`，然后按下 `Tab` 键，系统会自动帮你把剩下的字母补全。如果首字母相同的文件夹有多个，多按几次 Tab 可以在它们之间循环切换。这不仅极大地节省了敲键盘的时间，还能从根本上避免路径拼写错误。
* **一键回老家 (`cd ~`)**：波浪号 `~` 代表用户主目录（Home Directory）。无论你迷失在文件系统的哪个深层渊薮，只要敲下 `cd ~`，就能瞬间传送回你的主目录。
* **一键去根目录 (`cd \`)**：直接跳转到文件系统的最顶层（例如 Windows 的 C 盘根目录）。日常开发中用得相对较少，但偶尔需要直接访问系统级文件时会用到。

## 终端大扫除与终极目标预演
* **清屏命令 (`clear`)**：当你在终端里敲了太多的 `ls` 和 `cd`，满屏都是杂乱的历史输出时，只需输入 `clear` 并回车，屏幕瞬间清空，回到最顶端。这是程序员保持专注力的强迫症福音。
* **我们的终极目标**：讲师在视频中再次强调，我们费这么大劲学习这些终端目录切换，目的只有一个——找到你的 Python 文件，然后敲下类似 `python mycode.py` 的命令去执行它。这是我们这门课，也是未来真实开发的日常基本盘（Bread and Butter）。



# OPTIONAL Making Directories with MKDIR

这节课我们来学习终端操作的另一个高频命令——如何使用命令行来创建文件夹（目录）。在 DevOps 的日常工作中，不管是初始化项目环境、挂载数据卷，还是归档日志，创建目录都是基石操作。

如果你觉得用命令行建文件夹太抽象，讲师也给出了非常务实的建议：直接右键新建文件夹完全没问题，关键是你要能用终端“找”到它。

---

## 核心命令：mkdir (Make Directory)
* **命令渊源**：`mkdir` 是 "make directory" 的缩写。它与 Linux/Unix 系统中的命令完全一致，在 PowerShell 中同样完美适用。
* **基本语法**：只需要敲下 `mkdir`，加一个空格，然后跟上你想要创建的文件夹名称即可。例如：`mkdir cat_pics`。
* **执行逻辑**：该命令会在你**当前所在的工作目录**（Current Directory）下，直接创建一个新的子文件夹（Child Folder）。

## 实操组合拳：创建、查看与进入
* **创建新目录**：假设你当前在桌面（Desktop），输入 `mkdir cat_pics` 并回车，桌面上就会瞬间多出一个名为 `cat_pics` 的文件夹。你可以在图形界面中直观地看到它冒出来。
* **丝滑连招**：创建完之后，你可以立刻结合前两节课学到的“导航”命令：
  * 先输入 `ls`：查看当前目录内容，验证新文件夹是否成功生成。
  * 再输入 `cd cat_pics`：利用 Tab 键补全，直接潜入你刚刚创建的新文件夹中，准备在里面部署代码。

## 极客视角：CLI vs GUI 的底层逻辑
* **直接操控系统大动脉**：讲师将命令行生动地比喻为“直接接入电脑大动脉的主管道（a main line into the artery of your computer）”。相比于图形界面（GUI）那几层厚厚的抽象封装，命令行剥离了视觉糖衣，让你以更底层、更直接的方式干预系统。
* **务实的工程观**：虽然纯键盘操作熟练后效率极高，但讲师的态度非常务实开放：如果你作为初学者觉得用 `mkdir` 建立文件夹非常痛苦，甚至打击了你学 Python 的积极性，那么**请毫不犹豫地退回到鼠标右键去“新建文件夹”**。
* **目标导向（Result-Oriented）**：这门课的核心是 Python。不管你的文件夹是用酷炫的命令敲出来的，还是用鼠标点出来的，对于 Python 解释器来说没有任何区别。我们的终极底线是：**你必须能用命令行导航（cd）到那个文件夹，并执行里面的代码**。

## 下节预告
学会了创建文件夹，下一节课我们将补齐终端基础操作的最后一块拼图：如何直接创建文件（Files）。搞定这些，我们就彻底扫清了环境障碍，正式进军 Python 领地！



# OPTIONAL Making Files (it's...complicated)

这节课讲的是终端操作中相对比较“心累”的部分：如何在 PowerShell 中创建一个新文件。讲师非常坦诚地表示，相比于 Unix 系统（Mac/Linux）那行云流水的 `touch` 命令，Windows 的原生命令行在建文件这件事上显得有些“笨拙”且语法冗长。作为 DevOps 工程师，我非常认同讲师的观点：工具是为了效率服务的，如果命令行让你感到痛苦，那就换种更直观的方式。

---

## 为什么在 Windows 上建文件很“坑”？
* **Unix 的优雅**：在 Mac 或 Linux 上，创建一个空文件只需要输入 `touch app.py`，简洁明了。
* **PowerShell 的无奈**：PowerShell 并没有内置 `touch` 这个命令。虽然它功能强大，但在创建文件的语法上非常“啰嗦”（Verbose），这可能会让刚接触命令行的初学者感到沮丧。

## 方案一：Echo 加上重定向符号
* **语法**：`echo $null >> slide.py`
* **逻辑**：`$null` 代表空，`>>` 代表将内容（这里是空）注入到指定的文件中。
* **致命陷阱（编码问题）**：这是做开发最容易踩的坑。PowerShell 默认使用 **UTF-16** 编码创建文件，而 Python 3 强烈要求文件必须是 **UTF-8** 编码。
* **后果**：如果你直接这样创建 Python 文件并运行，可能会看到类似 `non-UTF-8 code` 的报错。你必须在编辑器里手动将编码改为 UTF-8 才能正常运行。

## 方案二：使用 New-Item 命令
* **语法**：`New-Item -ItemType File swings.py`
* **评价**：这是 PowerShell 官方推荐的方式，虽然能成功创建文件，但这一长串字符敲起来实在太累了。讲师直言，除非你是强迫症，否则很少有人愿意每次都打这么长一串。

## 程序员的务实建议：使用文本编辑器
* **回归直觉**：如果你觉得上面的命令很难记，完全可以直接打开你的文本编辑器（如 Sublime Text, VS Code 或 Notepad）。
* **操作流**：`文件` -> `新建文件` -> `保存` -> `选择文件夹（如桌面上的 playground 目录）` -> `重命名为 xxx.py`。
* **不要有心理负担**：讲师强调，即便你是一个经验丰富的开发者，也经常会直接在编辑器里保存文件，而不是非要在终端里炫技。

## 核心任务：找到并运行
* **目标导向**：不管你是用哪种方式创建的文件，我们的核心需求只有一个——**在终端里找到它并运行**。
* **工作流演示**：
  1. 打开一个新的 PowerShell 窗口。
  2. `cd Desktop\playground`（导航到文件所在目录）。
  3. `ls`（确认文件就在那）。
  4. `python monkey_bars.py`（用 Python 执行它）。
* **总结**：只要你能熟练掌握 `cd` 和 `ls` 来定位文件，你的命令行基础就已经及格了。

## 下节预告
学会了创建文件夹和文件，最后我们要学习如何“毁尸灭迹”——如何删除它们。搞定删除命令后，我们就完成了终端操作的完整闭环。



# Creating a Touch Function

Creating a Touch Function

Thanks to Zachary for originally posting this on the discussion board!

Rather than typing the long/ugly command to create a new file using powershell, you can set up a **custom function** to mimic the touch command you'll see me use on my mac.

## Creating a temporary function

If you were to run the following in your terminal:

```
function touch {New-Item -ItemType File -Name ($args[0])}
```

 it will create a temporary function (temp meaning while that instance of PowerShell is open) that will allow you to type:

```
touch filename
```



## Creating a "permanent" function



To make this a "permanent" change it just needs to be added to the PowerShell profile found at:

```
C:\Users\USERSNAMEHERE\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

Note that you need to alter the above path to reflect your actual username.

First run:

```
Test-Path $PROFILE
```

to check if a profile file already exist.

If `True` , then navigate to the above location and copy and paste in the function line. Restart PowerShell.

If `False` , then enter the below command to create a new empty profile: **(ONLY DO IF NO PROFILE IS FOUND AS THE -force FLAG WILL OVERWRITE ANY EXISTING PROFILE)**

```
New-Item -Path $PROFILE -Type File -force
```



At this point navigate to the above profile location and paste in the function. Restart PowerShell. You can now type touch to create new empty files encoded with UTF-8.



# Windows Powershell 配置

**配置 Powershell 的环境变量**

以管理员身份运行一个powershell，执行下面的代码，这样powershell就可以加载环境变量文件不会报错

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

新建一个文件夹 

```go
$HOME\Documents\WindowsPowerShell
```

创建一个文件，这个文件里面保存了一个函数，加载之后就可以使用 touch 函数创建文件

```go
$HOME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

右键编辑这个文件，粘贴保存

```go
function touch {New-Item -ItemType File -Name ($args[0])}
```

![image-20260407004211862](http://imgs.ilee.xyz/img/20260407020053513.png)



**增加右键，打开 powershell 窗口**

![image-20260407004052646](http://imgs.ilee.xyz/img/20260407020049520.png)

在任意一个位置，创建一个注册表文件，然后导入

```go
Windows Registry Editor Version 5.00

; --- 在文件夹空白处右键 ---
[HKEY_CLASSES_ROOT\Directory\Background\shell\PowerShellAdmin]
@="以管理员身份运行 PowerShell"
"Icon"="powershell.exe"

[HKEY_CLASSES_ROOT\Directory\Background\shell\PowerShellAdmin\command]
@="powershell.exe -Command \"Start-Process powershell.exe -ArgumentList '-NoExit', '-Command', 'Set-Location -LiteralPath ''%V''' -Verb RunAs\""

; --- 在文件夹图标上右键 ---
[HKEY_CLASSES_ROOT\Directory\shell\PowerShellAdmin]
@="以管理员身份运行 PowerShell"
"Icon"="powershell.exe"

[HKEY_CLASSES_ROOT\Directory\shell\PowerShellAdmin\command]
@="powershell.exe -Command \"Start-Process powershell.exe -ArgumentList '-NoExit', '-Command', 'Set-Location -LiteralPath ''%1''' -Verb RunAs\""
```

保存的时候，编码必须是 ANSI

![image-20260407003517992](http://imgs.ilee.xyz/img/20260407020041212.png)

双击导入这个注册表文件

![image-20260407003602307](http://imgs.ilee.xyz/img/20260407014920143.png)



# OPTIONAL: Removing Files and Folders with RM

本节课我们迎来了终端基础操作的最后一环：**删除文件与文件夹（rm 命令）**。讲师演示了如何在命令行中执行删除操作，但也发出了强烈的“高危警告”。如果你觉得敲代码删除文件太容易失误，完全可以退回到图形界面，把文件拖进回收站。课程最后，讲师也给大家打了一剂“定心丸”：如果之前的命令行知识让你感到挫败，不要灰心，你真正需要死磕的只有 `cd` 和 `ls`。

---

## 终端里的“橡皮擦”：删除单文件
* **核心命令**：`rm` (Remove 的缩写)。
* **基本语法**：输入 `rm`，加一个空格，然后跟上文件名。例如：`rm swings.py`。
* **残酷的真相**：与图形界面不同，使用 `rm` 命令删除的文件**不会**进入回收站（Recycling Bin）。它会绕过回收机制，直接在文件系统中“灰飞烟灭”。所以在敲下回车前，请务必确认你真的不需要它了。

## 危险的“大杀器”：删除文件夹
* **为什么复杂**：删除一个空文件夹和删除一个装满成百上千个子文件夹的目录，在系统底层的逻辑是不同的。因此，删除文件夹的命令要“啰嗦”得多。
* **完整语法**：`rm -r -fo playground`
* **参数硬核拆解**：对于初次接触命令行的同学，这两个参数（Flags）至关重要：
  * **`-r` (Recursive/递归)**：这是一个经典的计算机科学概念。它告诉系统：“不要只删最外面那层皮，给我钻进去，把里面的每一层子文件夹、每一个文件统统删光，直到彻底清空。”
  * **`-fo` (Force/强制)**：阻止系统弹出任何警告提示。它代表着一种绝对的机器执行力：别废话，直接删。

## SRE 视角的安全守则
* **威力巨大，后果自负**：讲师特别警告，如果你不小心在你的用户主目录（Home Directory）或者根目录运行了这个带有强制递归参数的命令，它会瞬间摧毁你的系统或大量个人数据（也就是咱们做运维常说的“删库跑路”级别的灾难）。
* **防呆设计**：好在这个命令足够长，你几乎不可能因为“手滑”而意外敲出 `rm -r -fo`。但每次使用 Tab 键补全路径时，依然要瞪大眼睛看清楚后面跟的到底是什么文件夹。

## 讲师的“定心丸”：抓住核心痛点
* **允许挫败感**：讲师非常坦诚，把命令行这种枯燥且硬核的内容放在课程最开头，确实容易劝退新手。如果你感到不知所措，这非常正常。
* **最低及格线**：忘掉如何用命令行建文件、删文件夹吧！你能用鼠标搞定的，就用鼠标搞定。**你在这门课唯一必须掌握的命令行技能就是：使用 `cd` 移动位置，使用 `ls` 查看文件，然后去执行 Python。**
* **进入正题**：熬过了枯燥的环境配置与终端教学，你可以选择做一下随堂小测验，或者直接跳到下一章。接下来，我们将正式开始安装 Python 并写下第一行真正的代码！
