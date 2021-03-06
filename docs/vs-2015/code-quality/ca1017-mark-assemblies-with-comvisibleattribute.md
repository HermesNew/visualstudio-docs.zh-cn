---
title: CA1017：用 ComVisibleAttribute 标记程序集 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 505e5780b8a50113aaf98ea7dbac767d280bebb6
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662058"
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017：用 ComVisibleAttribute 标记程序集
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkAssembliesWithComVisible|
|CheckId|CA1017|
|类别|Microsoft. Design|
|是否重大更改|不间断|

## <a name="cause"></a>原因
 程序集未应用 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> 特性。

## <a name="rule-description"></a>规则说明
 @No__t_0 特性确定 COM 客户端如何访问托管代码。 合理的设计指出程序集将显式指示 COM 可见性。 可以为整个程序集设置 COM 可见性，然后为单个类型和类型成员重写 COM 可见性。 如果该属性不存在，则该程序集的内容对 COM 客户端可见。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，请将特性添加到程序集。 如果你不希望程序集对 COM 客户端可见，请应用属性，并将其值设置为 `false`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 如果希望程序集可见，请应用属性，并将其值设置为 `true`。

## <a name="example"></a>示例
 下面的示例演示一个应用了 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 特性的程序集，该程序集用于阻止它对 COM 客户端可见。

 [!code-cpp[FxCop.Design.AssembliesCom#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/cpp/FxCop.Design.AssembliesCom.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/cs/FxCop.Design.AssembliesCom.cs#1)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/vb/FxCop.Design.AssembliesCom.vb#1)]

## <a name="see-also"></a>请参阅
 [与非托管代码](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)的互操作性，[为互操作提供 .net 类型](https://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)
