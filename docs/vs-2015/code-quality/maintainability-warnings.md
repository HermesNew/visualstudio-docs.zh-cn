---
title: 可维护性警告 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e448a72e2ff92b3e3028829d4b1e7658c304ee3c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667895"
---
# <a name="maintainability-warnings"></a>维护性警告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可维护性警告支持库和应用程序维护。

## <a name="in-this-section"></a>本节内容

|规则|描述|
|----------|-----------------|
|[CA1500：变量名不应与字段名相同](../code-quality/ca1500-variable-names-should-not-match-field-names.md)|实例方法声明的参数或本地变量的名称与声明类型的实例字段匹配，这将导致错误。|
|[CA1501：避免过度继承](../code-quality/ca1501-avoid-excessive-inheritance.md)|类型在继承层次结构中的深度超过四级。 深度嵌套的类型层次结构可能很难遵循、理解和维护。|
|[CA1502：避免过度复杂](../code-quality/ca1502-avoid-excessive-complexity.md)|此规则通过方法来测量线性独立的路径的数量，该数量是由条件分支的数量和复杂度决定的。|
|[CA1504：检查令人误解的字段名](../code-quality/ca1504-review-misleading-field-names.md)|实例字段的名称以 "s_" 开头，或静态（在 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] 中共享）字段的名称以 "m_" 开头。|
|[CA1505：避免编写无法维护的代码](../code-quality/ca1505-avoid-unmaintainable-code.md)|类型或方法具有较低的可维护性索引值。 如果可维护性指数较低，则表示类型或方法可能难以维护，最好重新进行设计。|
|[CA1506：避免过度类耦合](../code-quality/ca1506-avoid-excessive-class-coupling.md)|此规则通过计算类型或方法包含的唯一类型引用的个数来衡量类耦合。|

## <a name="see-also"></a>请参阅
 [测量托管代码的复杂性和可维护性](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
