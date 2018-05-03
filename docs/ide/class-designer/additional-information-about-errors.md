---
title: 类设计器错误
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: troubleshooting
f1_keywords:
- vs.classdesigner.CPlusPlusViewInDiagramNoTypeFound
- vs.classdesigner.CPlusPlusNoTypeFound
- vs.classdesigner.CannotShowBaseType
- vs.classdesigner.MatchOrphanTypesAtLoad
- vs.classdesigner.CannotShowType
- vs.classdesigner.AssociationTypeNotFoundError
- vs.classdesigner.ViewInDiagramNoTypesFound
- vs.classdesigner.CannotImplementInterface
- vs.classdesigner.CannotShowImplementedInterface
- vs.classdesigner.ViewInDiagramUnparsableTypeFound
- vs.classdesigner.AssociationTypeNotFound
- vs.classdesigner.CPlusPlusTypeCannotBeAdded
helpviewer_keywords:
- errors, class diagrams
- errors, Class Designer
- error messages, Class Designer
- Class Designer [Visual Studio], errors
- error messages, class diagrams
- class diagrams, errors
ms.assetid: 79d70e70-704c-4255-ab68-c10d6949470e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0af8686af556ca24cdbc9e0a51206f4f0728206
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="additional-information-about-class-designer-errors"></a>有关类设计器错误的附加信息

类设计器不会跟踪源文件的位置，因此修改项目结构或移动项目中的源文件就可能导致类设计器无法继续对类型（尤其是 typedef 的源类型、基类或关联类型）进行跟踪。 可能会收到错误，如“类设计器无法显示此类型”。 如果收到错误，要将修改过的或被重新定位的源代码再次拖到类图中以重新显示。

## <a name="resources"></a>资源

你在以下资源中找到关于其他错误和警告的协助：

- [使用 Visual C++ 代码](working-with-visual-cpp-code.md)包括有关在类图中显示 C++ 的疑难解答信息。
- [Visual Studio 类设计器论坛](http://go.microsoft.com/fwlink/?LinkId=160754)提供一个有关类设计器相关问题的论坛。

## <a name="see-also"></a>请参阅

- [设计和查看类与类型](designing-and-viewing-classes-and-types.md)
