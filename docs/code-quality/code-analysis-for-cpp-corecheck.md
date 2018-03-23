---
title: Visual Studio c + + 核心指南检查器引用 |Microsoft 文档
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code analysis, C++ core check
ms.assetid: f1429463-136e-41ed-8a75-a8dbf0b4fd89
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0825ea42ca74b224574299846504dfde7dd6f809
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="c-core-guidelines-checker-reference"></a>C + + 核心准则检查程序参考

本部分列出了 c + + 核心准则检查程序警告。 有关代码分析的信息，请参阅[/analyze （代码分析）](/cpp/build/reference/analyze-code-analysis)和[快速入门： C/c + + 代码分析](../code-quality/quick-start-code-analysis-for-c-cpp.md)。

> [!NOTE]
> 一些警告属于多个组，并且并非所有警告都有一个完整的参考主题。

## <a name="ownerpointer-group"></a>OWNER_POINTER Group

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)返回而不是堆分配的作用域的对象，如果它具有移动构造函数。 请参阅[c + + 核心准则 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)。

[C26403 RESET_OR_DELETE_OWNER](C26403.md)重置或显式删除所有者\<T > 指针 %变量 %。 请参阅[c + + 核心准则 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)。

[C26404 DONT_DELETE_INVALID](C26404.md)不要删除所有者\<T >，可能处于无效状态。 请参阅[c + + 核心准则 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)。

[C26405 DONT_ASSIGN_TO_VALID](C26405.md)不分配到所有者\<T >，可能处于有效状态。 请参阅[c + + 核心准则 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)。

[C26406 DONT_ASSIGN_RAW_TO_OWNER](C26406.md)现在将原始指针分配给所有者\<T >。 请参阅[c + + 核心准则 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)。

[C26407 DONT_HEAP_ALLOCATE_UNNECESSARILY](C26407.md)喜欢范围的对象，因此不堆的分配不必要地。 请参阅[c + + 核心准则 R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)。

[C26429 USE_NOTNULL](C26429.md)从未为 nullness 进行过测试符号 %符号 %，它可以将标记为空白。 请参阅[c + + 核心准则 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)。

[C26430 TEST_ON_ALL_PATHS](C26430.md)符号 %符号 %未测试的所有路径上的 nullness。 请参阅[c + + 核心准则 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)。

[C26431 DONT_TEST_NOTNULL](C26431.md)表达式 %expr%的类型已 gsl::not_null。 不会测试它 nullness。 请参阅[c + + 核心准则 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)。

## <a name="rawpointer-group"></a>RAW_POINTER Group

[C26400 NO_RAW_POINTER_ASSIGNMENT](c26400.md)不分配的分配或函数调用结果的所有者\<T > 的值返回到原始指针; 使用所有者\<T > 改为。 请参阅[c + + 核心准则 I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw)。

[C26401 DONT_DELETE_NON_OWNER](c26401.md)不要删除不是所有者的原始指针\<T >。 请参阅[c + + 核心准则 I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw)。

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)  返回而不是堆分配的作用域的对象，如果它具有移动构造函数。 请参阅[c + + 核心准则 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)。

[C26408 NO_MALLOC_FREE](C26408.md)避免 malloc() 和 free （），应尽量使用删除的新的 nothrow 版本。 请参阅[c + + 核心准则 R.10](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-mallocfree)。

[C26409 NO_NEW_DELETE](C26409.md)避免新的调用和显式删除，请使用 std::make_unique\<T > 改为。 请参阅[c + + 核心准则 R.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-newdelete)。

[C26429 USE_NOTNULL](C26429.md)从未为 nullness 进行过测试符号 %符号 %，它可以将标记为空白。 请参阅[c + + 核心准则 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)。

[C26430 TEST_ON_ALL_PATHS](C26430.md)符号 %符号 %未测试的所有路径上的 nullness。 请参阅[c + + 核心准则 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)。

[C26431 DONT_TEST_NOTNULL](C26431.md)表达式 %expr%的类型已 gsl::not_null。 不会测试它 nullness。 请参阅[c + + 核心准则 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)。

[C26481 NO_POINTER_ARITHMETIC](C26481.md)不要使用指针算法。 请改用跨度。 请参阅[c + + 核心准则 Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)。

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)。
表达式 %expr%： 指针 decay 到任何数组。 请参阅[c + + 核心准则 Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)。

