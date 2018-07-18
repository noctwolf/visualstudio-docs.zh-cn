---
title: JsCreateDataView 函数 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e5150a9b858e09217ee7ac3c1f25efba36615f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24567977"
---
# <a name="jscreatedataview-function"></a>JsCreateDataView 函数
创建 JavaScript `DataView` 对象。  
  
## <a name="syntax"></a>语法  
  
```  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>参数  
 `arrayBuffer`  
 用作存储生成的 `DataView` 对象的现有 `ArrayBuffer` 对象。  
  
 `byteOffset`  
 自 `arrayBuffer` 开始后，生成的 `DataView` 要引用的偏移量（以字节为单位）。  
  
 `byteLength`  
 ArrayBuffer 中生成的 DataView 要引用的字节数。  
  
 `result`  
 新的 DataView 对象。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 需要活动脚本上下文。  
  
 此 API 仅在“边缘”模式下受到支持。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)