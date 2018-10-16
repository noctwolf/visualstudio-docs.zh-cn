---
title: SetEnv 任务 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.task.setenv
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), tasks
- SetEnv task (MSBuild (Visual C++))
ms.assetid: fd9e4225-68cb-4608-8b27-468b0218c936
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c15f0be4498c3ff3014c273d31657851c9e65b8
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205658"
---
# <a name="setenv-task"></a>SetEnv 任务
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
设置或删除指定环境变量的值。  
  
## <a name="parameters"></a>参数  
 下表描述了 SetEnv 任务的参数。  
  
|参数|描述|  
|---------------|-----------------|  
|**名称**|必需的 **String** 参数。<br /><br /> 环境变量名。|  
|OutputEnvironmentVariable|可选的 **String** 输出参数。<br /><br /> 包含分配给 Name 参数指定的环境变量的值。|  
|Prefix|必需的 `Boolean` 参数。<br /><br /> 如果为 `true`，则将 Value 参数的值连接到 Name 参数指定的环境变量的值之前，然后向环境变量分配结果。 如果为 `false`，则仅向环境变量分配 Value 参数的值。|  
|**Target**|可选 **String** 参数。<br /><br /> 指定环境变量的存储位置。 指定“`User`”或“`Machine`”。<br /><br /> 有关详细信息，请参阅 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 网站上的“EnvironmentVariableTarget 枚举”。|  
|**值**|可选 **String** 参数。<br /><br /> 分配给 Name 参数指定的环境变量的值。 如果 Value 为空并且该变量存在，则删除该变量。 如果该变量不存在，即使无法执行该操作也不会出现任何错误。<br /><br /> 有关详细信息，请参阅 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 网站上的“Environment::SetEnvironmentVariable 方法”。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [任务参考](../msbuild/msbuild-task-reference.md)



