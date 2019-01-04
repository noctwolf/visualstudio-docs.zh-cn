---
title: 如何：使用 _Analysis_assume 指定其他代码信息
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 17e25ace1da6cad9fcdc129b6c6f517c39c9c103
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53845073"
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>如何：使用 _Analysis_assume 指定其他代码信息
您可以对代码分析工具的提示，它们将帮助分析过程并降低警告 C/c + + 代码。 若要提供的其他信息，请使用以下函数：

 `_Analysis_assume(`  `expr`  `)`

 `expr` -假定为计算结果为 true 的任何表达式。

 代码分析工具假设由表达式表示的条件是在其中该函数将显示，并将保持为 true，直到表达式更改，例如，通过对变量赋值的点，则返回 true。

> [!NOTE]
>  `_Analysis_assume` 不会影响代码优化。 外部代码分析工具，`_Analysis_assume`定义为执行任何操作。

## <a name="example"></a>示例
 下面的代码使用`_Analysis_assume`若要更正代码分析警告[C6388](../code-quality/c6388.md):

```
#include<windows.h>
#include<codeanalysis\sourceannotations.h>

using namespace vc_attributes;

// calls free and sets ch to null
void FreeAndNull(char* ch);

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

void test( )
{
  char *pc = (char*)malloc(5);
  FreeAndNull(pc);
  _Analysis_assume(pc == NULL);
  f(pc);
}
```

## <a name="see-also"></a>请参阅
 [__assume](/cpp/intrinsics/assume)