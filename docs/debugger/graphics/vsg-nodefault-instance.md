---
title: VSG_NODEFAULT_INSTANCE |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4655b6105a940b7f2c742ba8bcd0812d0be5ab95
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433176"
---
# <a name="vsgnodefaultinstance"></a>VSG_NODEFAULT_INSTANCE
通过其存在定义的默认实例是否[VsgDbg 类](vsgdbg-class.md)类，它提供编程捕获界面 — 提供。  
  
## <a name="syntax"></a>语法  
  
```C++  
#define VSG_NODEFAULT_INSTANCE  
```  
  
## <a name="value"></a>“值”  
 通过其存在或缺失的预处理器符号决定是否提供 `VsgDbg` 类的默认实例。 如果定义此符号，则不提供 `VsgDbg` 类的默认实例；否则，将在程序运行前提供并初始化默认实例。  
  
 通过具有全局范围的指针 `g_pVsgDbg` 提供编程捕获接口。  
  
```cpp
VsgDbg *g_pVsgDbg;  
```  
  
## <a name="remarks"></a>备注  
 默认实例通常足够，但要在 DLL 外部创建 D3D 设备后使用 DLL 内部的编程捕获接口，您必须创建并管理自己的 `VsgDbg` 类的实例。 如果您正通过此方式管理自己的编程捕获 API 的接口，请通过定义 `VSG_NODEFAULT_INSTANCE` 禁用默认实例来避免开销。  
  
 如果未禁用默认实例，则它将在程序运行前自动进行初始化并在程序终止时自动销毁。 您不必显式初始化或取消初始化此实例。  
  
 若要禁用默认实例，必须定义`VSG_NODEFAULT_INSTANCE`包含之前`vsgcapture.h`在程序中。  
  
## <a name="example"></a>示例  
 此示例说明如何禁用默认实例：  
  
```cpp
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h  
#define VSG_NODEFAULT_INSTANCE  
  
#include <vsgcapture.h>  
```
