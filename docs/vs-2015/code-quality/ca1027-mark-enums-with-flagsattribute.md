---
title: CA1027：用 FlagsAttribute 标记枚举 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkEnumsWithFlags
- CA1027
helpviewer_keywords:
- CA1027
- MarkEnumsWithFlags
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 6f2dc7dcd79fbcaf47a2db3cf49f22f3467a06ab
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661937"
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027：用 FlagsAttribute 标记枚举
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkEnumsWithFlags|
|CheckId|CA1027|
|类别|Microsoft. Design|
|是否重大更改|不间断|

## <a name="cause"></a>原因
 公共枚举的值是2的幂或是枚举中定义的其他值的组合，且 <xref:System.FlagsAttribute?displayProperty=fullName> 特性不存在。 若要减少误报，此规则不对具有连续值的枚举报告冲突。

## <a name="rule-description"></a>规则说明
 枚举是一种值类型，它定义一组相关的已命名常数。 将 <xref:System.FlagsAttribute> 应用于枚举（当其命名常量可以有意义组合）时。 例如，考虑一个应用程序中一周中的几天的枚举，该枚举跟踪可用的日期。 如果每个资源的可用性是通过使用 <xref:System.FlagsAttribute> 的枚举进行编码的，则可以表示任意日期组合。 如果没有属性，则只能表示一周中的一天。

 对于存储可组合枚举的字段，单独的枚举值在字段中被视为位组。 因此，此类字段有时被称为*位域*。 若要将存储的枚举值组合到位域中，请使用布尔条件运算符。 若要测试位域以确定是否存在特定的枚举值，请使用布尔逻辑运算符。 若要使位域正确存储和检索组合的枚举值，枚举中定义的每个值都必须是2的幂。 除非这样，否则布尔逻辑运算符将无法提取存储在字段中的单个枚举值。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，请将 <xref:System.FlagsAttribute> 添加到枚举。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果你不希望枚举值可组合，请禁止显示此规则发出的警告。

## <a name="example"></a>示例
 在下面的示例中，`DaysEnumNeedsFlags` 为满足使用 <xref:System.FlagsAttribute> 的要求的枚举，但没有该枚举。 @No__t_0 枚举的值不是2的幂，但不正确地指定 <xref:System.FlagsAttribute>。 这违反[了规则 CA2217：请勿用 FlagsAttribute 标记枚举](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)。

 [!code-csharp[FxCop.Design.EnumFlags#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumFlags/cs/FxCop.Design.EnumFlags.cs#1)]

## <a name="related-rules"></a>相关规则
 [CA2217：不要使用 FlagsAttribute 标记枚举](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>请参阅
 <xref:System.FlagsAttribute?displayProperty=fullName>
