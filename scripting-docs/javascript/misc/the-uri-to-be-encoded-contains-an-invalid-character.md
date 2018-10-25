---
title: 要进行编码的 URI 包含无效字符 |Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5024
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a3f0fdbb-8d4b-41ae-a396-43dfc9483760
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e93d145ea6b0991123c2a7c80f8acf54a83a264
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49832169"
---
# <a name="the-uri-to-be-encoded-contains-an-invalid-character"></a>要编码的 URI 包含无效字符
尝试将字符串编码为 URI （统一资源标识符），但它包含无效字符。 尽管大多数字符在字符串转换为 Uri 中有效，但某些 Unicode 字符序列是非法的。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   请确保要进行编码的字符串包含有效 Unicode 序列。 完整的 URI 组成一系列组件和分隔符。 在尖括号中的名称表示组件，并":"，"/"，";"和"？"是保留的字符用作分隔符。 常规形式为：  
  
    ```JavaScript  
    <Scheme>:<first>/<second>;<third>?<fourth>  
    ```  
  
## <a name="see-also"></a>请参阅  
 [encodeURI 函数](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeURIComponent 函数](../../javascript/reference/encodeuricomponent-function-javascript.md)