---
title: 更改日志（Visual Studio Tools for Unity、Mac）| Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 33a6ac54-d997-4308-b5a0-af7387460849
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: d43542dc78c8bc0eaeb05e1a620edff7a88efa37
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="change-log-visual-studio-tools-for-unity-mac"></a>更改日志（Visual Studio Tools for Unity、Mac）
Visual Studio Tools for Unity 更改日志。

## <a name="1501"></a>1.5.0.1
 发布时间 2018-03-28
 
### <a name="new-features"></a>新增功能

-   **集成：**

    -   添加了对 Unity 项目资源管理器中的额外模板的支持。

## <a name="1500"></a>1.5.0.0
 发布时间 2018-03-21
 
### <a name="new-features"></a>新增功能

-   **集成：**

    -   添加了对检测并附加到通过 USB 连接的 Android 播放器的支持。

## <a name="1403"></a>1.4.0.3
 发布时间 2018-03-05
 
### <a name="new-features"></a>新增功能

-   **项目生成：**

    -   添加了对 Unity 2018.1 中新项目生成器的支持。

-   **集成：**

    -   为专用设置添加了选项面板。

## <a name="1402"></a>1.4.0.2
 发布时间 2018-01-24
 
### <a name="bug-fixes"></a>Bug 修复

-   **项目生成：**

    -   修复了 Mono 版本检测的问题。

-   **集成：**

    -   修复了 2018.1 和插件激活的计时问题。

    -   修复了检测新播放器时的通知。

## <a name="1401"></a>1.4.0.1
 发布时间 2018-01-23
 
### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   修复了双击展开/折叠文件夹

## <a name="1400"></a>1.4.0.0
 发布时间 2017-12-13
 
### <a name="new-features"></a>新增功能

-   **项目生成：**

    -   添加了对 .NET Standard 的支持。

### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   固定自动 pdb 到 mdb 调试符号转换。

## <a name="1301"></a>1.3.0.1
 发布时间 2017-12-12
 
### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   修复了在尝试更改数组大小时对 EditorPrefs.GetBool 的间接调用影响检查器的问题。

-   **向导：**

    -   在插入方法前刷新 roslyn 上下文。

## <a name="1300"></a>1.3.0.0
 发布时间 2017-11-20
 
### <a name="new-features"></a>新增功能

-   **向导：**

    -   添加了“实现 Unity 消息”向导。

    -   添加了对 Mac 7.4 的 VS 中 API 新完成的支持。

## <a name="1200"></a>1.2.0.0
 发布时间 2017-10-23
 
### <a name="new-features"></a>新增功能

-   **调试器：**

    -   增加了对可移植调试符号文件的支持。

### <a name="bug-fixes"></a>Bug 修复

-   **项目生成：**

    -   修复了额外 .dll 扩展名错误添加到程序集文件问题。

    -   不强制 AllowAttachedDebuggingOfEditor Unity，因为现在默认为“true”。

## <a name="1103"></a>1.1.0.3
 发布时间 2017-10-23
 
### <a name="new-features"></a>新增功能

-   **项目生成：**

    -   添加了对 .NET 4.6 配置文件的支持。

## <a name="1102"></a>1.1.0.2
 发布时间 2017-08-08
 
### <a name="new-features"></a>新增功能

-   **调试器：**

    -   如果不确定附加到哪个 Unity，启动“附加到进程”对话框。

-   **项目生成：**

    -   使用 Unity 5.6 时，始终启用不安全编译开关。

## <a name="1101"></a>1.1.0.1
 发布时间 2017-07-20
 
### <a name="new-features"></a>新增功能

-   **集成：**

    -   添加了对本地化资源的支持。

## <a name="1100"></a>1.1.0.0
 发布时间 2017-07-12
 
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
 发布时间 2017-05-04
 
### <a name="bug-fixes"></a>Bug 修复

-   **集成：**

    -   修复了混合和常规项目的活动文档跟踪。

## <a name="1000"></a>1.0.0.0
 发布时间 2017-05-03