## <a name="uniquepointer-group"></a>UNIQUE_POINTER Group

[C26410 NO_REF_TO_CONST_UNIQUE_PTR](C26410.md)参数 %参数 %是指`const`唯一指针，使用 const T * 或 const T 和相反。 请参阅[c + + 核心准则 R.32](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-uniqueptrparam)。

[C26411 NO_REF_TO_UNIQUE_PTR](C26411.md)参数 %参数 %是唯一的指向指针的引用，并且永远不会重新分配或重置，请使用 T * 或 T （&) 相反。 请参阅[c + + 核心准则 R.33](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-reseat)。

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)移动、 复制、 重新分配，或重置本地智能指针 %符号 %。 请参阅[c + + 核心准则 R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)。

[C26415 SMART_PTR_NOT_NEEDED](C26415.md)智能指针参数 %符号 %仅用于访问包含的指针。 使用 T * 或 T （&) 相反。 请参阅[c + + 核心准则 R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam)。

## <a name="sharedpointer-group"></a>SHARED_POINTER Group

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)移动、 复制、 重新分配，或重置本地智能指针 %符号 %。 请参阅[c + + 核心准则 R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)。

[C26415 SMART_PTR_NOT_NEEDED](C26415.md)智能指针参数 %符号 %仅用于访问包含的指针。 使用 T * 或 T （&) 相反。 请参阅[c + + 核心准则 R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam)。

[C26416 NO_RVALUE_REF_SHARED_PTR](C26416.md)共享指针参数 %符号 %通过右值引用传递。 而是按值传递。 请参阅[c + + 核心准则 R.34](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-owner)。

[C26417 NO_LVALUE_REF_SHARED_PTR](C26417.md)通过引用传递，并且不会重置或重新分配共享指针参数 %符号 %。 使用 T * 或 T （&) 相反。 请参阅[c + + 核心准则 R.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam)。

[C26418 NO_VALUE_OR_CONST_REF_SHARED_PTR](C26418.md)不复制或移动共享指针参数 %符号 %。 使用 T * 或 T （&) 相反。 请参阅[c + + 核心准则 R.36](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-const)。

## <a name="declaration-group"></a>声明组

[C26426 NO_GLOBAL_INIT_CALLS](C26426.md)全局初始值设定项调用非 constexpr 函数 %符号 %。 请参阅[c + + 核心准则 I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects)。

[C26427 NO_GLOBAL_INIT_EXTERNS](C26427.md)全局初始值设定项访问外部对象 %符号 %。 请参阅[c + + 核心准则 I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects)。

[C26444 NO_UNNAMED_RAII_OBJECTS](c26444.md)避免未命名的对象与自定义的构造和析构。 请参阅[ES.84： 不 （尝试） 声明没有名称的本地变量](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)。

## <a name="class-group"></a>类组

[C26432 DEFINE_OR_DELETE_SPECIAL_OPS](C26432.md)如果你定义或删除任何默认操作类型 %符号 %中的，定义或将其全部删除。 请参阅[c + + 核心准则 C.21](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c21-if-you-define-or-delete-any-default-operation-define-or-delete-them-all)。

[C26433 OVERRIDE_EXPLICITLY](c26433.md)函数 %符号 %应使用替代标记。 请参阅[C.128： 虚函数应明确指定一个虚拟的重写时，或最终](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final)。

[C26434 DONT_HIDE_METHODS](C26434.md)函数 %symbol_1 移动 %将隐藏非虚拟函数 %symbol_2%。 请参阅[c + + 核心准则 C.128](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final)。

[C26435 SINGLE_VIRTUAL_SPECIFICATION](c26435.md)函数 %符号 %应指定恰好有一个虚拟、 重写' 或 'final'。 请参阅[C.128： 虚函数应明确指定一个虚拟的重写时，或最终](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)。


[C26436 NEED_VIRTUAL_DTOR](C26436.md)类型与虚函数的 %符号 %需要任一公共虚拟或受保护非虚拟析构函数。 请参阅[c + + 核心准则 C.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c35-a-base-class-destructor-should-be-either-public-and-virtual-or-protected-and-nonvirtual)。


