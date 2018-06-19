---
title: JsThreadServiceCallback Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c4b7ea4d0d5eaba17269a1777cdf96b5a2a5cda3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568767"
---
# <a name="jsthreadservicecallback-typedef"></a>JsThreadServiceCallback Typedef
线程服务回调。  
  
## <a name="syntax"></a>语法  
  
```  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### <a name="parameters"></a>参数  
 回调  
 用于后台工作项的回调。  
  
 callbackData  
 要传递给回调的数据自变量。  
  
## <a name="remarks"></a>备注  
 当调用 JsCreateRuntime 时，主机可以指定后台线程服务。 若已指定，则使用此回调将后台工作项传递给该主机。 主机应立即开始执行后台工作项并返回 true，或者返回 false，且运行时将在线程中处理工作项。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)