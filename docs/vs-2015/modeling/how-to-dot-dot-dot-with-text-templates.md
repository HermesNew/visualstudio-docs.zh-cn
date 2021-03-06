---
title: 如何。带有文本模板 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: d1ac2509-0479-47eb-809c-1f171245d0b6
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c55c7a277d3f38b36367008ae6393f58c9c9a2c2
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671616"
---
# <a name="how-to--with-text-templates"></a>如何：使用文本模板 ...
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

@No__t_0 中的文本模板提供了一种有效的方式来生成任何类型的文本。 您可以使用文本模板，在运行时生成文本作为应用程序的一部分，并在设计时生成某些项目代码。 本主题概述最常问的 "如何实现 ..." 怀疑.

 在本主题中，前面有项目符号的多个答案是备选建议。

 有关文本模板的常规介绍，请参阅[代码生成和 T4 文本模板](../modeling/code-generation-and-t4-text-templates.md)。

## <a name="how-to-"></a>如何。

### <a name="generate-part-of-my-application-code"></a>生成部分应用程序代码
 我在文件或数据库中有配置或*模型*。 我的代码的一个或多个部分依赖于该模型。

- 从文本模板生成某些代码文件。 有关详细信息，请参阅[使用 T4 文本模板生成设计时代码](../modeling/design-time-code-generation-by-using-t4-text-templates.md)和[开始编写模板的最佳方式是什么？](#starting)。

### <a name="generate-files-at-run-time-passing-data-into-the-template"></a>在运行时生成文件，将数据传递到模板
 在运行时，应用程序会生成包含标准文本和数据混合的文本文件（如报表）。 我想避免写入数百个 `write` 语句。

- 将运行时文本模板添加到你的项目。 此模板在您的代码中创建一个类，您可以实例化此类，并使用它来生成文本。 可在构造函数参数中将数据传递给它。 有关详细信息，请参阅[带有 T4 文本模板的运行时文本生成](../modeling/run-time-text-generation-with-t4-text-templates.md)。

- 如果希望从仅在运行时可用的模板生成，则可以使用标准文本模板。 如果要编写 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 扩展，则可以调用文本模板化服务。 有关详细信息，请参阅[在 VS 扩展中调用文本转换](../modeling/invoking-text-transformation-in-a-vs-extension.md)。 在其他上下文中，可以使用文本模板化引擎。 有关更多信息，请参见<xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>。

     使用 \< # @parameter # > 指令将参数传递给这些模板。 有关详细信息，请参阅[T4 参数指令](../modeling/t4-parameter-directive.md)。

### <a name="read-another-project-file-from-a-template"></a>从模板中读取另一个项目文件
 若要从与模板相同的 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 项目读取文件：

- 将 `hostSpecific="true"` 插入 `<#@template#>` 指令。

     在代码中，使用 `this.Host.ResolvePath(filename)` 获取文件的完整路径。

### <a name="invoke-methods-from-a-template"></a>从模板调用方法
 如果方法已存在，例如，在标准 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 类中：

- 使用 \< # @assembly # > 指令加载程序集，并使用 \< # @import # > 设置命名空间上下文。 有关详细信息，请参阅[T4 Import 指令](../modeling/t4-import-directive.md)。

   如果经常使用相同的一组程序集和导入指令，则考虑编写指令处理器。 在每个模板中，可以调用指令处理器，该处理器可加载程序集和模型文件并设置命名空间上下文。 有关详细信息，请参阅[创建自定义 T4 文本模板指令处理器](../modeling/creating-custom-t4-text-template-directive-processors.md)。

  如果你要自行编写方法：

- 如果要编写运行时文本模板，请编写与运行时文本模板同名的分部类定义。 将其他方法添加到此类中。

- 编写类功能控制块 `<#+ ... #>`，你可以在其中声明方法、属性和私有类。 在编译文本模板时，它将转换为类。 标准控制块 `<#...#>` 和文本将转换为单个方法，类功能块作为单独的成员插入。 有关详细信息，请参阅[文本模板控制块](../modeling/text-template-control-blocks.md)。

   定义为类功能的方法还可以包括嵌入文本块。

   请考虑将类功能置于单独的文件中，以便 `<#@include#>` 到一个或多个模板文件中。

- 在单独的程序集（类库）中编写方法，并从模板中调用这些方法。 使用 `<#@assembly#>` 指令加载程序集，并 `<#@import#>` 设置命名空间上下文。 请注意，若要在调试时重新生成程序集，则可能需要停止并重新启动 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。 有关详细信息，请参阅[T4 文本模板指令](../modeling/t4-text-template-directives.md)。

### <a name="generate-many-files-from-one-model-schema"></a>从一个模型架构生成许多文件
 如果您经常从具有相同 XML 或数据库架构的模型生成文件：

- 请考虑编写指令处理器。 这使您可以将每个模板中的多个 assembly 语句和 import 语句替换为单个自定义指令。 指令处理器还可以加载和分析模型文件。 有关详细信息，请参阅[创建自定义 T4 文本模板指令处理器](../modeling/creating-custom-t4-text-template-directive-processors.md)。

### <a name="generate-files-from-a-complex-model"></a>从复杂模型生成文件

- 考虑创建用于表示模型的域特定语言（DSL）。 这使得编写模板更为容易，因为您使用的类型和属性反映了模型中元素的名称。 您不必分析文件或导航 XML 节点。 例如:

     `foreach (Book book in this.Library) { ... }`

     有关详细信息，请参阅[使用域特定语言入门](../modeling/getting-started-with-domain-specific-languages.md)和[从域特定语言生成代码](../modeling/generating-code-from-a-domain-specific-language.md)。

- 考虑从 UML 模型生成代码。 代码不必直接反映 UML。 例如，不必为 UML 模型中的每个类生成类。 相反，您可以使用 UML 类图来表示网站，并从每个 UML 类生成网页。 选择最接近需求的关系图类型。 例如，选择 "活动图" 来表示任何类型的工作流。 你可以定义构造型，以将适用于你的应用程序的信息添加到每个类型的元素。

     通过从 UML 模型生成，可以在关系图的窗体中绘制和编辑模型，但不需要设计自己的关系图类型，就像在 DSL 中那样。

     有关详细信息，请参阅为[应用程序创建模型](../modeling/create-models-for-your-app.md)和[从 UML 模型生成文件](../modeling/generate-files-from-a-uml-model.md)。

### <a name="get-data-from-includevsprvsincludesvsprvs-mdmd"></a>从 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 获取数据
 若要使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中提供的服务，请设置 `hostSpecific` 特性并加载 `EnvDTE` 程序集。 例如:

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetService(typeof(EnvDTE.DTE));
#>

Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>

```

### <a name="execute-text-templates-in-the-build-process"></a>在生成过程中执行文本模板

- 有关详细信息，请参阅[生成过程中的代码生成](../modeling/code-generation-in-a-build-process.md)。

## <a name="more-general-questions"></a>更多一般问题

### <a name="starting"></a>开始编写文本模板的最佳方式是什么？

1. 编写生成的文件的特定示例。

2. 通过插入 `<#@template #>` 指令，以及加载输入文件或模型所需的指令和代码，将其转换为文本模板。

3. 用表达式和代码块逐渐替换部分文件。

### <a name="what-is-a-model"></a>什么是 "模型"？

- 模板读取的输入。 它可以在文件或数据库中。 它可以是 XML、Visio 绘图、特定于域的语言（DSL）或 UML 模型，也可以是纯文本。 它可以分布在多个文件中。 通常，多个模板读取一个模型。

     术语 "模型" 的含义在于它比生成的程序代码或其他文件更直接表示业务的某些方面。 例如，它可能表示生成的软件将监督的通信网络的计划。

### <a name="what-is-the-benefit-of-using-text-templates"></a>使用文本模板的好处是什么？
 通常，您将从一个模型生成多个代码或其他文件。 模型比生成的代码更直接表示要求。 它省略了实现的详细信息，并根据要求而不是代码来编写。 当需求发生变化时–通常情况是，您可以比程序代码的不同部分更轻松、更可靠地更新模型。

 因此，从敏捷开发方法的角度来看，代码生成是一个非常有用的工具。

### <a name="what-best-practices-are-there-for-text-templates"></a>用于文本模板的 "最佳实践" 是什么？

- 有关详细信息，请参阅[编写 T4 文本模板的准则](../modeling/guidelines-for-writing-t4-text-templates.md)。

### <a name="what-is-t4"></a>什么是 "T4"？

- 此处所述 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 文本模板功能的另一个名称。 以前的版本（未发布）是 "文本模板转换" 的缩写。
