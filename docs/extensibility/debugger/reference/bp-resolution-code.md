---
title: BP_RESOLUTION_CODE Документы Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_RESOLUTION_CODE
helpviewer_keywords:
- BP_RESOLUTION_CODE structure
ms.assetid: ac103ec5-771c-4667-92de-b5abb53bbb52
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fbfd16025d338b54bec8e2e4276de62c8d00477e
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80737857"
---
# <a name="bp_resolution_code"></a>BP_RESOLUTION_CODE
Описывает расположение точки разрыва кода.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct _BP_RESOLUTION_CODE {
    IDebugCodeContext2* pCodeContext;
} BP_RESOLUTION_CODE;
```

```csharp
public struct BP_RESOLUTION_CODE {
    public IDebugCodeContext2 pCodeContext;
};
```

## <a name="members"></a>Участники
`pCodeContext`\
Объект [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) определяет положение точки разрыва в коде.

## <a name="remarks"></a>Примечания
Эта структура является членом [структуры BP_RESOLUTION_LOCATION,](../../../extensibility/debugger/reference/bp-resolution-location.md) которая, в свою очередь, является членом [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) структуры, возвращенной методом [GetResolutionInfo.](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)

## <a name="requirements"></a>Требования
Заголовок: msdbg.h

Название: Microsoft.VisualStudio.Debugger.Interop

Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Структуры и объединения](../../../extensibility/debugger/reference/structures-and-unions.md)
- [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