[C26443 NO_EXPLICIT_DTOR_OVERRIDE](c26443.md)重写析构函数不应使用显式的替代或虚拟说明符。 请参阅[C.128： 虚函数应明确指定一个虚拟的重写时，或最终](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)。


## <a name="type-group"></a>类型组

[C26437 DONT_SLICE](C26437.md)不切片。 请参阅[c + + 核心准则 ES.63](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es63-dont-slice)。

## <a name="style-group"></a>样式组

[C26438 NO_GOTO](C26438.md)避免`goto`。 请参阅[c + + 核心准则 ES.76](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es76-avoid-goto)。

## <a name="function-group"></a>函数组

[C26439 SPECIAL_NOEXCEPT](C26439.md)可能不会引发这种函数。 将其声明`noexcept`。 请参阅[c + + 核心准则 F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept)。

[C26440 DECLARE_NOEXCEPT](C26440.md)可以声明函数 %符号 % `noexcept`。 请参阅[c + + 核心准则 F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept)。

[C26447 DONT_THROW_IN_NOEXCEPT](c26447.md)函数声明**noexcept**但调用的函数可能会引发异常。
请参阅[c + + 核心准则： F.6： 如果你的函数可能不会引发，将其声明 noexcept](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept)。

## <a name="concurrency-group"></a>并发组

[C26441 NO_UNNAMED_GUARDS](C26441.md)必须命名为防护对象。 请参阅[c + + 核心准则 cp.44](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cp44-remember-to-name-your-lock_guards-and-unique_locks)。

## <a name="const-group"></a>CONST 组

[C26460 USE_CONST_REFERENCE_ARGUMENTS](c26460.md)函数 %函数 %的引用自变量 %自变量 %可以标记为`const`。 请参阅[c + + 核心准则 con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref)。

[C26461 USE_CONST_POINTER_ARGUMENTS](c26461.md)： 函数 %函数 %的指针自变量 %自变量 %可以标记的指针为`const`。 请参阅[c + + 核心准则 con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref)。

[C26462 USE_CONST_POINTER_FOR_VARIABLE](c26462.md)指向由 %变量 %的值分配一次，可将其标记为一个指针到`const`。 请参阅[c + + 核心准则 con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)。

[C26463 USE_CONST_FOR_ELEMENTS](c26463.md)数组 %数组 %的元素分配一次，标记元素`const`。 请参阅[c + + 核心准则 con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)。

[C26464 USE_CONST_POINTER_FOR_ELEMENTS](c26464.md)指向数组 %数组 %的元素的值只能分配一次，标记元素作为指向`const`。 请参阅[c + + 核心准则 con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)。

[C26496 USE_CONST_FOR_VARIABLE](c26496.md)仅一次分配给变量 %变量 %是，将其标记为`const`。 请参阅[c + + 核心准则 con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)。

[C26497 USE_CONSTEXPR_FOR_FUNCTION](c26497.md)无法标记此函数 %函数 %`constexpr`需要编译时计算的情况。 请参阅[c + + 核心准则 F.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rf-constexpr)。

[C26498 USE_CONSTEXPR_FOR_FUNCTIONCALL](c26498.md)可以使用此函数调用 %函数 %`constexpr`需要编译时计算的情况。 请参阅[c + + 核心准则 con.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-constexpr)。

## <a name="type-group"></a>类型组

[C26465 NO_CONST_CAST_UNNECESSARY](c26465.md)不要使用`const_cast`转换掉`const`。 `const_cast` 不是必需的;constness 或波动性不是通过此转换正在删除。 请参阅[c + + 核心准则 Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-constcast)。

[C26466 NO_STATIC_DOWNCAST_POLYMORPHIC](c26466.md)不要使用`static_cast`向下转换方面。 从多态类型强制转换应使用 dynamic_cast。 请参阅[c + + 核心准则 Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-downcast)。

[C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR](c26471.md)不要使用`reinterpret_cast`。 可以使用强制转换从 void * `static_cast`。 请参阅[c + + 核心准则 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)。

[C26472 NO_CASTS_FOR_ARITHMETIC_CONVERSION](C26472.md)不要使用`static_cast`有关算术转换。 使用大括号初始化、 gsl::narrow_cast 或 gsl::narow。 请参阅[c + + 核心准则 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)。

[C26473 NO_IDENTITY_CAST](C26473.md)不其中的源类型和目标类型是相同的指针类型之间强制转换。 请参阅[c + + 核心准则 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)。

