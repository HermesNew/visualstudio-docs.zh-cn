---
title: “指令指针”(IP) 视图：.NET 内存采样数据 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: 7d91cc14-e8e9-4ebb-b14f-b9f0da770508
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: dd06bc09114785c4359d05e3cda70c3ce7646c9e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "68143673"
---
# <a name="instruction-pointers-ips-view---net-memory-sampling-data"></a>“指令指针”(IP) 视图：.NET 内存采样数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

用采样方法收集的 .NET 内存分配分析数据有一个 IP 视图，其中列出在分析运行期间分配了内存的程序集指令。 该视图的列还列出分配的大小和数量。  
  
 仅列出独占值。  
  
|列|说明|  
|------------|-----------------|  
|**进程 ID**|分析运行的进程 ID (PID)。|  
|**进程名**|进程的名称。|  
|**模块名**|指令所在模块的名称。|  
|**模块路径**|指令所在模块的路径。|  
|**源文件**|指令所在的源文件。|  
|**函数名**|函数名。|  
|**函数行号**|此函数在源文件中的起始行号。|  
|**函数地址**|函数的起始地址。|  
|**源行开始**|源文件中发生分配的起始行号。|  
|**源行结束**|源文件中发生分配的结束行号。|  
|**源字符开始**|发生分配的源文件行中起始字符的偏移量。|  
|**源字符结束**|发生分配的源文件行中结束字符的偏移量。|  
|**指令地址**|指令的地址。|  
|**独占分配数**|由指令创建的对象总数。|  
|**独占分配数百分比**|在分析运行期间创建的，由指令分配的所有对象数的百分比。|  
|**独占字节数**|分析运行期间由指令分配的内存字节数。|  
|**独占字节数百分比**|分析运行期间由指令分配的所有内存字节数的百分比。|  
  
## <a name="see-also"></a>另请参阅  
 [“指令指针”(IP) 视图](../profiling/instruction-pointers-ips-view-sampling-data.md)
