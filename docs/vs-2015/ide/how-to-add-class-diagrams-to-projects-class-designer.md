---
title: 如何：向项目中添加类图（类设计器）| Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class diagrams, creating
- Class Designer [Visual Studio], opening
ms.assetid: 0eac1b54-2711-4e4b-9654-a0c429c08c8f
caps.latest.revision: 43
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c0264aa4a514b8e508ef9d06ba75f212b629b99c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479325"
---
# <a name="how-to-add-class-diagrams-to-projects-class-designer"></a>如何：向项目中添加类图（类设计器）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 将类图添加到项目 （类设计器）](https://docs.microsoft.com/visualstudio/ide/how-to-add-class-diagrams-to-projects-class-designer)。  
  
若要设计、编辑及重构类和其他类型，请将类图添加到 Visual C# .NET、Visual Basic .NET 或 C++ 项目中。 若要直观显示项目中代码的不同部分，请将多个类图添加到该项目中。  
  
 你不可以从在多个应用间共享代码的项目创建类图。 要创建 UML 类图，请参阅[创建 UML 建模项目和关系图](../modeling/create-uml-modeling-projects-and-diagrams.md)。  
  
### <a name="to-add-a-blank-class-diagram-to-a-project"></a>向项目中添加空白类图  
  
1.  在解决方案资源管理器中，右击项目名称。 然后选择“添加新项”或“添加”、“新建项”。  
  
2.  从模板列表中选择“类图”。 对于 Visual C++ 项目，请查看“模板”下方，然后查看“实用工具”下方以查找该模板。  
  
     类图随即在类设计器中打开，并在解决方案资源管理器的项目层次结构中以一个带 .cd 扩展名的文件出现。 使用“类设计器”工具箱将形状和线条拖动到类图中。  
  
3.  要添加多个类图，请重复上述步骤。  
  
### <a name="to-add-a-class-diagram-based-on-existing-types"></a>基于现有类型添加类图  
  
1.  在解决方案资源管理器中，打开类文件上下文菜单，然后选择“查看类图”。  
  
     或  
  
     在“类视图”中，打开命名空间或类型上下文菜单，然后选择“查看类图”。  
  
### <a name="to-display-the-contents-of-a-complete-project-in-a-class-diagram"></a>在类图中显示完整项目的内容  
  
1.  在“解决方案资源管理器”或“类视图”中，右键单击该项目并选择“视图”，然后选择“查看类图”。  
  
     即会创建一个自动填充的类图。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用类设计器创建类型](../ide/how-to-create-types-by-using-class-designer.md)   
 [如何：查看现有类型（类设计器）](../ide/how-to-view-existing-types-class-designer.md)   
 [设计类和类型（类设计器）](../ide/designing-classes-and-types-class-designer.md)   
 [查看类型和关系（类设计器）](../ide/viewing-types-and-relationships-class-designer.md)   
 [使用类图（类设计器）](../ide/working-with-class-diagrams-class-designer.md)


