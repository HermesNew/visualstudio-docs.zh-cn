---
title: ZipDirectory 任务 | Microsoft Docs
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ZipDirectory
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ZipDirectory task [MSBuild]
- MSBuild, ZipDirectory task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
caps.latest.revision: 16
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8c9a51fe097eb110e44b3f4bd932a26f4efb6ea6
ms.sourcegitcommit: 96737c54162f5fd5c97adef9b2d86ccc660b2135
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77630634"
---
# <a name="zipdirectory-task"></a>ZipDirectory 任务

根据目录内容创建 .zip 存档。 

>[!NOTE]
>仅在 MSBuild 15.8 及更高版本中提供 `ZipDirectory` 任务。

## <a name="parameters"></a>参数

 下表描述了 `ZipDirectory` 任务的参数。

|参数|描述|
|---------------|-----------------|
|`DestinationFile`|<xref:Microsoft.Build.Framework.ITaskItem> 参数（必选）<br /><br /> 要创建的 .zip 文件的完整路径。 |
|`Overwrite`|可选 `Boolean` 参数。<br /><br /> 如果为 `true`，则跳过要覆盖的目标文件（如有）。 默认为 `false`。|
|`SourceDirectory`|必选 <xref:Microsoft.Build.Framework.ITaskItem> 参数。<br /><br /> 指定要从中创建 .zip 存档的目录。 |

## <a name="remarks"></a>备注

 除上面列出的参数外，此任务还从 <xref:Microsoft.Build.Tasks.TaskExtension> 类继承参数，后者自身继承自 <xref:Microsoft.Build.Utilities.Task> 类。 有关这些其他参数的列表及其说明的信息，请参阅 [TaskExtension 基类](../msbuild/taskextension-base-class.md)。

## <a name="example"></a>示例

 以下示例在生成项目后基于输出目录创建 .zip 存档。 

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <Target Name="ZipOutputPath" AfterTargets="Build">
        <ZipDirectory
            SourceDirectory="$(OutputPath)"
            DestinationFile="$(MSBuildProjectDirectory)\output.zip" />
    </Target>

</Project>
```

## <a name="see-also"></a>请参阅

- [任务](../msbuild/msbuild-tasks.md)
- [任务参考](../msbuild/msbuild-task-reference.md)
