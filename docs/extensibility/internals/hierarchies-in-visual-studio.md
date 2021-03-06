---
title: Иерархии в визуальной студии (ru) Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- hierarchies, Visual Studio IDE
- IDE, hierarchies
ms.assetid: 0a029a7c-79fd-4b54-bd63-bd0f21aa8d30
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cdbb8a0e58f6b1e5bc6e32f8c319d1480c4db4b5
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80708191"
---
# <a name="hierarchies-in-visual-studio"></a>Иерархии в Visual Studio
Интегрированная [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] среда разработки (IDE) отображает проект как *иерархию.* В IDE иерархия представляет собой дерево узлов, где каждый узлы имеет набор связанных свойств. *Иерархия проекта* — это контейнер, в мещающий элементы проекта, отношения элементов и связанные с ними свойства и команды.

 В [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], вы управляете иерархиями проектов <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>с помощью интерфейса иерархии, . Интерфейс <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> перенаправляет команды, которые вы вызываете из элементов проекта в соответствующее окно иерархии вместо стандартного обработчика команд.

## <a name="project-hierarchies"></a>Иерархии проектов
 Каждая иерархия проекта содержит элементы, которые можно просматривать и отомещать. Эти элементы варьируются в зависимости от типа проекта. Например, проект базы данных может содержать сохраненные процедуры, представления данных и таблицы баз данных. С другой стороны, проект на языке программирования, скорее всего, будет включать исходные файлы и файлы ресурсов для бит-карт и диалоговых коробок. Иерархии могут быть вложены, что дает вам некоторую дополнительную гибкость при создании иерархии проекта.

 При создании нового типа проекта тип проекта управляет полным набором элементов, которые могут быть отредактированы в нем. Тем не менее, проекты могут содержать элементы, для которых они не имеют поддержки редактирования. Например, проекты Visual C', возможно, содержат HTML-файлы, даже несмотря на то, что Visual C' не предоставляет настраиваемого редактора для типа HTML файла.

 Иерархии управляют сохранением содержащихся в них элементов. Реализация иерархии должна контролировать любые специальные свойства, влияющие на сохранение элементов в иерархии. Например, если элементы представляют объекты в репозитории вместо файлов, реализация иерархии должна контролировать сохранение этих объектов. IDE сам направляет иерархию для сохранения элементов в соответствии с пользовательским вводом, но IDE не контролирует никаких действий, необходимых для сохранения этих элементов. Вместо этого проект находится под контролем.

 Когда пользователь открывает элемент в редакторе, иерархия, контролирующая этот элемент, выбрана и становится активной иерархией. Выбранная иерархия определяет набор команд, доступных для действия элемента. Отслеживание фокусировки пользователей таким образом позволяет иерархии отражать текущий контекст пользователя.

## <a name="see-also"></a>См. также
- [Типы проектов](../../extensibility/internals/project-types.md)
- [Выбор и валюта в IDE](../../extensibility/internals/selection-and-currency-in-the-ide.md)
- [Образцы VSSDK](https://github.com/Microsoft/VSSDK-Extensibility-Samples)
