---
title: Excel Communicator 示例接口 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1dbf1090-762c-4824-82dd-2d7c2c6f00b6
caps.latest.revision: 13
ms.author: gewarren
manager: douge
ms.openlocfilehash: a1f544734cd00361162c461cd2b1682204075e10
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476836"
---
# <a name="sample-excel-communicator-interface"></a>示例 Excel Communicator 接口
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[示例 Excel Communicator 接口](https://docs.microsoft.com/visualstudio/test/sample-excel-communicator-interface)。  
  
`IExcelUICommunication` 示例接口在 `ExcelAddIn` 项目的 `ExcelUICommunicator` 对象中使用。  
  
## <a name="iexceluicommunication-interface"></a>IExcelUICommunication 接口  
 此接口定义 `CodedUIExtension`（在编码的 UI 测试进程中运行）和 `ExcelCodedUIAddIn`（在 [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 进程中运行）之间的通信点。  
  
 `ExcelCodedUIAddinHelper` 程序集具有 `ExcelUICommunicator` 类，该类派生自此接口并使用 Excel 对象模型来处理方法。  
  
 某些方法从 Excel 中获取请求的信息，然后创建并返回其中一个信息对象，如 `CellInformation` 对象。  
  
 其他方法使用提供的信息对象，在 Excel 中查找相应的控件，并对控件执行某一进程。 例如，`ScrollIntoView` 方法滚动工作表，以显示指定单元格。  
  
## <a name="codeduiextensibilitysample-and-excelcodeduiaddinhelper-communication"></a>CodedUIExtensibilitySample 和 ExcelCodedUIAddinHelper 通信  
 `ExcelCodedUIAddinHelper` 程序集在 Excel 进程中运行，具有实现 `IExcelUITestCommunication` 接口的 `UICommunicator` 类，并且该类直接从 Excel UI 获取或设置所需的信息。  
  
 `CodedUIExtensibilitySample` 程序集在 Visual Studio 编码的 UI 测试进程中运行。 此程序集具有 `Communicator` 类，此类打开 .NET 远程处理信道，其 `Instance` 属性通过 `IExcelUICommunication` 接口来使用 `ExcelCodedUIAddinHelper` 程序集中的 `UICommunicator` 对象，以便在两个程序集之间来回传递请求和信息对象，例如 `CellInformation` 对象。  
  
## <a name="see-also"></a>请参阅  
 [扩展编码的 UI 测试和操作录制以支持 Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)   
 [用于编码的 UI 测试的 Excel 示例外接程序](../test/sample-excel-add-in-for-coded-ui-testing.md)   
 [用于 Excel 的编码的 UI 测试扩展示例](../test/sample-coded-ui-test-extension-for-excel.md)



