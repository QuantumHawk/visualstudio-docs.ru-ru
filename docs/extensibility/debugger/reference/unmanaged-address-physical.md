---
title: UNMANAGED_ADDRESS_PHYSICAL Документы Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UNMANAGED_ADDRESS_PHYSICAL
helpviewer_keywords:
- UNMANAGED_ADDRESS_PHYSICAL structure
ms.assetid: fed09686-caa6-4efc-851e-a0432019e9d0
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9070fcfbf79fb96ecff87a793c221f3e7a65c2ae
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80713288"
---
# <a name="unmanaged_address_physical"></a>UNMANAGED_ADDRESS_PHYSICAL
Эта структура представляет собой физический адрес.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct _tagUNMANAGED_ADDRESS_PHYSICAL {
   ULONGLONG offset;
} UNMANAGED_ADDRESS_PHYSICAL;
```

```csharp
public struct UNMANAGED_ADDRESS_PHYSICAL {
   public ulong offset;
}
```

## <a name="members"></a>Участники
 `offset`\
 64-битное смещение в физическое адресное пространство.

## <a name="remarks"></a>Примечания
 Эта структура является частью соединения в `dwKind` [структуре DEBUG_ADDRESS_UNION,](../../../extensibility/debugger/reference/debug-address-union.md) когда `ADDRESS_KIND_UNMANAGED_PHYSICAL` поле `DEBUG_ADDRESS_UNION` структуры устанавливается (значение от [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) перечисления).

## <a name="requirements"></a>Требования
 Заголовок: sh.h

 Название: Microsoft.VisualStudio.Debugger.Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Структуры и объединения](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
