---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 43327901b2233b9b2818296f9269975d8524438b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541543"
---
反序列化不受信任的数据时，不安全反序列化程序是易受攻击。 攻击者可以修改以包括具有恶意副作用的意外的类型的序列化的数据。 针对不安全的反序列化程序的攻击可能，例如，基础操作系统上执行命令、 通过网络进行通信或删除文件。