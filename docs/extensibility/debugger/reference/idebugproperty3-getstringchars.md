---
title: IDebugProperty3::GetStringChars |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::GetStringChars
helpviewer_keywords:
- IDebugProperty3::GetStringChars
ms.assetid: 832c37f3-85cb-4227-8ab2-f27a80eafe90
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a0597d67e55cb458648b757ca0e222aee7b7a073
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53927228"
---
# <a name="idebugproperty3getstringchars"></a>IDebugProperty3::GetStringChars
检索与此属性关联的字符串并将其存储在用户提供的缓冲区。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetStringChars(  
   ULONG  buflen,  
   WCHAR* rgString,  
   ULONG* pceltFetched  
);  
```  
  
```csharp  
int GetStringChars(  
   uint       buflen,   
   out string rgString,   
   out uint   pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `buflen`  
 [in]用户提供缓冲区可容纳最大字符数。  
  
 `rgString`  
 [out]返回的字符串。  
  
 [仅 c + +]，`rgString`指向该缓冲区用于接收字符串的 Unicode 字符的指针。 此缓冲区必须至少为`buflen`中大小的字符 （而非字节）。  
  
 `pceltFetched`  
 [out]其中返回的实际存储在缓冲区中的字符数。 (可以是`NULL`c + + 中。)  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。  
  
## <a name="remarks"></a>备注  
 在 c + +，必须格外小心以确保缓冲区至少`buflen`Unicode 字符。 请注意，Unicode 字符 2 个字节长。  
  
> [!NOTE]
>  在 c + +，则返回的字符串不包括终止 null 字符。 如果给定，`pceltFetched`将在字符串中指定的字符数。  
  
## <a name="example"></a>示例  
 
```cpp  
CStringW RetrievePropertyString(IDebugProperty2 *pPropInfo)  
{  
    CStringW returnString = L"";  
    CComQIPtr<IDebugProperty3> pProp3 = pPropInfo->pProperty;  
    If (pProp3 != NULL) {  
        ULONG dwStrLen = 0;  
        HRESULT hr;  
        hr = pProp3->GetStringCharLength(&dwStrLen);  
        if (SUCCEEDED(hr) && dwStrLen > 0) {  
            ULONG dwRead;  
            CStrBufW buf(returnString,dwStrLen,CStrBuf::SET_LENGTH);  
            hr = pProp3->GetStringChars(dwStrLen,  
                                        reinterpret_cast<WCHAR*>(static_cast<CStringW::PXSTR>(buf)),  
                                        &dwRead);  
        }  
    }  
    return(returnString);
}
```    
  
## <a name="see-also"></a>请参阅  
 [GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)