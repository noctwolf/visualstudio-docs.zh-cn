---
title: "&lt;publisherIdentity&gt;元素 （ClickOnce 部署） |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publisherIdentity Element [ClickOnce deployment manifest], introduction
- required element for signed manifests [ClickOnce], publisherIdentity Element
- publisherIdentity Element [ClickOnce deployment manifest], syntax, elements, and attributes
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 527ab7ae43790f7e824ead33fb601f0f8dee2bf0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt;元素 （ClickOnce 部署）
包含有关为此部署清单签名的发布者的信息。  
  
## <a name="syntax"></a>语法  
  
```  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `publisherIdentity`元素是必需的签名的清单。 下表显示的特性`publisherIdentity`元素支持。  
  
|特性|描述|  
|---------------|-----------------|  
|`name`|必须的。 描述此应用程序发布一方的标识。|  
|`issuerKeyHash`|必须的。 包含证书颁发者的公钥的 sha-1 哈希。|  
  
#### <a name="parameters"></a>参数  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>惠?  
  
## <a name="subhead"></a>副标题