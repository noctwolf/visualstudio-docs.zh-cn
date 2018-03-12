---
title: "使用 Assert 类 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Assert classes
- Assert statements
- unit tests, Assert statements
- unit tests, Assert classes
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 01d41202f49a61a1ae2ba0f926b5c5b563ab351c
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="using-the-assert-classes"></a>使用 Assert 类
使用 UnitTestingFramework 命名空间的 Assert 类来验证特定功能。 单元测试方法会执行开发代码中的方法代码，但只有包含 Assert 语句时，它才会报告代码行为的正确性。  
  
## <a name="kinds-of-asserts"></a>Assert 的类型  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting> 命名空间提供多种类型的 Assert 类：  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>  
  
 在测试方法中，可以调用任意数量的 Assert 类的方法，例如 Assert.AreEqual()。 Assert 类有许多方法可供选择，并且其中有很多方法具有若干重载。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>  
  
 使用 CollectionAssert 类比较对象的集合，并验证一个或多个集合的状态。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>  
  
 使用 StringAssert 类比较字符串。 此类包含大量有用的方法，如 StringAssert.Contains、StringAssert.Matches 和 StringAssert.StartsWith。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>  
  
 测试失败时，将引发 AssertFailedException 异常。 如果测试超时，引发意外的异常，或者包含生成失败结果的 Assert 语句，测试则将失败。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>  
  
 测试生成无结论的结果时，将引发 AssertInconclusiveException。 通常，将 Assert.Inconclusive 语句添加到仍在进行的测试中以指示它尚未准备好运行。  
  
> [!NOTE]
>  替代策略将使用 Ignore 属性标记尚未准备好运行的测试。 但是，这样做的弊端是你无法轻松地对尚待执行的测试的数量生成报表。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>  
  
 如果编写新的 Assert 异常类，让该类从基类 UnitTestAssertException 继承使其可更轻松地将异常识别为断言失败，而不是从测试或生产代码引发的意外异常。  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>  
  
 如果想要让测试方法验证期望由开发代码中的方法引发的异常确实是在该方法中引发的，请使用 ExpectedExceptionAttribute 属性修饰测试方法。  
  
## <a name="see-also"></a>请参阅

<xref:Microsoft.VisualStudio.TestTools.UnitTesting>  
[单元测试代码](../test/unit-test-your-code.md)
