---
title: '&lt;publisherIdentity&gt;元素 （ClickOnce 部署） |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 1d25b9ff6c4d8a3eb43d18d5c9849ba7199ffe79
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49226936"
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt;元素 （ClickOnce 部署）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

包含有关为此部署清单签名的发布者的信息。  
  
## <a name="syntax"></a>语法  
  
```  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `publisherIdentity`元素是必需的签名的清单。 下表显示特性的`publisherIdentity`元素支持。  
  
|特性|描述|  
|---------------|-----------------|  
|`name`|必须的。 描述发布此应用程序的参与方的标识。|  
|`issuerKeyHash`|必须的。 包含证书颁发者的公钥的 sha-1 哈希。|  
  
#### <a name="parameters"></a>参数  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
  
## <a name="subhead"></a>副标题



