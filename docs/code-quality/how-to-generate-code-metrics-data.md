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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96b74421d638a99823399a0049b712bc6c54c8a9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53849053"
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

可以从命令行生成代码度量数据C#和.NET Framework、.NET Core 和.NET Standard 应用的 Visual Basic 项目。 命令行代码度量工具称为*Metrics.exe*。

若要获取*Metrics.exe*可执行文件，您必须[自己生成](#generate-the-executable)。 在不久的将来，[已发布的新版*Metrics.exe*将提供](https://github.com/dotnet/roslyn-analyzers/issues/1756)这样就不必自己构建。

### <a name="generate-the-executable"></a>生成可执行文件

若要生成可执行文件*Metrics.exe*，请执行以下步骤：

1. 克隆[dotnet/roslyn 的分析器](https://github.com/dotnet/roslyn-analyzers)存储库。
2. 以管理员身份打开 Visual Studio 开发人员命令提示。
3. 根目录**roslyn 分析器**存储库中，执行以下命令： `Restore.cmd`
4. 将目录更改为*src\Tools*。
5. 执行以下命令以生成**Metrics.csproj**项目：

   ```shell
   msbuild /m /v:m /p:Configuration=Release Metrics.csproj
   ```

   名为可执行文件*Metrics.exe*中生成*artifacts\bin*目录存储库根目录下。

   > [!TIP]
   > 若要构建*Metrics.exe*中[旧模式](#legacy-mode)，执行以下命令：
   >
   > ```shell
   > msbuild /m /v:m /t:rebuild /p:LEGACY_CODE_METRICS_MODE=true Metrics.csproj
   > ```

### <a name="usage"></a>用法

若要运行*Metrics.exe*、 提供一个项目或解决方案和一个输出 XML 文件作为自变量。 例如：

```shell
C:\>Metrics.exe /project:ConsoleApp20.csproj /out:report.xml
Loading ConsoleApp20.csproj...
Computing code metrics for ConsoleApp20.csproj...
Writing output to 'report.xml'...
Completed Successfully.
```

### <a name="output"></a>输出

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
                  <Method Name="void Program.Main(string[] args)" File="C:\Users\mavasani\source\repos\ConsoleApp20\ConsoleApp20\Program.cs" Line="7">
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

### <a name="tool-differences"></a>工具的差异

以前版本的 Visual Studio 中，包括 Visual Studio 2015 中，包含名为的命令行代码指标工具*Metrics.exe*。 此以前版本的工具进行了二进制分析，即，基于程序集的分析。 新工具将改为分析源代码。 因为新*Metrics.exe*是源基于代码的则结果将为生成的以前版本的内容不同*Metrics.exe*和 Visual Studio 2017 IDE 中。

新*Metrics.exe*工具可以计算度量值，即使出现源代码错误，只要可以加载的解决方案和项目。

#### <a name="metric-value-differences"></a>指标值的差异

`LinesOfCode`度量值是更加准确，且在新可靠*Metrics.exe*。 它是独立于任何代码生成的差异，工具集或运行时更改时不会更改。 新*Metrics.exe*对实际代码，包括空白的行和注释的行进行计数。

其他指标，如`CyclomaticComplexity`并`MaintainabilityIndex`与以前的版本使用同一个公式*Metrics.exe*，但新*Metrics.exe*的计数`IOperations`（逻辑源的说明进行操作） 而不是中间语言 (IL) 指令。 这些数字会从早期版本的略有不同*Metrics.exe*并从 Visual Studio 2017 IDE 代码度量值结果。

### <a name="legacy-mode"></a>旧模式

您还可以选择生成*Metrics.exe*中*旧模式*。 旧模式版本的工具生成更接近于哪些较旧版本的工具生成的指标值。 此外，在旧模式下， *Metrics.exe*为一组相同的方法类型版本的工具生成代码度量值的上一生成代码度量值。 例如，它不会生成代码度量数据字段和属性的初始值设定项。 对于向后兼容性，或者你对代码签入的入口基于代码度量值的数字，传统模式很有用。 要生成的命令*Metrics.exe*在旧模式是：

```shell
msbuild /m /v:m /t:rebuild /p:LEGACY_CODE_METRICS_MODE=true Metrics.csproj
```

有关详细信息，请参阅[生成代码度量值在旧模式下启用](https://github.com/dotnet/roslyn-analyzers/pull/1841)。

## <a name="see-also"></a>请参阅

- [使用代码度量结果窗口](../code-quality/working-with-code-metrics-data.md)
- [代码度量值](../code-quality/code-metrics-values.md)
