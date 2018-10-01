---
title: '&lt;签名&gt;元素 （ClickOnce 部署） |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
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
- <Signature> element [ClickOnce deployment manifest]
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: b1f829971a1e5a5d62c95c1f81fb75375f7cc74e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481489"
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;签名&gt;元素 （ClickOnce 部署）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[&lt;签名&gt;元素 （ClickOnce 部署）](https://docs.microsoft.com/visualstudio/deployment/signature-element-clickonce-deployment)。  
  
包含对此部署清单进行数字签名所需的信息。  
  
## <a name="syntax"></a>语法  
  
```  
  
      <Signature>   
   XML signature information   
</Signature>  
```  
  
## <a name="remarks"></a>备注  
 使用封装签名的部署清单签名是可选的但建议。 有关签名 XML 文件，请参阅 World Wide Web 联合会建议"Xml-signature Syntax and Processing，"中所述[ http://www.w3.org/TR/xmldsig-core/ ](http://www.w3.org/TR/xmldsig-core/)。  
  
 如果你想要对清单签名，哈希必须提供的所有文件。 具有不哈希处理的文件的清单不能进行签名，因为用户不能验证未经哈希的文件的内容。  
  
## <a name="example"></a>示例  
 下面的代码示例演示`Signature`元素中使用的部署清单中[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]部署。  
  
```  
<Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
  <SignedInfo>  
    <CanonicalizationMethod Algorithm=  
           "http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />  
    <SignatureMethod Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#rsa-sha1" />  
    <Reference URI="">  
      <Transforms>  
        <Transform Algorithm=  
           "http://www.w3.org/2000/09/xmldsig#enveloped-signature" />  
      </Transforms>  
      <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <DigestValue>d2z5AE...</DigestValue>  
    </Reference>  
  </SignedInfo>  
  <SignatureValue>  
4PHj6SaopoLp...  
  </SignatureValue>  
  <KeyInfo>  
    <X509Data>  
      <X509Certificate>  
MIIHnTCCBoWgAwIBAgIKJY9+nwAHAAB...  
      </X509Certificate>  
    </X509Data>  
  </KeyInfo>  
</Signature>  
```  
  
## <a name="see-also"></a>请参阅  
 [ClickOnce 部署清单](../deployment/clickonce-deployment-manifest.md)



