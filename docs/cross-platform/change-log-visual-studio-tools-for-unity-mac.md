---
title: 更改日志（Visual Studio Tools for Unity、Mac）| Microsoft Docs
ms.custom: ''
ms.date: 11/13/2018
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 33a6ac54-d997-4308-b5a0-af7387460849
author: therealjohn
ms.author: johmil
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 0b641c9dd1fe797fc036a6ece893ad61fc52ff87
ms.sourcegitcommit: 5c049194fa256b876ad303f491af11edd505756c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53027232"
---
# <a name="change-log-visual-studio-tools-for-unity-mac"></a>更改日志（Visual Studio Tools for Unity、Mac）
Visual Studio Tools for Unity 更改日志。

## <a name="1700"></a>1.7.0.0
 发布时间：2018 年 11 月 13 日

### <a name="new-features"></a>新增功能

-   **调试器：**

    -   在“附加”对话框中添加了更多客户端信息（IP、计算机名称）。

### <a name="bug-fixes"></a>Bug 修复

-   **调试器：**

     -   修复了用于与 Unity 调试器引擎进行通信的库中的死锁，此死锁会导致 Visual Studio 或 Unity 冻结，尤其是在用户点击“附加到 Unity”或重启游戏时。
     
-   **集成：**

     -   修复了选中另一个默认编辑器时 Unity 插件的激活。
     
     -   修复了 Unity 文件模板创建。

## <a name="1602"></a>1.6.0.2
 发布时间：2018 年 7 月 24 日

### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

     -   回滚了针对 Unity 性能缺陷的解决方案（此缺陷已由 Unity 修复）。
     
## <a name="1601"></a>1.6.0.1
 发布时间：2018 年 7 月 10 日

### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

     -   支持固定着色器代码着色。
     
## <a name="1600"></a>1.6.0.0
 发布时间：2018 年 6 月 26 日

### <a name="bug-fixes"></a>Bug 修复

-   **向导：**

    -   修复了 OnApplicationFocus 消息拼写错误。

-   **项目生成：**

     -   Unity 性能 Bug 的暂时解决方法：生成项目时缓存 MonoIsland。
     
     -   使用新版 Unity 运行时，不要再将可移植 pdb 转换为 mdb。
     
## <a name="1502"></a>1.5.0.2
 发布时间：2018 年 4 月 18 日
 
### <a name="new-features"></a>新增功能

-   **集成：**

    -   添加了对基本着色器代码补全的支持。
    
    -   添加了对在着色器文件中切换注释的支持。

## <a name="1501"></a>1.5.0.1
 发布时间：2018 年 3 月 28 日
 
### <a name="new-features"></a>新增功能

-   **集成：**

    -   添加了对 Unity 项目资源管理器中的额外模板的支持。

## <a name="1500"></a>1.5.0.0
 发布时间：2018 年 3 月 21 日
 
### <a name="new-features"></a>新增功能

-   **集成：**

    -   添加了对检测并附加到通过 USB 连接的 Android 播放器的支持。

## <a name="1403"></a>1.4.0.3
 发布时间：2018 年 3 月 5 日
 
### <a name="new-features"></a>新增功能

-   **项目生成：**

    -   添加了对 Unity 2018.1 中新项目生成器的支持。

-   **集成：**

    -   为专用设置添加了选项面板。

## <a name="1402"></a>1.4.0.2
 发布时间：2018 年 1 月 24 日
 
### <a name="bug-fixes"></a>Bug 修复

-   **项目生成：**

    -   修复了 Mono 版本检测的问题。

-   **集成：**

    -   修复了 2018.1 和插件激活的计时问题。

    -   修复了检测新播放器时的通知。

## <a name="1401"></a>1.4.0.1
 发布时间：2018 年 1 月 23 日
 
### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   修复了双击展开/折叠文件夹

## <a name="1400"></a>1.4.0.0
 发布时间：2017 年 12 月 13 日
 
### <a name="new-features"></a>新增功能

-   **项目生成：**

    -   添加了对 .NET Standard 的支持。

### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   固定自动 pdb 到 mdb 调试符号转换。

## <a name="1301"></a>1.3.0.1
 发布时间：2017 年 12 月 12 日
 
### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   修复了在尝试更改数组大小时对 EditorPrefs.GetBool 的间接调用影响检查器的问题。

-   **向导：**

    -   在插入方法前刷新 roslyn 上下文。

## <a name="1300"></a>1.3.0.0
 发布时间：2017 年 11 月 20 日
 
### <a name="new-features"></a>新增功能

-   **向导：**

    -   添加了“实现 Unity 消息”向导。

    -   添加了对 Mac 7.4 的 VS 中 API 新完成的支持。

## <a name="1200"></a>1.2.0.0
 发布时间：2017 年 10 月 23 日
 
### <a name="new-features"></a>新增功能

-   **调试器：**

    -   增加了对可移植调试符号文件的支持。

### <a name="bug-fixes"></a>Bug 修复

-   **项目生成：**

    -   修复了额外 .dll 扩展名错误添加到程序集文件问题。

    -   不强制 AllowAttachedDebuggingOfEditor Unity，因为现在默认为“true”。

## <a name="1103"></a>1.1.0.3
 发布时间：2017 年 10 月 23 日
 
### <a name="new-features"></a>新增功能

-   **项目生成：**

    -   添加了对 .NET 4.6 配置文件的支持。

## <a name="1102"></a>1.1.0.2
 发布时间：2017 年 8 月 8 日
 
### <a name="new-features"></a>新增功能

-   **调试器：**

    -   如果不确定附加到哪个 Unity，启动“附加到进程”对话框。

-   **项目生成：**

    -   使用 Unity 5.6 时，始终启用不安全编译开关。

## <a name="1101"></a>1.1.0.1
 发布时间：2017 年 7 月 20 日
 
### <a name="new-features"></a>新增功能

-   **集成：**

    -   添加了对本地化资源的支持。

## <a name="1100"></a>1.1.0.0
 发布时间：2017 年 7 月 12 日
 
### <a name="new-features"></a>新增功能

-   **集成：**

    -   添加了对通过“附加到进程”窗口附加到播放器和编辑器的支持。

-   **项目生成：**

    -   修复了使用 mcs.rsp 文件的程序集名称引用。

    -   添加了对 assembly.json 编译单元的支持。    

    -   修复了通过 API 级别进行定义的问题。    

### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   修复了编译时的着色器错误消息。

## <a name="1001"></a>1.0.0.1
 发布时间：2017 年 5 月 4 日
 
### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   修复了混合和常规项目的活动文档跟踪。

## <a name="1000"></a>1.0.0.0
 发布时间：2017 年 5 月 3 日
