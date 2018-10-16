---
title: 降噪百分比 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.filter
helpviewer_keywords:
- Concurrency Visualizer, Noise Reduction Percentage
ms.assetid: 1c10cd4c-2fdd-48c9-b562-a334b3b2df6c
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82aca1dce25fab3ab344f4192e1c2e13ede8276a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49254483"
---
# <a name="noise-reduction-percentage"></a>降噪百分比
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

默认情况下，降噪百分比设置的值为 2。 调用树中只显示非独占时间百分比大于或等于此设置的项。 通过更改此设置，可以控制在调用树中显示的项数。 例如，如果将此值更改为 10，将只显示非独占时间百分比大于或等于 10% 的调用树项。 通过增大此设置的值，可以关注对进程性能影响较大的项。



