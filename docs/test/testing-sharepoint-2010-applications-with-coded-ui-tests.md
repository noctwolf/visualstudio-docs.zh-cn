---
title: 使用编码的 UI 测试来测试 SharePoint 应用程序
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 8b2851d436e9cef64f8a03c3f794d07f12cd0cf8
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55912750"
---
# <a name="test-sharepoint-applications-with-coded-ui-tests"></a>使用编码的 UI 测试来测试 SharePoint 应用程序

通过在 SharePoint 应用程序中包含编码的 UI 测试，您可以验证整个应用程序（包括其 UI 控件）是否正常工作。 编码的 UI 测试还可以验证 UI 中的值和逻辑。

若要详细了解使用编码的 UI 测试的好处，请参阅[使用 UI 自动化来测试代码](../test/use-ui-automation-to-test-your-code.md)。

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

**要求**

- Visual Studio Enterprise

## <a name="create-a-coded-ui-test-for-a-sharepoint-app"></a>为 SharePoint 应用创建编码的 UI 测试

为 SharePoint 应用程序[创建编码的 UI 测试](../test/use-ui-automation-to-test-your-code.md)与为其他类型的应用程序创建测试相同。 支持对“Web 编辑”界面上的所有控件进行录制和播放。 选择类别和 Web 部件的接口都是标准 Web 控件。

![SharePoint Web 部件](../test/media/cuit_sharepoint.png)

> [!NOTE]
> 如果要录制操作，请在生成代码前验证操作。 因为有多种行为与鼠标悬停操作关联，所以它在默认情况下处于开启状态。 注意从编码的 UI 测试中移除冗余的悬停操作。 为此，您可以编辑测试的代码，或者使用 [编码的 UI 测试编辑器](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)。

## <a name="test-office-controls-within-a-sharepoint-app"></a>测试 SharePoint 应用中的 Office 控件

若要对 SharePoint 应用中的某些 Office Web 部件实现自动化，必须作出一些细微的代码修改。

> [!NOTE]
> 不支持测试 SharePoint 应用程序中的 Visio 和 PowerPoint 控件。

### <a name="excel-cell-controls"></a>Excel 单元格控件

若要包括 Excel 单元格控件，则必须在编码的 UI 测试代码中做一些更改。

> [!WARNING]
> 如果在任何 Excel 单元格中输入文本，然后进行箭头键操作，将无法正确进行录制。 使用鼠标选择单元格。

如果要录制对空单元格的操作，则必须双击该单元格，然后执行设置文本操作，以此修改代码。 这是必需的，因为如果单击单元格，然后进行任何键盘操作，会激活单元格内的 `textarea`。 如果只是录制对空单元格的 `setvalue` ，将会搜索直到单击单元格后才会显示的 `editbox` 。 例如:

```csharp
Mouse.DoubliClick(uiItemCell,new Point(31,14));
uiGridKeyboardInputEdit.Text=value;
```

如果要录制对非空单元格的操作，则稍微有些复杂，因为在向单元格添加文本时，将会添加一个新的 \<div> 控件作为此单元格的子项。 新的 \<div> 控件包含刚才输入的文本。 记录器需要录制对新 \<div> 控件的操作；但是，它无法进行录制，因为新 \<div> 控件直到进入测试后才会存在。 您必须手动对代码做出以下更改，才能解决这一问题。

1. 转到单元格初始化，将 `RowIndex` 和 `ColumnIndex` 作为主要属性：

    ```csharp
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. RowIndex] = "3";
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. ColumnIndex] = "3";
    ```

2. 找到单元格的 `HtmlDiv` 子项：

    ```csharp
    private UITestControl getControlToDoubleClick(HtmlCell cell)
    {
         if (String.IsNullOrEmpty(cell.InnerText)) return cell;
         HtmlDiv pane = new HtmlDiv(cell);
         pane.FilterProperties[HtmlDiv.PropertyNames.InnerText] = cell.InnerText;
         // Class is an important property in finding pane
         pane.FilterProperties[HtmlDiv.PropertyNames.Class] = "cv-nwr";
         UITestControlCollection panes = pane.FindMatchingControls();
         return panes[0];
    }
    ```

3. 添加 `HtmlDiv`鼠标双击操作的代码：

    ```csharp
    Mouse.DoubleClick(uIItemPane, new Point(31, 14)); )
    ```

4. 添加 `TextArea`设置文本操作的代码：

    ```csharp
    uIGridKeyboardInputEdit.Text = value; }
    ``

## See also

- [Use UI automation to test your code](../test/use-ui-automation-to-test-your-code.md)
- [Create SharePoint solutions](../sharepoint/create-sharepoint-solutions.md)
- [Verify and debug SharePoint code](../sharepoint/verifying-and-debugging-sharepoint-code.md)
- [Build and debug SharePoint solutions](../sharepoint/building-and-debugging-sharepoint-solutions.md)
- [Profile the performance of SharePoint applications](../sharepoint/profiling-the-performance-of-sharepoint-applications.md)
