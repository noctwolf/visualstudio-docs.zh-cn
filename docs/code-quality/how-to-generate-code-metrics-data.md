---
title: 从 IDE 或命令行生成代码度量值
ms.date: 11/02/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- code metrics data
- code metrics results
- code metrics [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91e32cdae7310a99021946315279736bddb094a8
ms.sourcegitcommit: 0f7411c1a47d996907a028e920b73b53c2098c9f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2019
ms.locfileid: "55690133"
---
# <a name="how-to-generate-code-metrics-data"></a>如何：生成代码度量数据

你可以生成一个或多个项目或整个解决方案的代码度量值结果。 代码度量值可在 Visual Studio 交互式开发环境 (IDE)，以及为C#和 Visual Basic 项目，在命令行。

此外，您可以安装[NuGet 包](https://dotnet.myget.org/feed/roslyn-analyzers/package/nuget/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.2-beta2-63202-01)包括四个代码度量值[分析器](roslyn-analyzers-overview.md)规则：CA1501、 CA1502、 CA1505 和 CA1506。 默认情况下，将禁用这些规则，但也可以启用它们从**解决方案资源管理器**中或在[规则集](using-rule-sets-to-group-code-analysis-rules.md)文件。

## <a name="visual-studio-ide-code-metrics"></a>Visual Studio IDE 代码度量值

### <a name="generate-code-metrics-results-for-an-entire-solution"></a>生成整个解决方案的代码度量结果

可以在任何通过以下方式生成整个解决方案的代码度量结果：

- 在菜单栏上，选择**分析** > **计算代码度量值** > **针对解决方案**。

- 在中**解决方案资源管理器**，右键单击该解决方案，然后选择**计算代码度量值**。

- 在中**代码度量结果**窗口中，选择**为解决方案计算代码度量值**按钮。

此时将生成结果和**代码度量结果**显示窗口。 若要查看结果详细信息，请展开的树中**层次结构**列。

### <a name="generate-code-metrics-results-for-one-or-more-projects"></a>生成一个或多个项目的代码度量结果

1. 在中**解决方案资源管理器**，选择一个或多个项目。

1. 在菜单栏上，选择**分析** > **计算代码度量值** > **为所选项目**。

此时将生成结果和**代码度量结果**显示窗口。 若要查看结果详细信息，请展开的树中**层次结构**。

## <a name="command-line-code-metrics"></a>命令行代码度量值

可以从命令行生成代码度量数据C#和.NET Framework、.NET Core 和.NET Standard 应用的 Visual Basic 项目。 若要从命令行运行代码度量值，请安装[Microsoft.CodeAnalysis.Metrics NuGet 包](#microsoftcodeanalysismetrics-nuget-package)或生成[Metrics.exe](#metricsexe)可执行您自己。

### <a name="microsoftcodeanalysismetrics-nuget-package"></a>Microsoft.CodeAnalysis.Metrics NuGet 包

若要从命令行生成代码度量数据的最简单方法是通过安装[Microsoft.CodeAnalysis.Metrics](https://www.nuget.org/packages/Microsoft.CodeAnalysis.Metrics/) NuGet 包。 安装此包后，运行`msbuild /t:Metrics`从包含项目文件的目录。 例如：

```shell
C:\source\repos\ClassLibrary3\ClassLibrary3>msbuild /t:Metrics
Microsoft (R) Build Engine version 16.0.360-preview+g9781d96883 for .NET Framework
Copyright (C) Microsoft Corporation. All rights reserved.

Build started 1/22/2019 4:29:57 PM.
Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" on node 1 (Metrics target(s))
.
Metrics:
  C:\source\repos\ClassLibrary3\packages\Microsoft.CodeMetrics.2.6.4-ci\build\\..\Metrics\Metrics.exe /project:C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj /out:ClassLibrary3.Metrics.xml
  Loading ClassLibrary3.csproj...
  Computing code metrics for ClassLibrary3.csproj...
  Writing output to 'ClassLibrary3.Metrics.xml'...
  Completed Successfully.
Done Building Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" (Metrics target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)
```

可以通过指定覆盖输出文件的名称`/p:MetricsOutputFile=<filename>`。 此外可以获取[旧式](#previous-versions)通过指定的代码度量值数据`/p:LEGACY_CODE_METRICS_MODE=true`。 例如：

```shell
C:\source\repos\ClassLibrary3\ClassLibrary3>msbuild /t:Metrics /p:LEGACY_CODE_METRICS_MODE=true /p:MetricsOutputFile="Legacy.xml"
Microsoft (R) Build Engine version 16.0.360-preview+g9781d96883 for .NET Framework
Copyright (C) Microsoft Corporation. All rights reserved.

Build started 1/22/2019 4:31:00 PM.
The "MetricsOutputFile" property is a global property, and cannot be modified.
Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" on node 1 (Metrics target(s))
.
Metrics:
  C:\source\repos\ClassLibrary3\packages\Microsoft.CodeMetrics.2.6.4-ci\build\\..\Metrics.Legacy\Metrics.Legacy.exe /project:C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj /out:Legacy.xml
  Loading ClassLibrary3.csproj...
  Computing code metrics for ClassLibrary3.csproj...
  Writing output to 'Legacy.xml'...
  Completed Successfully.
Done Building Project "C:\source\repos\ClassLibrary3\ClassLibrary3\ClassLibrary3.csproj" (Metrics target(s)).

Build succeeded.
    0 Warning(s)
    0 Error(s)
```

### <a name="code-metrics-output"></a>代码度量值输出

生成的 XML 输出会采用以下格式：

```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeMetricsReport Version="1.0">
  <Targets>
    <Target Name="ConsoleApp20.csproj">
      <Assembly Name="ConsoleApp20, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null">
        <Metrics>
          <Metric Name="MaintainabilityIndex" Value="100" />
          <Metric Name="CyclomaticComplexity" Value="1" />
          <Metric Name="ClassCoupling" Value="1" />
          <Metric Name="DepthOfInheritance" Value="1" />
          <Metric Name="LinesOfCode" Value="11" />
        </Metrics>
        <Namespaces>
          <Namespace Name="ConsoleApp20">
            <Metrics>
              <Metric Name="MaintainabilityIndex" Value="100" />
              <Metric Name="CyclomaticComplexity" Value="1" />
              <Metric Name="ClassCoupling" Value="1" />
              <Metric Name="DepthOfInheritance" Value="1" />
              <Metric Name="LinesOfCode" Value="11" />
            </Metrics>
            <Types>
              <NamedType Name="Program">
                <Metrics>
                  <Metric Name="MaintainabilityIndex" Value="100" />
                  <Metric Name="CyclomaticComplexity" Value="1" />
                  <Metric Name="ClassCoupling" Value="1" />
                  <Metric Name="DepthOfInheritance" Value="1" />
                  <Metric Name="LinesOfCode" Value="7" />
                </Metrics>
                <Members>
                  <Method Name="void Program.Main(string[] args)" File="C:\source\repos\ConsoleApp20\ConsoleApp20\Program.cs" Line="7">
                    <Metrics>
                      <Metric Name="MaintainabilityIndex" Value="100" />
                      <Metric Name="CyclomaticComplexity" Value="1" />
                      <Metric Name="ClassCoupling" Value="1" />
                      <Metric Name="LinesOfCode" Value="4" />
                    </Metrics>
                  </Method>
                </Members>
              </NamedType>
            </Types>
          </Namespace>
        </Namespaces>
      </Assembly>
    </Target>
  </Targets>
</CodeMetricsReport>
```

### <a name="metricsexe"></a>Metrics.exe

如果不想要安装 NuGet 包，可以生成并使用*Metrics.exe*直接的可执行文件。 若要生成*Metrics.exe*可执行文件：

1. 克隆[dotnet/roslyn 的分析器](https://github.com/dotnet/roslyn-analyzers)存储库。
2. 以管理员身份打开 Visual Studio 开发人员命令提示。
3. 根目录**roslyn 分析器**存储库中，执行以下命令： `Restore.cmd`
4. 将目录更改为*src\Tools*。
5. 执行以下命令以生成**Metrics.csproj**项目：

   ```shell
   msbuild /m /v:m /p:Configuration=Release Metrics.csproj
   ```

   名为可执行文件*Metrics.exe*中生成*artifacts\bin*目录存储库根目录下。

#### <a name="metricsexe-usage"></a>Metrics.exe 使用情况

若要运行*Metrics.exe*、 提供一个项目或解决方案和一个输出 XML 文件作为自变量。 例如：

```shell
C:\>Metrics.exe /project:ConsoleApp20.csproj /out:report.xml
Loading ConsoleApp20.csproj...
Computing code metrics for ConsoleApp20.csproj...
Writing output to 'report.xml'...
Completed Successfully.
```

#### <a name="legacy-mode"></a>旧模式

您可以选择生成*Metrics.exe*中*旧模式*。 旧模式版本的工具生成更接近于什么的指标值[较旧版本的工具生成](#previous-versions)。 此外，在旧模式下， *Metrics.exe*为一组相同的方法类型版本的工具生成代码度量值的上一生成代码度量值。 例如，它不会生成代码度量数据字段和属性的初始值设定项。 对于向后兼容性，或者你对代码签入的入口基于代码度量值的数字，传统模式很有用。 要生成的命令*Metrics.exe*在旧模式是：

```shell
msbuild /m /v:m /t:rebuild /p:LEGACY_CODE_METRICS_MODE=true Metrics.csproj
```

有关详细信息，请参阅[生成代码度量值在旧模式下启用](https://github.com/dotnet/roslyn-analyzers/pull/1841)。

### <a name="previous-versions"></a>早期版本

以前版本的 Visual Studio 中，包括 Visual Studio 2015 中，包含一个命令行代码指标工具，也称为*Metrics.exe*。 此以前版本的工具进行了二进制分析，即，基于程序集的分析。 新工具将改为分析源代码。 因为新的命令行代码指标工具是基于代码的源，则结果将不同于生成的以前版本的内容*Metrics.exe*和 Visual Studio 2017 IDE 中。

新的命令行代码指标工具计算度量值，即使出现源代码错误，只要可以加载的解决方案和项目。

#### <a name="metric-value-differences"></a>指标值的差异

`LinesOfCode`度量值是更加准确，且在新的命令行代码指标工具中可靠。 它是独立于任何代码生成的差异，工具集或运行时更改时不会更改。 新工具对实际代码，包括空白的行和注释的行进行计数。

其他指标，如`CyclomaticComplexity`并`MaintainabilityIndex`与以前的版本使用同一个公式*Metrics.exe*，但新的工具进行计数的`IOperations`（逻辑源指令） 而不是中间语言 (IL) 指令。 这些数字会从早期版本的略有不同*Metrics.exe*并从 Visual Studio 2017 IDE 代码度量值结果。

## <a name="see-also"></a>请参阅

- [使用代码度量结果窗口](../code-quality/working-with-code-metrics-data.md)
- [代码度量值](../code-quality/code-metrics-values.md)
