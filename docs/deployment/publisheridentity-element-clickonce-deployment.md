---
title: '&lt;publisherIdentity&gt;元素 （ClickOnce 部署） |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publisherIdentity Element [ClickOnce deployment manifest], introduction
- required element for signed manifests [ClickOnce], publisherIdentity Element
- publisherIdentity Element [ClickOnce deployment manifest], syntax, elements, and attributes
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d1fa91423a5c0ddf6b276095b53ae4461d7057c4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55005522"
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt;元素 （ClickOnce 部署）
包含有关为此部署清单签名的发布者的信息。  
  
## <a name="syntax"></a>语法  
  
```xml  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `publisherIdentity`元素是必需的签名的清单。 下表显示特性的`publisherIdentity`元素支持。  
  
|特性|说明|  
|---------------|-----------------|  
|`name`|必需。 描述发布此应用程序的参与方的标识。|  
|`issuerKeyHash`|必需。 包含证书颁发者的公钥的 sha-1 哈希。|  
  
#### <a name="parameters"></a>参数  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
  
## <a name="subhead"></a>副标题