---
title: IPropertyProxyEESide::InPlaceUpdateObject |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IPropertyProxyEESide::InPlaceUpdateObject
helpviewer_keywords:
- IPropertyProxyEESide::InPlaceUpdateObject
ms.assetid: abf89411-1853-4f23-b244-d5e0afa197b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bf62b75fb421cdfb6ad323fbdd12958f93991254
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31124896"
---
# <a name="ipropertyproxyeesideinplaceupdateobject"></a>IPropertyProxyEESide::InPlaceUpdateObject
使用给定的数据对象中更新对象的数据，并返回一个表示对象的新数据的新数据对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT InPlaceUpdateObject(  
   [in] IEEDataStorage*   dataIn,  
   [out] IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int InPlaceUpdateObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dataIn`  
 [in][IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)对象，其中包含新的数据。  
  
 `dataOut`  
 [out]返回一个新`IEEDataStorage`对象，其中包含被替换的数据。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法实际更新对象的数据。 在返回的数据[IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)对象不需要中传入的数据相同`IEEDataStorage`对象，但返回的对象必须反映该属性的当前值。  
  
 传入的数据对象通常是不由 EE 实现。 但是，此方法返回的对象始终由 EE，这样就 EE 实现`IEEDataStorage`上任何类所需的接口。  
  
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)方法创建传入的数据对象的基础的数据对象，但不会影响该属性的原始数据。  
  
## <a name="see-also"></a>另请参阅  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)