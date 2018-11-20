---
title: 'Idiasession:: Put_loadaddress |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: daf1e7748a95ae0ad2d7fce3592e0a6948077f45
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51762003"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

此符号存储区中的符号设置相对应的可执行文件的加载地址。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `NewVal`  
 [in]加载可执行文件的地址。  
  
## <a name="remarks"></a>备注  
 使用此方法的值计算符号虚拟地址 (VA) 属性。 除非将此属性设置为非零值，不会计算虚拟地址。  
  
> [!NOTE]
>  当你获得时，必须调用此方法[IDiaSession](../../debugger/debug-interface-access/idiasession.md)对象，并开始使用该对象，如果您需要使用任何虚拟属性上的符号之前。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)



