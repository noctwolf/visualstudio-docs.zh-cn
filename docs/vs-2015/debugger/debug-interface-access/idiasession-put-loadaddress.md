---
title: 'Idiasession:: Put_loadaddress |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e39ac68468113f371c032f2f29b4613fa229a3b7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471348"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiasession:: Put_loadaddress](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-put-loadaddress)。  
  
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



