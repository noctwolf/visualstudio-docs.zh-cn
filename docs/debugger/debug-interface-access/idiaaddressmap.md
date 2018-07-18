---
title: IDiaAddressMap |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap interface
ms.assetid: e6467529-508c-4328-85d7-89444ae4d1c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb1593f59125c4b6325bfd97015485cc2a4d85f6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31468965"
---
# <a name="idiaaddressmap"></a>IDiaAddressMap
提供控制 DIA SDK 如何计算调试对象的虚拟和相对虚拟地址。  
  
## <a name="syntax"></a>语法  
  
```  
IDiaAddressMap : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDiaAddressMap`。  
  
|方法|描述|  
|------------|-----------------|  
|[IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)|指示是否已为特定的会话建立地址映射。|  
|[IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)|指定是否应使用地址映射将符号地址转换。|  
|[IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)|指示是否启用的计算和的相对虚拟地址的使用。|  
|[IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)|允许客户端启用或禁用相对虚拟地址的计算。|  
|[IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)|检索当前的图像对齐方式。|  
|[IDiaAddressMap::put_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)|设置的图像对齐方式。|  
|[IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)|设置图像标头，以便相对虚拟地址的转换。|  
|[IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)|提供的地址映射，以支持图像布局翻译。|  
  
## <a name="remarks"></a>备注  
 此接口由提供的控件封装在你提供的数据的两个集： 映像标头并解决地图。 大多数客户端使用[idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)方法以查找正确的调试信息的映像和方法可以通常发现的所有必要的标头和地图数据本身。 但是，某些客户端实现专用的处理和搜索数据。 此类客户端使用的方法`IDiaAddressMap`接口 DIA SDK 提供搜索结果。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口是可从 DIA 会话对象。 客户端调用`QueryInterface`DIA 会话对象接口上，通常的方法[IDiaSession](../../debugger/debug-interface-access/idiasession.md)来检索`IDiaAddressMap`接口。  
  
## <a name="requirements"></a>要求  
 标头： Dia2.h  
  
 库： diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>请参阅  
 [接口 （调试接口访问 SDK）](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)