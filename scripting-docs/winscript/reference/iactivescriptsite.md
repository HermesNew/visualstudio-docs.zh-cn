---
title: IActiveScriptSite |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSite interface
ms.assetid: 4d604a11-5365-46cf-ab71-39b3dbbe9f22
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 56b2a749eb3553044bda5816639498a0682e37e0
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72570085"
---
# <a name="iactivescriptsite"></a>IActiveScriptSite
由宿主实现，用于为 Windows 脚本引擎创建站点。 通常，此站点将与对脚本可见的所有对象（例如，ActiveX 控件）的容器相关联。 通常，此容器将对应于正在查看的文档或页面。 例如，Microsoft Internet Explorer 将为要显示的每个 HTML 页面创建此类容器。 页面上的每个 ActiveX 控件（或其他自动化对象）和脚本引擎本身在此容器中都是可枚举的。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|||  
|-|-|  
|方法|描述|  
|[IActiveScriptSite::GetLCID](../../winscript/reference/iactivescriptsite-getlcid.md)|检索主机用于显示用户界面元素的区域设置标识符。|  
|[IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)|获取有关通过调用[IActiveScript：： AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)方法添加到引擎中的项的信息。|  
|[IActiveScriptSite::GetDocVersionString](../../winscript/reference/iactivescriptsite-getdocversionstring.md)|检索主机定义的字符串，该字符串唯一标识宿主的当前文档版本。|  
|[IActiveScriptSite::OnScriptTerminate](../../winscript/reference/iactivescriptsite-onscriptterminate.md)|当脚本完成执行时调用。|  
|[IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)|向宿主通知脚本引擎已更改状态。|  
|[IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md)|通知宿主在引擎运行脚本时出现执行错误。|  
|[IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md)|向宿主通知脚本引擎已开始执行脚本代码。|  
|[IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md)|向宿主通知脚本引擎已从执行脚本代码返回。|  
  
## <a name="see-also"></a>请参阅  
 [活动脚本接口](../../winscript/reference/active-script-interfaces.md)