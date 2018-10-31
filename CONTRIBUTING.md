# <a name="contributing"></a>参与

感谢你对参与 Visual Studio 文档的关注！

本主题将介绍在 [Visual Studio 文档站点](https://docs.microsoft.com/visualstudio)中添加或更新内容的基本过程。

本主题将介绍：

* [参与流程](#process-for-contributing)
* [指南清单](#guidance-checklist)
* [生成文档](#building-the-docs)
* [提供示例](#contributing-to-samples)
* [参与者许可协议](#contributor-license-agreement)

## <a name="process-for-contributing"></a>参与流程

步骤 1：提出问题，描述你要编写的文章及其与现有内容的相关性。
“文档”文件夹中的内容按内容范围（例如，调试器）划分成不同的部分。 为新内容确定正确的文件夹。 获取对建议的反馈。 

可以稍作更改，跳过第一个步骤。

步骤 2：对 `MicrosoftDocs/visualstudio-docs` 存储库进行分叉。

步骤 3：为文章创建 `branch`。

步骤 4：编写文章。

如果要新建主题，可以使用此[模板文件](./styleguide/template.md)作为起点。 它包含编写指南，还介绍了每篇文章所需的元数据，例如作者信息。

导航到与步骤 1 中为文章确定的 TOC 位置对应的文件夹。
该文件夹包含该部分中的所有文章的 Markdown 文件。 如有必要，可以创建一个新文件夹来放置内容文件。

对于图像和其他静态资源，请将其添加到名为“媒体”的子文件夹中。 如果要为内容创建新文件夹，请将媒体文件夹添加到新文件夹。

请务必遵循正确的 Markdown 语法。 有关详细信息，请参阅[风格指南](./styleguide/template.md)。

### <a name="example-structure"></a>结构示例

    docs
      /debugger
          debugging-installed-app-package.md
          /media
              debugging-installed-app-package.png

步骤 5：从分支将拉取请求 (PR) 提交到 `MicrosoftDocs/visualstudio-docs/master`。

如果 PR 正在解决现有问题，请将 `Fixes #Issue_Number` 关键字添加到提交消息或 PR 描述中，以便在合并 PR 时自动关闭该问题。 有关详细信息，请参阅[通过提交消息关闭问题](https://help.github.com/articles/closing-issues-via-commit-messages/)。

Visual Studio 团队将审核 PR，并告知更改是否正常或是否需要进行任何其他更新/更改才能批准。

步骤 6：与团队讨论后，对分支进行必要的更新。

一旦应用反馈且更改正常，维护人员会将 PR 合并到主分支。

我们会以某种节奏，将所有提交从主分支推送到实时分支，你将能在 https://docs.microsoft.com/visualstudio/ 中实时看到你的参与内容。

## <a name="dos-and-donts"></a>注意事项

下面是一个简短的指导规则列表，当你参与 .NET 文档时应牢记其中内容。

- 请勿发出大型拉取请求。 可以提出问题并发起讨论，以便我们在你花费大量时间前确定方向。
- 请务必阅读[风格指南](./styleguide/template.md)以及[语气和语调](./styleguide/voice-tone.md)指南。
- 请务必使用[模板](./styleguide/template.md)文件作为工作的起点。
- 请务必在处理文章前，在分叉上创建一个单独的分支。
- 请务必遵循 [GitHub 流工作流](https://guides.github.com/introduction/flow/)。
- 请务必在博客和推文（或任何社交软件上）频繁地发布你的参与内容！

> [!NOTE]
> 你或许会注意到某些主题目前并没有遵循此处指定的所有准则和[风格指南](./styleguide/template.md)。 我们正努力实现整个站点的一致性。 请查看我们当前正在跟踪的有关此特定目标的[未解决问题](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Aguidelines-adherence)列表。

## <a name="building-the-docs"></a>生成文档

该文档使用[ GitHub Flavored Markdown ](https://help.github.com/categories/writing-on-github/)编写，并使用[ DocFX ](https://dotnet.github.io/docfx/)和其他内部发布/生成工具生成。 文档托管在 [docs.microsoft.com](https://docs.microsoft.com/dotnet)。

如果想要生成本地文档，则需要安装最新版的 [DocFX](https://dotnet.github.io/docfx/)。

有许多使用 DocFX 的方法，[DocFX 入门指南](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html)中介绍了其中的大多数方法。
以下说明使用该工具的[基于命令行的](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html#2-use-docfx-as-a-command-line-tool)版本。
如果你对以上链接中列出的其他方式更熟悉，可以使用这些方式。

注意：当前的 DocFX 需要使用 .NET Framework（对于 Windows）或 Mono（对于 Linux 或 macOS）。 我们希望在将来将其移植到 .NET Core。

可以使用内置 Web 服务器在本地生成和预览生成的站点。 导航到计算机上的核心文档文件夹并键入以下命令：

```
docfx -t default --serve
```

这将在[ localhost：8080 ](http://localhost:8080)上启动本地预览。 然后可以通过转到 `http://localhost:8080/[path]`（如 http://localhost:8080/articles/welcome.html）查看所作的更改。

注意：本地预览目前不包含任何主题，因此外观和文档站点不同。 我们正在努力改善体验。

# <a name="contributing-to-samples"></a>提供示例

现在，在文章中将所需示例代码作为内联代码块添加。 存储库中有一个 codesnippets 文件夹，但尚未准备好进行公开参与。
