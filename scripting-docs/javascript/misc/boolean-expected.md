---
title: 缺少布尔值 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5010
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 35d71b7f-53fd-44c4-a7c7-b1550c65cfd4
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cb8ec8f7244b98cfa628794b485859dbec611c19
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49868087"
---
# <a name="boolean-expected"></a>缺少布尔值
你尝试调用**Boolean.prototype.toString**或**Boolean.prototype.valueOf**方法以外的类型的对象上`Boolean`。 调用此类型的对象的类型必须是`Boolean`。 例如：

```JavaScript
var o = new Object;
o.f = Boolean.prototype.toString;
o.f();
```

## <a name="to-correct-this-error"></a>更正此错误

- 仅调用**Boolean.prototype.toString**或**Boolean.prototype.valueOf**类型的对象上的方法**布尔值。**

## <a name="see-also"></a>请参阅

- [Boolean 对象](../../javascript/reference/boolean-object-javascript.md)
- [数据类型](../../javascript/data-types-javascript.md)
- [控制程序流](../../javascript/controlling-program-flow-javascript.md)
- [复制、传递和比较数据](../../javascript/advanced/copying-passing-and-comparing-data-javascript.md)