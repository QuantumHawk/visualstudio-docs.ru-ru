---
title: JavaScript и TypeScript в Visual Studio 2019
ms.date: 03/16/2020
ms.technology: vs-javascript
ms.topic: conceptual
dev_langs:
- JavaScript
- TypeScript
- DHTML
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: '>= vs-2019'
ms.openlocfilehash: 199a27dbfef2b7297563e87d973137e2acd9c745
ms.sourcegitcommit: eef26de3d7a5c971baedbecf3b4941fb683ddb2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81544293"
---
# <a name="javascript-and-typescript-in-visual-studio-2019"></a>JavaScript и TypeScript в Visual Studio 2019

## <a name="overview"></a>Обзор

Visual Studio 2019 предоставляет обширную поддержку для разработки JavaScript, как с помощью прямого использования JavaScript, также и с помощью [языка программирования TypeScript](http://www.typescriptlang.org/), который был разработан с целью повышения продуктивности и интереса во время разработки на JavaScript, особенно при разработке масштабных проектов. Код JavaScript или TypeScript в Visual Studio можно написать для многих типов приложений и служб.

## <a name="javascript-language-service"></a>Служба языка JavaScript

Опыт работы с JavaScript в Visual Studio 2019 обеспечивается тем же обработчиком, что и поддержка TypeScript. Это позволяет улучшить поддержку компонентов, функциональность и интеграцию сразу в готовом виде.

Функция восстановления устаревшей языковой службы JavaScript более не доступна. Теперь пользователи сразу получают новую языковую службу JavaScript. Новая языковая служба основана исключительно на языковой службе TypeScript, которая базируется на статическом анализе. Это позволяет нам оптимизировать инструментарий, поэтому ваш код на JavaScript может использовать преимущества расширенной поддержки IntelliSense на основе определений типов. Новая служба имеет небольшой размер и использует меньше памяти, чем устаревшие службы, обеспечивая более высокую производительность пользовательского кода по мере его масштабирования. Также мы улучшили производительность языковой службы для обработки более крупных проектов.

## <a name="typescript-support"></a>Поддержка TypeScript

Visual Studio 2019 предоставляет несколько вариантов для интеграции компиляции TypeScript в проект.

* [Пакет NuGet для TypeScript](https://www.nuget.org/packages/Microsoft.TypeScript.MSBuild). Когда в проект устанавливается пакет NuGet или TypeScript 3.2 или более новой версии, в редактор загружается соответствующая версия языковой службы TypeScript.
* [Пакет npm TypeScript](https://www.npmjs.com/package/typescript). Когда в проект устанавливается пакет npm или TypeScript 2.1 или более новой версии, в редактор загружается соответствующая версия языковой службы TypeScript.
* Также как и стандартный SDK, который можно скачать из [VS Marketplace](https://marketplace.visualstudio.com/items?itemName=TypeScriptTeam.typescript-331-vs2017), TypeScript SDK доступен в установщике Visual Studio по умолчанию.

> [!TIP]
> Для проектов, которые разработаны в Visual Studio 2019, рекомендуется использовать пакеты TypeScript NuGet и TypeScript npm. Они обеспечивают лучшую портативность в различных средах и платформах.

Чаще всего пакеты NuGet используются для компиляции TypeScript с помощью .NET Core CLI. Пока файл проекта не будет вручную изменен для импорта целевых объектов сборки из установки TypeScript SDK, пакет NuGet останется единственным способом включения компиляции TypeScript с помощью команд .NET Core CLI, таких как `dotnet build` и `dotnet publish`.

## <a name="remove-default-imports-aspnet-core-projects"></a>Удаление импортов по умолчанию (проекты ASP.NET Core)

В старых проектах, где используется [формат не в стиле SDK](https://docs.microsoft.com/nuget/resources/check-project-format), может потребоваться удалить некоторые элементы файла проекта.

Если вы используете пакет NuGet для поддержки MSBuild в проекте, файл проекта не должен импортировать `Microsoft.TypeScript.Default.props` или `Microsoft.TypeScript.targets`. Файлы импортируются пакетом NuGet, поэтому их отдельное включение может привести к непредвиденным последствиям.

1. Щелкните проект правой кнопкой мыши и выберите пункт **Выгрузить проект**.

1. Щелкните проект правой кнопкой мыши и выберите **Изменить \<*имя файла проекта*\>** .

   Откроется файл проекта.

1. Удалите ссылки на `Microsoft.TypeScript.Default.props` и `Microsoft.TypeScript.targets`.

   Удаляемые импорты имеют примерно следующий вид:

   ```xml
   <Import
      Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)\TypeScript\Microsoft.TypeScript.Default.props"
      Condition="Exists('$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)\TypeScript\Microsoft.TypeScript.Default.props')" />

   <Import
      Project="$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)\TypeScript\Microsoft.TypeScript.targets"
      Condition="Exists('$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)\TypeScript\Microsoft.TypeScript.targets')" />
   ```

## <a name="projects"></a>Проекты

Приложения UWP на JavaScript больше не поддерживаются в Visual Studio 2019. Невозможно создать или открыть проекты UWP на JavaScript (файлы с расширением *JSPROJ*). Дополнительные сведения см. в [документации по созданию прогрессивных веб-приложений (PWA), эффективно работающих на Windows](/microsoft-edge/progressive-web-apps/get-started).
