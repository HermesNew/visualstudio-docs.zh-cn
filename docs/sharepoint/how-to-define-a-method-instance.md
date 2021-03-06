---
title: 如何：定义方法实例 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method instance
- BDC [SharePoint development in Visual Studio], method
- Business Data Connectivity service [SharePoint development in Visual Studio], method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0e21900e87278ad500ee8497d1dd0c49350695d1
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "72981799"
---
# <a name="how-to-define-a-method-instance"></a>如何：定义方法实例
  必须为模型中的每个方法定义至少一个方法实例。

 使用 " **BDC 方法详细信息**" 窗口添加方法实例。 添加方法实例时，Visual Studio 会将 `<MethodInstance>` 元素添加到项目中模型文件的 XML。 有关 `<MethodInstance>` 元素的特性的详细信息，请参阅[MethodInstance](/previous-versions/office/developer/sharepoint-2010/ee556838(v=office.14))。

### <a name="to-define-a-method-instance"></a>定义方法实例

1. 在 " **BDC 方法详细信息**" 窗口中，展开方法的节点，然后展开 "**实例**" 节点。

2. 在 "**添加方法实例**" 列表中，选择 "**创建 Finder 实例**"。

     "**实例**" 节点下将出现一个新的方法实例。

3. 在菜单栏上，选择 "**查看** > **属性" 窗口**。

4. 在 "**属性**" 窗口中，设置方法实例的属性。 有关每个属性的详细信息，请参阅[MethodInstance](/previous-versions/office/developer/sharepoint-2010/ee556838(v=office.14))。

## <a name="see-also"></a>请参阅
- [BDC 模型设计工具概述](../sharepoint/bdc-model-design-tools-overview.md)
- [如何：向模型添加实体](../sharepoint/how-to-add-an-entity-to-a-model.md)
- [如何：向方法添加参数](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [如何：定义参数的类型描述符](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)
- [设计业务数据连接模型](../sharepoint/designing-a-business-data-connectivity-model.md)
