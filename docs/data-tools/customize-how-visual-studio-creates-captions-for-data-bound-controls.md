---
title: 自定义 Visual Studio 创建数据绑定控件的标题的方式
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- Label captions, Data Sources window
- smart captions
- captions, data-bound
- Data Sources Window, label captions
ms.assetid: 6d4d15f8-4d78-42fd-af64-779ae98d62c8
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 69e97efe6db8b06f476b7dc004e3b52a77701cb0
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758415"
---
# <a name="customize-how-visual-studio-creates-captions-for-data-bound-controls"></a>自定义 Visual Studio 创建数据绑定控件的标题的方式

当将项从[数据源窗口](add-new-data-sources.md)拖到设计器，特别注意派上用场： 标题标签中的列名称重新格式化为可读性更强的字符串，当两个或更多的词语发现连接在一起。 你可以自定义在其中这些标签的创建的方式，通过设置**SmartCaptionExpression**， **SmartCaptionReplacement**，并**SmartCaptionSuffix**中的值**HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\15.0\Data 设计人员**注册表项。

> [!NOTE]
> 在创建之前，此注册表项不存在。

智能隐藏式字幕控制正则表达式的值中输入**SmartCaptionExpression**值。 添加**数据设计器**注册表项重写默认正则表达式，用于控制标题标签。 有关正则表达式的详细信息，请参阅[在 Visual Studio 中使用正则表达式](../ide/using-regular-expressions-in-visual-studio.md)。

下表介绍控件标题标签的注册表值。

|注册表项|描述|
|-------------------|-----------------|
|**SmartCaptionExpression**|用于与您的模式匹配正则表达式。|
|**SmartCaptionReplacement**|要显示中匹配的任何组的格式**SmartCaptionExpression**。|
|**SmartCaptionSuffix**|若要追加到末尾的标题的一个可选字符串。|

下表列出了这些注册表值的内部默认设置。

|注册表项|默认值|说明|
|-------------------|-------------------|-----------------|
|**SmartCaptionExpression**|**(\\\p{Ll}) (\\\p{Lu})&#124;_ +**|匹配后跟一个大写字符或下划线的小写字符。|
|**SmartCaptionReplacement**|**$1 2 美元**|**1 美元**表示匹配在第一个表达式，表达式的括号中的任意字符以及 **$2**表示匹配在第二个括号中的任意字符。 替换为第一个匹配项、 空格和第二个匹配项。|
|**SmartCaptionSuffix**|**:**|表示字符追加到返回的字符串。 例如，如果标题是`Company Name`，后缀使得 `Company Name:`|

> [!CAUTION]
> 你应执行任何操作在注册表编辑器时请格外小心。 在编辑之前备份注册表。 如果在注册表编辑器使用不当可能导致严重的问题，可能需要重新安装操作系统。 Microsoft 不保证可以解决通过注册表编辑器使用不当导致的问题。 使用注册表编辑器的风险由您自己承担。
>
> 以下知识库文章包含有关备份、 编辑和还原注册表的说明： [Microsoft Windows 注册表说明](http://support.microsoft.com/default.aspx?scid=kb;en-us;256986)(http://support.microsoft.com/default.aspx?scid=kb; en-我们; 256986)

## <a name="modify-the-smart-captioning-behavior-of-the-data-sources-window"></a>修改智能隐藏式字幕行为的数据源窗口

1.  通过单击打开命令窗口**启动**，然后**运行**。

2.  类型`regedit`中**运行**对话框中，然后单击**确定**。

3.  展开**HKEY_CURRENT_USER** > **软件** > **Microsoft** > **VisualStudio**节点。

7.  右键单击**15.0**节点，并创建一个新**密钥**名为`Data Designers`。

8.  右键单击**数据设计器**节点，并创建三个新的字符串值：

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`

11. 右键单击**SmartCaptionExpression**值，然后选择**修改**。

12. 输入所需的正则表达式**数据源**窗口来使用。

13. 右键单击**SmartCaptionReplacement**值，然后选择**修改**。

14. 输入替换字符串格式设置你想要显示在正则表达式中匹配的模式的方式。

15. 右键单击**SmartCaptionSuffix**值，然后选择**修改**。

16. 输入你想要显示的标题末尾的任何字符。

    下一次将项从**数据源**窗口中，创建标题标签使用提供的新注册表值。

## <a name="turn-off-the-smart-captioning-feature"></a>关闭隐藏字幕的智能功能

1.  通过单击打开命令窗口**启动**，然后**运行**。

2.  类型`regedit`中**运行**对话框中，然后单击**确定**。

3.  展开**HKEY_CURRENT_USER** > **软件** > **Microsoft** > **VisualStudio**节点。

7.  右键单击**15.0**节点，并创建一个新**密钥**名为`Data Designers`。

8.  右键单击**数据设计器**节点，并创建三个新的字符串值：

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`

11. 右键单击**SmartCaptionExpression**项，然后选择**修改**。

12. 输入`(.*)`的值。 这将匹配整个字符串。

13. 右键单击**SmartCaptionReplacement**项，然后选择**修改**。

14. 输入`$1`的值。 这将字符串替换匹配的值，该值是整个字符串，以便将保持不变。

    下一次将项从**数据源**窗口中，与未修改的标题创建标题标签。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中将控件绑定到数据](../data-tools/bind-controls-to-data-in-visual-studio.md)