---
title: "与 VSTU 共享 Unity 日志回叫 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-unity-tools
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: da0a8b98e358060cf11de87d9af2edf7e6b15f58
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="share-the-unity-log-callback-with-vstu"></a>与 VSTU 共享 Unity 日志回调
Visual Studio Tools for Unity 对 Unity 注册了一个日志回调，能够将其控制台流式传输到 Visual Studio。 如果编辑器脚本也对 Unity 注册了一个日志回调，则 VSTU 回调可能会妨碍你的回调。 若要防止这种可能性，则使用 `VisualStudioIntegration.LogCallback` 事件与 VSTU 协作。

## <a name="demonstrates"></a>演示
 如何共享由 Visual Studio Tools for Unity 创建的 Unity 日志回调。

## <a name="example"></a>示例

```csharp
using System;

using UnityEngine;
using UnityEditor;

using SyntaxTree.VisualStudio.Unity.Bridge;

[InitializeOnLoad]
public class LogCallbackHook
{
    static LogCallbackHook()
    {
        VisualStudioIntegration.LogCallback += (string condition, string trace, LogType type) =>
        {
            // place code that implements your log callback here
        };
    }
}
```

## <a name="see-also"></a>请参阅
 [示例：项目文件生成](../cross-platform/customize-project-files-created-by-vstu.md)
