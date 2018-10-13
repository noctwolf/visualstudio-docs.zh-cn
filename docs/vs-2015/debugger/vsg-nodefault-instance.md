---
title: VSG_NODEFAULT_INSTANCE |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5e582c8093b08c6b23b428415edade7db4ac22b6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49178825"
---
# <a name="vsgnodefaultinstance"></a>VSG_NODEFAULT_INSTANCE
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

通过其存在定义的默认实例是否[VsgDbg 类](../debugger/vsgdbg-class.md)类，它提供编程捕获界面 — 提供。  
  
## <a name="syntax"></a>语法  
  
```cpp  
#define VSG_NODEFAULT_INSTANCE  
```  
  
## <a name="value"></a>“值”  
 通过其存在或缺失的预处理器符号决定是否提供 `VsgDbg` 类的默认实例。 如果定义此符号，则不提供 `VsgDbg` 类的默认实例；否则，将在程序运行前提供并初始化默认实例。  
  
 通过具有全局范围的指针 `g_pVsgDbg` 提供编程捕获接口。  
  
```  
VsgDbg *g_pVsgDbg;  
```  
  
## <a name="remarks"></a>备注  
 默认实例通常足够，但要在 DLL 外部创建 D3D 设备后使用 DLL 内部的编程捕获接口，您必须创建并管理自己的 `VsgDbg` 类的实例。 如果您正通过此方式管理自己的编程捕获 API 的接口，请通过定义 `VSG_NODEFAULT_INSTANCE` 禁用默认实例来避免开销。  
  
 如果未禁用默认实例，则它将在程序运行前自动进行初始化并在程序终止时自动销毁。 您不必显式初始化或取消初始化此实例。  
  
 若要禁用默认实例，必须定义`VSG_NODEFAULT_INSTANCE`包含之前`vsgcapture.h`在程序中。  
  
## <a name="example"></a>示例  
 此示例说明如何禁用默认实例：  
  
```  
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h  
#define VSG_NODEFAULT_INSTANCE  
  
#include <vsgcapture.h>  
```



