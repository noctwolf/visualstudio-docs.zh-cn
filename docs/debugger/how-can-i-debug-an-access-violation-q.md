---
title: 调试 c + + 访问冲突 |Microsoft Docs
ms.custom: seodec18
ms.date: 05/23/2017
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 9311d754-0ce9-4145-b147-88b6ca77ba63
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: fe15813489fbdc0f3a9506468f56773fb3f35deb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53850370"
---
# <a name="how-can-i-debug-a-c-access-violation"></a>如何调试 c + + 访问冲突？
## <a name="problem-description"></a>问题描述  
 我的程序产生了访问冲突。 如何调试它？  
  
## <a name="solution"></a>解决方案  
 如果在取消引用多个指针的代码行上出现访问冲突，则可能很难辨别引起访问冲突的指针。 从 Visual Studio 2015 Update 1 起，异常对话框现对导致访问冲突的指针进行显式命名。  
  
 例如，给定以下代码，应出现访问冲突：  
  
```C++  
#include <iostream>  
using namespace std;  
  
class ClassB {  
public:  
        ClassC* C;  
        ClassB() {  
                C = new ClassC();  
        }  
     void printHello() {  
                cout << "hello world";  
        }  
};  
  
class ClassA {  
public:  
    ClassB* B;  
      ClassA() {  
                B = nullptr;  
        }  
};  
  
int main() {  
    ClassA* A = new ClassA();  
      A->B->printHello();  
}  
```  
  
 如果在 Visual Studio 2015 Update 1 中运行此代码，你将看到以下异常对话框：  
  
 ![AccessViolationCPlus](../debugger/media/accessviolationcplus.png "AccessViolationCPlus")  
  
 如果无法确定为该指针为何导致访问冲突，请对代码进行跟踪以确保正确指出了导致问题的指针。  如果它作为参数传递，请确保正确传递且未意外创建[浅表副本](http://stackoverflow.com/questions/184710/what-is-the-difference-between-a-deep-copy-and-a-shallow-copy)。 然后验证未由于创建数据断点而在程序中某些位置无意更改了所述指针的值，以确保没有在程序中其他位置对其进行修改。 有关数据断点的详细信息，请参阅 [Using Breakpoints](../debugger/using-breakpoints.md)中的数据断点部分。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)