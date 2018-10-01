---
title: 如何调试访问冲突？ | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 9311d754-0ce9-4145-b147-88b6ca77ba63
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c06121d84c6b573b5f1895fa447535826dad540
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479645"
---
# <a name="how-can-i-debug-an-access-violation"></a>如何调试访问冲突？
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何调试访问冲突？](https://docs.microsoft.com/visualstudio/debugger/how-can-i-debug-an-access-violation-q)。  
  
问题描述  
 我的程序产生了访问冲突。 如何调试它？  
  
## <a name="solution"></a>解决方案  
 如果在取消引用多个指针的代码行上出现访问冲突，则可能很难辨别引起访问冲突的指针。 从 Visual Studio 2015 Update 1 起，异常对话框现对导致访问冲突的指针进行显式命名。  
  
 例如，给定以下代码，应出现访问冲突：  
  
```cpp  
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
  
 如果无法确定为该指针为何导致访问冲突，请对代码进行跟踪以确保正确指出了导致问题的指针。  如果它作为参数传递，请确保正确传递且未意外创建 [浅表副本](http://stackoverflow.com/questions/184710/what-is-the-difference-between-a-deep-copy-and-a-shallow-copy)。 然后验证未由于创建数据断点而在程序中某些位置无意更改了所述指针的值，以确保没有在程序中其他位置对其进行修改。 有关数据断点的详细信息，请参阅 [Using Breakpoints](../debugger/using-breakpoints.md)中的数据断点部分。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码常见问题解答](../debugger/debugging-native-code-faqs.md)



