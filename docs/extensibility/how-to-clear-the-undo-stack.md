---
title: "如何： 清除撤消堆栈 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e2592ad8bbec0ddf87731d25f5c46c714a3336d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-clear-the-undo-stack"></a>如何： 清除撤消堆栈
下面的以下过程说明如何清除撤消堆栈。  
  
### <a name="to-clear-the-undo-stack"></a>若要清除撤消堆栈  
  
1.  若要清除撤消堆栈使用[IOleUndoManager::DiscardFrom](http://msdn.microsoft.com/library/windows/desktop/ms693799)方法。 下面是此示例：  
  
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