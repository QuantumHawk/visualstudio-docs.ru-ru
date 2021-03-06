---
title: Создание расширения с окном инструмента (ru) Документы Майкрософт
ms.date: 3/16/2019
ms.topic: conceptual
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 17f72cf130c5ff0f2d6d03ca8c460aa98ea39111
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80739542"
---
# <a name="create-an-extension-with-a-tool-window"></a>Создание расширения с окном инструмента

В этой процедуре вы узнаете, как использовать шаблон проекта VSIX и шаблон **пользовательского окна инструмента** для создания расширения с окном инструментов.

## <a name="prerequisites"></a>Предварительные требования

 Начиная с Visual Studio 2015, вы не устанавливаете Visual Studio SDK из центра загрузки. Он включен в качестве дополнительной функции в Visual Studio установки. Вы также можете установить VS SDK позже. Для получения дополнительной информации, [см.](../extensibility/installing-the-visual-studio-sdk.md)

### <a name="create-a-tool-window"></a>Создание окна инструмента

1. Создайте проект VSIX под названием **FirstWindow**. Шаблон проекта VSIX можно найти в диалоге **нового проекта,** ища "vsix".

2. Когда проект откроется, добавьте шаблон элемента окна инструмента под названием **MyWindow.** В **Solution Explorer**, правой кнопкой мыши узла проекта и выберите **Добавить** > **новый пункт**. В диалоге **Добавить новый элемент** перейдите на **Visual C'** > **Extensibility** и выберите **окно пользовательского инструмента.** В поле **«Имя»** в нижней части окна измените имя файла окна инструмента на *MyWindow.cs.*

3. Выполните сборку решения и запустите отладку.

   Появляется экспериментальный экземпляр Visual Studio. Для получения дополнительной информации об экспериментальном экземпляре [см.](../extensibility/the-experimental-instance.md)

4. В экспериментальном примере перейдите к **View** > **Other Windows**.

   Вы должны увидеть пункт меню для **MyWindow**. Нажмите ее.

   Вы должны увидеть окно инструмента с названием **MyWindow** и кнопкой говоря **Нажмите меня!.**
