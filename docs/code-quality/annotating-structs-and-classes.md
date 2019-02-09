---
title: 批注结构和类
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
- _Field_z_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: e37d1ad27fab77e5aff1064ecc83e67ee7cc739d
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55935051"
---
# <a name="annotating-structs-and-classes"></a>批注结构和类
你可以通过使用类似于固定条件注释批注结构和类成员，它们都假定为满足的任何函数调用或进入/退出函数涉及封闭结构作为参数或结果值。

## <a name="struct-and-class-annotations"></a>结构和类批注

-   `_Field_range_(low, high)`

     该字段是从 （含） 范围内`low`到`high`。  等效于`_Satisfies_(_Curr_ >= low && _Curr_ <= high)`通过使用适当的前置或后置条件应用于带批注的对象。

-   `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`

     具有可写大小以元素 （或字节数） 为指定的字段`size`。

-   `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`

     具有可写大小以元素 （或字节数） 为指定的字段`size`，和`count`这些元素 （字节） 的可读。

-   `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`

     具有可读和可写大小元素 （或字节数） 为指定的字段`size`。

-   `_Field_z_`

     一个字段，具有一个以 null 结尾的字符串。

-   `_Struct_size_bytes_(size)`

     适用于结构或类声明。  指示该类型的有效对象，可能与指定的字节数会大于声明的类型， `size`。  例如：

    ```cpp

    typedef _Struct_size_bytes_(nSize)
    struct MyStruct {
        size_t nSize;
        ...
    };

    ```

     以字节为单位的参数的缓冲区大小`pM`类型的`MyStruct *`然后将其视为：

    ```cpp
    min(pM->nSize, sizeof(MyStruct))
    ```

## <a name="see-also"></a>请参阅

- [使用 SAL 批注以减少 C/C++ 代码缺陷](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [了解 SAL](../code-quality/understanding-sal.md)
- [对函数参数和返回值进行批注](../code-quality/annotating-function-parameters-and-return-values.md)
- [对函数行为进行批注](../code-quality/annotating-function-behavior.md)
- [对锁定行为进行批注](../code-quality/annotating-locking-behavior.md)
- [指定何时以及在何处应用批注](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [内部函数](../code-quality/intrinsic-functions.md)
- [最佳做法和示例](../code-quality/best-practices-and-examples-sal.md)