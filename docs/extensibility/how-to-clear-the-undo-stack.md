---
title: 如何： 清除撤消堆栈 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 59f8d57c0ba0e84107cd0d0290b950b335e5f2b0
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639466"
---
# <a name="how-to-clear-the-undo-stack"></a>如何： 清除撤消堆栈
下面的以下过程说明如何清除撤消堆栈。  
  
## <a name="to-clear-the-undo-stack"></a>若要清除撤消堆栈  
  
1.  若要清除撤消堆栈使用[IOleUndoManager::DiscardFrom](http://msdn.microsoft.com/library/windows/desktop/ms693799)方法。 以下是此示例：  
  
    ```  
    HRESULT CCmdWindow::ClearUndoStack()  
    {  
      HRESULT hr = S_OK;  
  
      if (m_pUndoMgr == NULL)  
        {  
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));  
        ASSERT(m_pUndoMgr != NULL, "",;);  
        }  
  
      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));  
  
    Error:  
      return hr;  
    }  
    ```  
  
## <a name="see-also"></a>请参阅  
 [如何： 实现撤消管理](../extensibility/how-to-implement-undo-management.md)