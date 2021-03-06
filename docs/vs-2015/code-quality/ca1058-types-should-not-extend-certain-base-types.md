---
title: CA1058：类型不应扩展某些基类型 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 9a4663fe3bc09b27bad9eeec05e325f07a3de6f3
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2019
ms.locfileid: "72603057"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058：类型不应扩展某些基类型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|类别|Microsoft. Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 外部可见的类型扩展某些基类型。 目前，此规则报告从以下类型派生的类型：

- <xref:System.ApplicationException?displayProperty=fullName>

- <xref:System.Xml.XmlDocument?displayProperty=fullName>

- <xref:System.Collections.CollectionBase?displayProperty=fullName>

- <xref:System.Collections.DictionaryBase?displayProperty=fullName>

- <xref:System.Collections.Queue?displayProperty=fullName>

- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

- <xref:System.Collections.SortedList?displayProperty=fullName>

- <xref:System.Collections.Stack?displayProperty=fullName>

## <a name="rule-description"></a>规则说明
 对于 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 版本1，建议从 <xref:System.ApplicationException> 中派生出新的异常。 建议已更改，新异常应派生自 <xref:System> 命名空间中 <xref:System.Exception?displayProperty=fullName> 或其子类之一。

 如果要创建基础对象模型或数据源的 XML 视图，请不要创建 <xref:System.Xml.XmlDocument> 的子类。

### <a name="non-generic-collections"></a>非泛型集合
 尽可能使用和/或扩展泛型集合。 不要在代码中扩展非泛型集合，除非你之前已将其发布。

 **错误用法的示例**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

 **正确用法的示例**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，请从其他基类型或泛型集合派生该类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 请勿禁止显示此规则发出的有关 <xref:System.ApplicationException> 冲突的警告。 可以安全地禁止显示此规则发出的有关 <xref:System.Xml.XmlDocument> 的冲突。 如果以前发布了代码，则可以安全地禁止显示非泛型集合的警告。
