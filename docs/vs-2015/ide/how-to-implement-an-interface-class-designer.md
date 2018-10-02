---
title: Практическое руководство. Реализация интерфейса (конструктор классов) | Документы Майкрософт
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
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e3626d35867902f96b7f3d48d0b7528fa16fc7a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47561727"
---
# <a name="how-to-implement-an-interface-class-designer"></a>Практическое руководство. Реализация интерфейса (конструктор классов)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [как: реализация интерфейса (конструктор классов)](https://docs.microsoft.com/visualstudio/ide/how-to-implement-an-interface-class-designer).  
  
В конструкторе классов можно реализовать интерфейс на диаграмме классов путем подключения его к классу, который предоставляет код для методов интерфейса. Конструктор классов создает реализацию интерфейса и отображает связь между интерфейсом и классом в виде отношения наследования. Вы можете реализовать интерфейс, нарисовав между интерфейсом и классом линию наследования или перетащив интерфейс из представления классов.  
  
> [!TIP]
>  Вы можете создавать интерфейсы точно так же, как и другие типы. Если интерфейс существует, но отсутствует на диаграмме классов, сначала отобразите его. Дополнительные сведения см. в разделах [Практическое руководство. Создание типов с помощью конструктора классов](../ide/how-to-create-types-by-using-class-designer.md) и [Практическое руководство. Просмотр существующих типов (конструктор классов)](../ide/how-to-view-existing-types-class-designer.md).  
  
### <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>Реализация интерфейса с помощью рисования линии наследования  
  
1.  Отобразите на диаграмме классов интерфейс и класс, которые реализуют интерфейс.  
  
2.  Нарисуйте линию наследования от класса и интерфейса.  
  
     Отображается интерфейс без описания операций, подключенный к классу, а метка с именем интерфейса идентифицирует наследственную связь. Visual Studio создает заглушки для всех членов интерфейса.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Создание наследования между типами (конструктор классов)](../ide/how-to-create-inheritance-between-types-class-designer.md).  
  
### <a name="to-implement-an-interface-from-the-class-view-window"></a>Реализация интерфейса из окна представления классов  
  
1.  Отобразите на диаграмме классов класс, который должен реализовать интерфейс.  
  
2.  Откройте представление классов и найдите интерфейс.  
  
    > [!TIP]
    >  Если представление классов не открыто, откройте его из меню **Вид**. Дополнительные сведения о представлении классов см. в разделе [Просмотр классов и их членов](http://msdn.microsoft.com/en-us/71e9e8f3-261a-4e0c-87bf-5ec48b8bf333).  
  
3.  Перетащите узел интерфейса на фигуру класса на диаграмме.  
  
     Отображается интерфейс без описания операций, подключенный к классу, а метка с именем интерфейса идентифицирует наследственную связь. Visual Studio создает заглушки для всех членов интерфейса, на этом этапе реализуется интерфейс.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание типов с помощью конструктора классов](../ide/how-to-create-types-by-using-class-designer.md)   
 [Практическое руководство. Просмотр существующих типов (конструктор классов)](../ide/how-to-view-existing-types-class-designer.md)   
 [Практическое руководство. Создание наследования между типами (конструктор классов)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Рефакторинг классов и типов (конструктор классов)](../ide/refactoring-classes-and-types-class-designer.md)


