---
title: '&lt;friendlyName&gt;元素 （Visual Studio 中的 Office 开发）'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <friendlyName> element
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4ff600e911ba97a437f998726b900dfc8c267ae8
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/27/2018
ms.locfileid: "53802454"
---
# <a name="ltfriendlynamegt-element-office-development-in-visual-studio"></a>&lt;friendlyName&gt;元素 （Visual Studio 中的 Office 开发）
  `friendlyName` 命名空间的 `vstov4` 元素存储已安装程序列表中出现的名称。

## <a name="syntax"></a>语法

```xml
<friendlyName>
</friendlyName>
```

## <a name="elements-and-attributes"></a>元素和属性
 `friendlyName` 元素位于 `vstov4` 命名空间中。 值出现在计算机中已安装程序列表中和 Microsoft Office 应用程序的 COM VSTO 外接程序对话框中。

 `friendlyName` 元素没有属性或子元素。

## <a name="vsto-add-in-example"></a>VSTO 外接程序示例

### <a name="description"></a>描述
 下面的代码示例演示使用 `friendlyName` 部署的应用程序级解决方案的 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]元素。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。

### <a name="code"></a>代码

```xml
<vstov4:friendlyName>
  ContosoOutlookAddIn
</vstov4:friendlyName>
```

## <a name="see-also"></a>请参阅

- [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)
- [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce 应用程序清单](../deployment/clickonce-application-manifest.md)