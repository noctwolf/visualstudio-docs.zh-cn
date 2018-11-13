---
title: 为表设计器构造筛选字符串 |Microsoft Docs
description: 为表设计器构造筛选字符串
author: ghogen
manager: douge
assetId: a1a10ea1-687a-4ee1-a952-6b24c2fe1a22
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/18/2016
ms.author: ghogen
ms.openlocfilehash: ff8c3dd927e81b9e131242a9a6631a8297046a6e
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001555"
---
# <a name="constructing-filter-strings-for-the-table-designer"></a>为表设计器构造筛选器字符串
## <a name="overview"></a>概述
显示在 Visual Studio 的 Azure 表中筛选数据**表设计器**，构造筛选器字符串和筛选器字段中输入它。 筛选器字符串语法由 WCF 数据服务定义并类似于 SQL WHERE 子句，但发送到表服务通过 HTTP 请求。 **表设计器**处理正确的编码，因此若要筛选所需的属性值，您需要只输入属性名称、 比较运算符、 条件值和 （可选） 一个布尔值筛选器字段中的运算符。 不需要包括 $filter 查询选项，就像您构造 URL 查询通过表[存储服务 REST API 参考](http://go.microsoft.com/fwlink/p/?LinkId=400447)。

WCF 数据服务基于[开放数据协议](http://go.microsoft.com/fwlink/p/?LinkId=214805)(OData)。 有关 filter 系统查询选项的详细信息 (**$filter**)，请参阅[OData URI 约定规范](http://go.microsoft.com/fwlink/p/?LinkId=214806)。

## <a name="comparison-operators"></a>比较运算符
对于所有属性类型支持以下逻辑运算符：

| 逻辑运算符 | 描述 | 示例筛选器字符串 |
| --- | --- | --- |
| eq |等于 |City eq Redmond |
| gt |大于 |价格 gt 20 |
| ge |大于或等于 |价格 ge 10 |
| lt |小于 |价格 lt 20 |
| le |小于或等于 |价格 le 100 |
| ne |不等于 |城市 ne 'London' |
| 和 |And |价格 le 200 和价格 gt 3.5 |
| 或 |Or |价格 le 3.5 或价格 gt 200 |
| not |Not |不 isAvailable |

构造筛选器字符串时，以下规则非常重要：

* 使用逻辑运算符来比较属性和值。 请注意，不能比较属性和动态值;该表达式的一侧必须是常量。
* 筛选器字符串的所有部分都都区分大小写。
* 常量的值必须是相同的数据类型的筛选器的顺序中的属性以返回有效结果。 有关受支持的属性类型的详细信息，请参阅[了解表服务数据模型](http://go.microsoft.com/fwlink/p/?LinkId=400448)。

## <a name="filtering-on-string-properties"></a>针对字符串属性进行筛选
筛选字符串属性时，将字符串常量括在单引号内。

以下示例筛选**PartitionKey**并**RowKey**属性; 其他非键属性还可添加到筛选器字符串：

    PartitionKey eq 'Partition1' and RowKey eq '00001'

虽然不是必需，则可以将每个筛选器表达式括在括号中：

    (PartitionKey eq 'Partition1') and (RowKey eq '00001')

请注意，表服务不支持通配符查询中，它们不支持在表设计器中或者。 但是，你可以执行前缀匹配对所需前缀使用比较运算符。 以下示例返回具有以字母 A 开头的姓氏属性的实体：

    LastName ge 'A' and LastName lt 'B'

## <a name="filtering-on-numeric-properties"></a>针对数值属性进行筛选
若要筛选整数或浮点数，请指定不带引号的数字。

此示例返回其值大于 30 的 Age 属性的所有实体：

    Age gt 30

此示例将返回 AmountDue 属性值小于或等于 100.25 的所有实体：

    AmountDue le 100.25

## <a name="filtering-on-boolean-properties"></a>针对布尔值属性进行筛选
若要筛选布尔值，指定 **，则返回 true**或**false**不带引号。

下面的示例返回所有实体，IsActive 属性设置为 **，则返回 true**:

    IsActive eq true

此外可以编写此筛选器表达式，而无需逻辑运算符。 在以下示例中，表服务还将返回所有实体 IsActive 所在 **，则返回 true**:

    IsActive

若要返回 IsActive 为 false 的所有实体，可以使用 not 运算符：

    not IsActive

## <a name="filtering-on-datetime-properties"></a>针对日期时间属性进行筛选
若要筛选的日期时间值，请指定**datetime**关键字后, 跟用单引号引起来的日期/时间常量。 日期/时间常数必须采用组合的 UTC 格式，如中所述[DateTime 属性值格式](http://go.microsoft.com/fwlink/p/?LinkId=400449)。

下面的示例返回 CustomerSince 属性等于 2008 年 7 月 10 日的实体：

    CustomerSince eq datetime'2008-07-10T00:00:00Z'
