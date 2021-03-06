---
title: IDiaSymbol：： get_backEndMinor |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_backEndMinor method
ms.assetid: 37f38d19-6685-440d-a477-7127c4f8699e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2bfe1e5e3fdd78774142bf2cfe8ce6f097d64ef2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72740967"
---
# <a name="idiasymbolget_backendminor"></a>IDiaSymbol::get_backEndMinor
检索编译器的后端次版本号。

## <a name="syntax"></a>语法

```C++
HRESULT get_backEndMinor ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>参数
 `pRetVal`

弄返回后端次版本号。 请参阅“备注”。

## <a name="return-value"></a>返回值
 如果成功，将返回 `S_OK`;否则，将返回 `S_FALSE` 或错误代码。

> [!NOTE]
> @No__t_0 的返回值意味着该属性对符号不可用。

## <a name="remarks"></a>备注
 编译器通常包含两个主要元素：前端（分析器），用于处理将源代码分析成中间窗体，并将中间窗体转换为程序集。 前端的版本不同于后端，这种情况并不常见。

 前端或后端版本号由三个部分组成： \<major >。\<minor >。\<build >，其中 \<major > 是主版本号，\<minor > 是次版本号，\<build > 是生成号。 例如，13.10.3077。

## <a name="requirements"></a>要求

|需求|描述|
|-----------------|-----------------|
|标头：|dia2|
|版本：|DIA SDK v7.0|

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)