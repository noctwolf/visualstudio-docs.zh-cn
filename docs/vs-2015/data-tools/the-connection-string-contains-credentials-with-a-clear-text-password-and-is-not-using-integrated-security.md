---
title: 连接字符串包含凭据具有明文密码并且未使用集成的安全性 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f1ec13cab1b8c41225cb1934740b8dd3e7f59ac0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49230862"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>连接字符串包含的凭据具有明文密码并且未使用集成安全性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
是否要将此敏感信息随连接字符串一起保存到当前 DBML 文件和应用程序配置文件中?  单击“否”可在保存连接字符串时不保存敏感信息。  
  
 在使用包含敏感信息（连接字符串中包含的密码）的数据连接时，可以选择将敏感信息随连接字符串一起保存到项目 DBML 文件和应用程序配置文件中，或者选择不保存敏感信息。  
  
> [!WARNING]
>  显式设置**连接**属性**应用程序设置**属性设置为**False**将密码添加到 DBML 文件。  
  
### <a name="to-save-the-connection-string-with-the-sensitive-information-in-the-projects-application-settings"></a>将敏感信息随连接字符串一起保存在项目的应用程序设置中  
  
-   单击 **“是”**。  
  
     连接字符串将存储为应用程序设置。 连接字符串以纯文本形式包含敏感信息。 DBML 文件不包含敏感信息。  
  
### <a name="to-save-the-connection-string-without-the-sensitive-information-in-the-projects-application-settings"></a>不将敏感信息随连接字符串一起保存在项目的应用程序设置中  
  
-   单击“否” 。  
  
     连接字符串将存储为应用程序设置，但不包含密码。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)

