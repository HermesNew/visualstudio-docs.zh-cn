---
title: CA1033：接口方法应可由子类型调用 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 2ee44537ba4f7f7efd65de2c8a27d139d9750b77
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661869"
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033：接口方法应可由子类型调用
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|
|CheckId|CA1033|
|类别|Microsoft. Design|
|是否重大更改|不间断|

## <a name="cause"></a>原因
 未密封的外部可见类型提供了显式实现公共接口的方法，但没有提供具有相同名称的其他外部可见方法。

## <a name="rule-description"></a>规则说明
 考虑显式实现公共接口方法的基类型。 派生自基类型的类型只能通过对被强制转换为接口的当前实例（`this` C#）的引用访问继承的接口方法。 如果派生类型重新实现（显式）继承的接口方法，则无法再访问基实现。 通过当前实例引用的调用将调用派生实现;这将导致递归和最终的堆栈溢出。

 如果提供了外部可见 `Close()` 或 `System.IDisposable.Dispose(Boolean)` 方法，则此规则不会报告 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 的显式实现的冲突。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，请实现新的方法，该方法公开相同的功能，并对派生类型可见或更改为 nonexplicit 实现。 如果可接受重大更改，替代方法是使类型成为密封类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果提供了与显式实现的方法具有相同功能但名称不同的外部可见方法，则可以安全地禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示了违反规则的类型，`ViolatingBase`，并显示了一个 `FixedBase` 的类型，该类型显示了冲突的修复。

 [!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ExplicitMethodImplementations/cs/FxCop.Design.ExplicitMethodImplementations.cs#1)]

## <a name="see-also"></a>请参阅
 [接口](https://msdn.microsoft.com/library/2feda177-ce11-432d-81b4-d50f5f35fd37)
