---
title: Шрифт и цвет Обзор | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], font and color
- font and color control [Visual Studio SDK], editors
ms.assetid: 2203e4e7-8b7f-44ec-8884-6ff718d4f278
caps.latest.revision: 23
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a4321619f249a992d9cdd044f621a21d85a6c380
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47562951"
---
# <a name="font-and-color-overview"></a>Шрифт и цвет Обзор
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [шрифт и цвет Обзор](https://docs.microsoft.com/visualstudio/extensibility/font-and-color-overview).  
  
В этом разделе рассматриваются параметры шрифта и цвета текста в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] интегрированной среды разработки (IDE). Он также понятия, категории и отображаемых элементов, и он описывает, как использовать атрибуты текста в пакеты VSPackage и базовым редактором.  
  
## <a name="the-fonts-and-colors-property-page"></a>Шрифты и цвета Свойства страницы  
 Вы можете управлять атрибуты отображаемого текста в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] интегрированной среды разработки (IDE) через **шрифты и цвета** страницу свойств. Чтобы найти **шрифты и цвета** свойство страницы на **средства** меню, щелкните **параметры**. Разверните **среды**, а затем нажмите кнопку **шрифты и цвета**.  
  
## <a name="categories-and-display-items"></a>Категории и отображаемые элементы  
 Шрифты и цвета упорядочены по **категории** и **отображаемые элементы**.  
  
-   Объект **категории** — это логические или функциональные контейнер для числа **отображаемые элементы**.  
  
     Список **категории** в **Показать параметры для** поле раскрывающегося списка **шрифты и цвета** страницу свойств.  
  
-   Объект **отображаемым элементом** — это сущность четко определенный текст, например комментарий, строка или структуре элемента управления, которая является для выделения цветом при отображении.  
  
 Каждый **отображаемым элементом** однозначно определяется внутри **категории** , которая его содержит. Следовательно, более одного **категории** может иметь **отображаемым элементом** с тем же именем.  
  
## <a name="vspackage-control-of-fonts-and-colors"></a>Элемент управления VSPackage шрифтов и цветов  
 [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] Позволяет VSPackages, для:  
  
-   Определить шрифт и цвет **категории**.  
  
-   Укажите шрифты и цвета, используемые для представления **отображаемые элементы**.  
  
-   Взаимодействовать с **шрифты и цвета** страницу свойств.  
  
-   Агрегатные несколько **категории** в группы.  
  
-   Сохранить изменения в параметрах по умолчанию.  
  
 Существует два способа для взаимодействия с настройки шрифта и цвета в пределах [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)].  
  
-   Один из способов называется *цветовой подсветки синтаксиса*. Он используется пакетом VSPackage, который настраивает существующий [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] редактор для реализации языковой службы и создать источник редактора.  
  
     Только один **категории** поддерживает этот механизм, а именно, **текстовый редактор**.  
  
-   Есть более общие вариант поддерживает все остальные **категории** и компоненты пользовательского интерфейса, отличного от редактора исходного кода при отображении текста. Дополнительные сведения см. в разделе <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>.  
  
## <a name="core-editor-text-settings"></a>Параметры текстового редактора Core  
 Параметры шрифта и цвета для объекта языковой службы базовым редактором, регулируются **EditorCategory текст** в **Показать параметры для** поле раскрывающегося списка **шрифты и цвета** страницу свойств.  
  
 При работе с редакторами, следует использовать специализированный шрифт и цвет элемента управления механизм, который предоставляет службы языка для контроля и расширить **текстовый редактор** параметры. Механизм называется *Цветовая подсветка синтаксиса* и предоставляет:  
  
-   Упрощенная методика для управления шрифты и цвета, отображаемые элементы.  
  
     Дополнительные сведения см. в разделах <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> и <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem>.  
  
-   Выделение цветом четко определенных и оптимизированный механизм.  
  
     Дополнительные сведения см. в разделе <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>.  
  
-   Оба возможность использовать встроенные отображаемые элементы из **EditorCategory текст** и расширять их.  
  
     Дополнительные сведения см. в разделе [как: Используйте встроенные цветные элементы](../extensibility/internals/how-to-use-built-in-colorable-items.md) и [пользовательских цветных элементов](../extensibility/internals/custom-colorable-items.md).  
  
-   Автоматическое сохранение текущего состояния обоих встроенных и пользовательских отображение элементов с **текстовый редактор** категории.  
  
 Дополнительные сведения о синтаксических конструкций см. в разделе [цветовая маркировка синтаксиса в языковой службе прежних версий](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).  
  
## <a name="see-also"></a>См. также  
 [Устаревшие интерфейсы в редакторе](../extensibility/legacy-interfaces-in-the-editor.md)   
 [Цветовая маркировка синтаксиса в языковой службе прежних версий](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)
