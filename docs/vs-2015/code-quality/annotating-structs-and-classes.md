---
title: 批注结构和类 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: jillfra
ms.openlocfilehash: 6db2202971facb0419db68c04835c8d5c848f528
ms.sourcegitcommit: 68f893f6e472df46f323db34a13a7034dccad25a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "77271582"
---
# <a name="annotating-structs-and-classes"></a>批注结构和类
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

您可以通过使用类似于固定条件的批注来批注结构和类成员，在任何将封闭结构作为参数或结果值的函数调用或函数入口/出口上，它们都假设为 true。  
  
## <a name="struct-and-class-annotations"></a>结构和类批注  
  
- `_Field_range_(low, high)`  
  
     该字段的范围是从 `low` 到 `high`。  等效于使用合适的前置或后置条件应用于批注对象的 `_Satisfies_(_Curr_ >= low && _Curr_ <= high)`。  
  
- `_Field_size_(size)`、`_Field_size_opt_(size)`、`_Field_size_bytes_(size)`、`_Field_size_bytes_opt_(size)`  
  
     在 `size`指定的元素（或字节）内具有可写大小的字段。  
  
- `_Field_size_part_(size, count)`、`_Field_size_part_opt_(size, count)`、`_Field_size_bytes_part_(size, count)``_Field_size_bytes_part_opt_(size, count)`  
  
     在 `size`指定的元素（或字节）中具有可写大小的字段，以及可读的元素（字节）的 `count`。  
  
- `_Field_size_full_(size)`、`_Field_size_full_opt_(size)`、`_Field_size_bytes_full_(size)`、`_Field_size_bytes_full_opt_(size)`  
  
     在 `size`指定的元素（或字节）中具有可读和可写大小的字段。  
  
- `_Struct_size_bytes_(size)`  
  
     在 `size`指定的元素（或字节）中具有可读和可写大小的字段。  
  
     适用于 struct 或类声明。  指示该类型的有效对象可能大于声明的类型，以及 `size`指定的字节数。  例如：  
  
    ```cpp  
  
    typedef _Struct_size_bytes_(nSize)  
    struct MyStruct {  
        size_t nSize;  
        …  
    };  
  
    ```  
  
     然后，将 `MyStruct *` 类型的参数 `pM` 的缓冲区大小（以字节为单位）为：  
  
    ```cpp  
    min(pM->nSize, sizeof(MyStruct))  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [使用 SAL 注释减少 C/C++代码缺陷](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [了解 SAL](../code-quality/understanding-sal.md)   
 [批注函数参数和返回值](../code-quality/annotating-function-parameters-and-return-values.md)   
 [批注函数行为](../code-quality/annotating-function-behavior.md)   
 [批注锁定行为](../code-quality/annotating-locking-behavior.md)   
 [指定何时以及在何处应用批注](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [内部函数](../code-quality/intrinsic-functions.md)   
 [最佳做法和示例](../code-quality/best-practices-and-examples-sal.md)
