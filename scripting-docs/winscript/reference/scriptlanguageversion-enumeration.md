---
title: SCRIPTLANGUAGEVERSION 枚举 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 58aa904a-e3ed-41c6-82d6-e91c8279a792
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 374025b7564c058ae89064b6a27384c9075a30f9
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54350097"
---
# <a name="scriptlanguageversion-enumeration"></a>SCRIPTLANGUAGEVERSION 枚举
指定可能的脚本版本。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum tagSCRIPTLANGUAGEVERSION{    SCRIPTLANGUAGEVERSION_DEFAULT = 0,    SCRIPTLANGUAGEVERSION_5_7  = 1,    SCRIPTLANGUAGEVERSION_5_8  = 2,    SCRIPTLANGUAGEVERSION_MAX  = 255} SCRIPTLANGUAGEVERSION ;  
```  
  
## <a name="enumeration-values"></a>枚举值  
  
|||  
|-|-|  
|SCRIPTLANGUAGEVERSION_DEFAULT|默认版本。 整数值为 0。|  
|SCRIPTLANGUAGEVERSION_5_7|Windows 脚本编写版本 5.7。 整数值为 1。|  
|SCRIPTLANGUAGEVERSION_5_8|Windows 脚本编写版本 5.8。 整数值为 2。|  
|SCRIPTLANGUAGEVERSION_MAX|最高版本。 整数值为 255。|  
  
## <a name="see-also"></a>请参阅  
 [活动脚本常量、枚举和错误代码](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)