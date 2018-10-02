---
title: 图形状态 |Microsoft Docs
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
- vs.graphics.statewindow
ms.assetid: 97e7757e-c372-4626-8149-99a81367a0e1
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 00b53745cc7a166d32633897c65888f4018f6068
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477548"
---
# <a name="graphics-state"></a>图形状态
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[图形状态](https://docs.microsoft.com/visualstudio/debugger/graphics/graphics-state)。  
  
Visual Studio 图形诊断中的“状态”窗口可帮助你了解当前事件（如绘图调用）时为活动状态的图形状态。  
  
## <a name="understanding-the-state-window"></a>了解“状态”窗口  
 “状态”窗口将影响呈现的状态收集到一起，并以层次结构将其显示在一个位置。 根据你的应用所使用的 Direct3D 版本，状态窗口中显示的信息可能有所不同。  
  
### <a name="state-views"></a>状态视图  
 你可以通过多种不同方式查看状态表：  
  
|视图|描述|  
|----------|-----------------|  
|API 输入状态视图|此视图将以类似于构成状态的 Direct3D 对象的布局显示状态。|  
|逻辑输入状态视图|此视图在逻辑视图中显示状态，该逻辑视图不会映射构成状态的 Direct3D 对象的布局。|  
|固定状态视图|固定状态视图取代了层次结构，以完全限定名形式将固定状态项显示在简单列表中。 通过此视图，你可以在少数行中查看不同状态捆绑包中的多个状态项。|  
  
##### <a name="to-change-the-state-view"></a>若要更改状态视图  
  
-   在“状态”窗口中标题栏下面的左上方，选择对应于你想要使用的状态视图样式的按钮。  
  
    -   **显示 API 输入的状态视图**  
  
    -   **显示逻辑状态视图**  
  
    -   **显示固定状态视图**  
  
> [!IMPORTANT]
>  必须将状态固定**显示 API 输入状态**或**显示逻辑状态**才显示在视图**显示固定状态视图**。  
  
### <a name="state-table-format"></a>状态表格式  
 “状态”窗口显示了多个信息列。  
  
|列|描述|  
|------------|-----------------|  
|name|状态项的名称。 如果此项表示状态的捆绑包，则可以展开该项以显示它。<br /><br /> 在中**API 输入状态视图**并**逻辑状态视图**指出，缩进名称以显示状态之间的层次结构关系。<br /><br /> 在中**固定状态视图**状态，则平面列表中显示完全限定的名称。|  
|“值”|状态项的值。|  
|类型|状态项的类型。|  
  
### <a name="changed-state"></a>已更改的状态  
 图形状态通常以增量方式在后续的绘图调用之间更改，并且状态更改不正确时会导致多种呈现问题。 为了帮助你找到自上次绘图调用以来已更改的状态，已更改状态会标有星号并显示为红色 - 这不仅适用于状态本身，还适用于其父状态项，以便你可以在最高级别轻松发现已更改的状态，然后深入了解详细信息。  
  
### <a name="pinning-state"></a>正在固定状态  
 因为很多应用按顺序（即更改一组已知状态）呈现类似对象，所以有时将更改中的状态固定到适当位置很有用，这样你可以在各个绘图调用间移动时观察状态如何更改。  
  
 如果你已隔离了问题的源（该问题由特定状态中的更改导致），此操作也非常有用。  
  
##### <a name="to-pin-state-in-place"></a>若要将状态固定到适当位置  
  
1.  在“状态”窗口中，找到你感兴趣的状态。 可能需要展开更高级别的状态来查找你感兴趣的详细信息。  
  
2.  将光标置于所感兴趣的状态上。 图钉图标将显示在状态项的左侧。  
  
3.  选择图钉图标以将状态项固定在适当位置。