[C26474 NO_IMPLICIT_CAST](C26474.md)不时转换可能是隐式的指针类型之间强制转换。 请参阅[c + + 核心准则 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)。

[C26475 NO_FUNCTION_STYLE_CASTS](C26475.md)不使用函数样式 C 强制转换。 请参阅[c + + 核心准则 ES.49](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es49-if-you-must-use-a-cast-use-a-named-cast)。
 
[C26490 NO_REINTERPRET_CAST](c26490.md)不要使用`reinterpret_cast`。 请参阅[c + + 核心准则 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)。

[C26491 NO_STATIC_DOWNCAST](c26490.md)不要使用`static_cast`向下转换方面。 请参阅[c + + 核心准则 Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)。

[C26492 NO_CONST_CAST](c26492.md)不要使用`const_cast`转换掉`const`。 请参阅[c + + 核心准则 Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)。

[C26493 NO_CSTYLE_CAST](c26493.md)不使用 C 样式强制转换。 请参阅[c + + 核心准则 Type.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)。
 
[C26494 VAR_USE_BEFORE_INIT](c26494.md)变量 %变量 %未初始化。 始终将对象初始化。 请参阅[c + + 核心准则 Type.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)。

[C26495 MEMBER_UNINIT](c26495.md)变量 %变量 %未初始化。 任何时候进行初始化的成员变量。 请参阅[c + + 核心准则 Type.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)。

## <a name="bounds-group"></a>边界组

[C26446 USE_GSL_AT](c26446.md)更愿意使用`gsl::at()`而不是未选中的下标运算符。 请参阅[c + + 核心准则： Bounds.4： 不要使用标准库函数和类型不是边界检查](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)。

[C26481 NO_POINTER_ARITHMETIC](C26481.md)。
不要使用指针算法。 请改用跨度。 请参阅[c + + 核心准则 Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26482 NO_DYNAMIC_ARRAY_INDEXING](c26482.md)仅使用常量表达式的数组中的索引。 请参阅[c + + 核心准则 Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26483 STATIC_INDEX_OUT_OF_RANGE](c26483.md)值 %值 %是超出界限 （0，%绑定的 %） 的变量 %变量 %。 仅索引到使用数组的边界内的常量表达式的数组。 请参阅[c + + 核心准则 Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)表达式 %expr%： 指针 decay 到任何数组。 请参阅[c + + 核心准则 Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

## <a name="gsl-group"></a>GSL Group

[C26445 NO_SPAN_REF](c26445.md)指`gsl::span`或`std::string_view`可能生存期问题的迹象。
请参阅[c + + 核心准则 GSL.view： 视图](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views)

[C26446 USE_GSL_AT](c26446.md)更愿意使用`gsl::at()`而不是未选中的下标运算符。 请参阅[c + + 核心准则： Bounds.4： 不要使用标准库函数和类型不是边界检查](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)。

[C26448 USE_GSL_FINALLY](c26448.md)请考虑使用`gsl::finally`如果最终操作的目标。 请参阅[c + + 核心准则： GSL.util： 实用工具](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-utilities)。

[C26449 NO_SPAN_FROM_TEMPORARY](c26449.md) 
 `gsl::span`或`std::string_view`创建从一个临时将无效时临时将失效。 请参阅[c + + 核心准则： GSL.view： 视图](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views)。


## <a name="deprecated-warnings"></a>不推荐使用的警告

以下警告核心准则检查器中，早期实验规则集的交集但现已弃用，可以安全地忽略。 通过从上面的列表的警告，警告所取代。

- 26412 DEREF_INVALID_POINTER
- 26413 DEREF_NULLPTR
- 26420 ASSIGN_NONOWNER_TO_EXPLICIT_OWNER
- 26421 ASSIGN_VALID_OWNER
- 26422 VALID_OWNER_LEAVING_SCOPE
- 26423 ALLOCATION_NOT_ASSIGNED_TO_OWNER
- 26424 VALID_ALLOCATION_LEAVING_SCOPE
- 26425 ASSIGNING_TO_STATIC
- 26499 NO_LIFETIME_TRACKING

## <a name="see-also"></a>另请参阅
[使用 c + + 核心准则检查器](using-the-cpp-core-guidelines-checkers.md)
