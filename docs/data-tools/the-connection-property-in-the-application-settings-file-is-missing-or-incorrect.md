---
title: 应用程序设置文件中的连接属性缺失或不正确
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 77724510-ff59-4d43-b933-a0434e1ac597
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: d125c5e12320f0c2a17e12c53ca62764f4dfe79f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55070808"
---
# <a name="the-connection-property-in-the-application-settings-file-is-missing-or-incorrect"></a>应用程序设置文件中的连接属性缺失或不正确

应用程序设置文件中缺少连接属性或连接属性不正确。 已使用 .dbml 文件中的连接字符串来替代它。

.dbml 文件包含对应用程序设置文件中某连接字符串的引用，但无法找到该连接字符串。 此消息是通知性消息；单击“确定”后将创建该连接字符串设置。

若要对此消息做出响应，请选择**确定**。 .dbml 文件中包含的连接信息将添加到应用程序设置中。

## <a name="see-also"></a>请参阅

- [O-R 设计器消息](../data-tools/o-r-designer-messages.md)
- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)