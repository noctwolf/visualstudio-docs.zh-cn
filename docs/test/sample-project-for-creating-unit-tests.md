---
title: 用于创建单元测试的示例代码
description: 本文提供可以使用 Visual Studio 中的单元测试进行测试的示例代码。
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
helpviewer_keywords:
- unit test sample [Visual Studio]
- unit tests, samples
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93335be347e9c2ae66045bc49f9609d6cb3a929d
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379769"
---
# <a name="sample-code-for-testing"></a>用于测试的示例代码

此示例代码包含一个类 BankAccount 以及可以通过单元测试进行测试的各种方法。

以下演练中使用了该代码：

- [创建并运行托管代码的单元测试](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)。 本演练将引导你完成创建和自定义单元测试、运行它们以及检查测试结果的步骤。
- [使用命令行测试实用工具](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)。 在本演练中，可使用 MSTest.exe 命令行实用工具运行测试和查看结果。

## <a name="sample-code"></a>示例代码

在此示例中唯一的有意错误是，Debit 方法“m_balance += amount”的等号之前应有减号而不是加号。

```csharp
using System;

namespace BankAccountNS
{
    /// <summary>
    /// Bank Account demo class.
    /// </summary>
    public class BankAccount
    {
        private string m_customerName;

        private double m_balance;

        private bool m_frozen = false;

        private BankAccount()
        {
        }

        public BankAccount(string customerName, double balance)
        {
            m_customerName = customerName;
            m_balance = balance;
        }

        public string CustomerName
        {
            get { return m_customerName; }
        }

        public double Balance
        {
            get { return m_balance; }
        }

        public void Debit(double amount)
        {
            if (m_frozen)
            {
                throw new Exception("Account frozen");
            }

            if (amount > m_balance)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            if (amount < 0)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            m_balance += amount; // intentionally incorrect code
        }

        public void Credit(double amount)
        {
            if (m_frozen)
            {
                throw new Exception("Account frozen");
            }

            if (amount < 0)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            m_balance += amount;
        }

        private void FreezeAccount()
        {
            m_frozen = true;
        }

        private void UnfreezeAccount()
        {
            m_frozen = false;
        }

        public static void Main()
        {
            BankAccount ba = new BankAccount("Mr. Bryan Walton", 11.99);

            ba.Credit(5.77);
            ba.Debit(11.22);
            Console.WriteLine("Current balance is ${0}", ba.Balance);
        }
    }
}
```

/* 此处描述的示例公司、组织、产品、域名、电子邮件地址、徽标、人员、地点和事件均属虚构。 无意与任何真实的公司、组织、产品、域名、电子邮件地址、徽标、人物、地点或事件相关联，也不应进行这方面的推断。 \*/

## <a name="create-the-project"></a>创建项目

若要使用此代码，需要先在 Visual Studio 中为其创建一个项目。 按照[演练：创建并运行托管代码的单元测试](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#create-a-project-to-test)中创建该项目的步骤操作。

## <a name="see-also"></a>请参阅

- [演练：创建并运行托管代码的单元测试](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)
- [演练：使用命令行测试实用工具](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
