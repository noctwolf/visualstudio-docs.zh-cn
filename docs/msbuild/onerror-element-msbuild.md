---
title: OnError 元素 (MSBuild) | Microsoft Docs
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#OnError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- OnError Element [MSBuild]
- <OnError Element [MSBuild]
ms.assetid: 765767d3-ecb7-4cd9-ba1e-d9468964dddc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e5a7ecc4c91dcb39d090c00b7b2ed37bd6bb906c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55011892"
---
# <a name="onerror-element-msbuild"></a>OnError 元素 (MSBuild)
对于某失败的任务，如果 `ContinueOnError` 属性为 `false`，则会出现一个或多个要执行的目标。  

 \<Project>  
 \<Target>  
 \<OnError>  

## <a name="syntax"></a>语法  

```xml  
<OnError ExecuteTargets="TargetName"  
    Condition="'String A'=='String B'" />  
```  

## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  

### <a name="attributes"></a>特性  

|特性|说明|  
|---------------|-----------------|  
|`Condition`|可选特性。<br /><br /> 要计算的条件。 有关详细信息，请参阅[条件](../msbuild/msbuild-conditions.md)。|  
|`ExecuteTargets`|必需的特性。<br /><br /> 任务失败时要执行的目标。 用分号分隔多个目标。 以指定顺序执行多个目标。|  

### <a name="child-elements"></a>子元素  
 无。  

### <a name="parent-elements"></a>父元素  

| 元素 | 说明 |
| - | - |
| [Target](../msbuild/target-element-msbuild.md) | [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 任务的容器元素。 |

## <a name="remarks"></a>备注  
 如果其中一个 `Target` 元素的任务失败并将 `ContinueOnError` 属性设置为 `ErrorAndStop`（或 `false`），则 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 执行 `OnError` 元素。 任务失败时，执行在 `ExecuteTargets` 属性中指定的目标。 如果目标中存在多个 `OnError` 元素，则在任务失败时将按顺序执行 `OnError` 元素。  

 有关 `ContinueOnError` 属性的详细信息，请参阅 [Task 元素 (MSBuild)](../msbuild/task-element-msbuild.md)。 有关目标的信息，请参阅[目标](../msbuild/msbuild-targets.md)。  

## <a name="example"></a>示例  
 以下代码执行 `TaskOne` 和 `TaskTwo` 任务。 如果 `TaskOne` 失败，[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 计算 `OnError` 元素并执行 `OtherTarget` 目标。  

```xml  
<Target Name="ThisTarget">  
    <TaskOne ContinueOnError="ErrorAndStop">  
    </TaskOne>  
    <TaskTwo>  
    </TaskTwo>  
    <OnError ExecuteTargets="OtherTarget" />  
</Target>  
```  

## <a name="see-also"></a>请参阅  
 [项目文件架构参考](../msbuild/msbuild-project-file-schema-reference.md)   
 [目标](../msbuild/msbuild-targets.md)
