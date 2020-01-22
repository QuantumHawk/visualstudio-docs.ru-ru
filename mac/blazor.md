---
title: Создание веб-приложений Blazor
description: Эта статья содержит сведения о поддержке Blazor в приложениях ASP.NET Core в Visual Studio для Mac.
author: jongalloway
ms.author: jogallow
ms.date: 12/17/2019
ms.technology: vs-ide-general
ms.assetid: D2717D3A-9225-40A8-8155-7D0143B2CA60
ms.openlocfilehash: dbc49a0ea9b4e4fa7880b6226331d447339b6575
ms.sourcegitcommit: d04441e3c5f2eff3a63f7aca35ccf7ecac90fb44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75737303"
---
# <a name="create-blazor-web-apps"></a>Создание веб-приложений Blazor

Из этого руководства вы узнаете, как создать свое первое веб-приложение Blazor. Более подробные инструкции см. в статье [Введение в ASP.NET Core Blazor](/aspnet/core/blazor/index).

Visual Studio для Mac (начиная с версии 8.4) включает поддержку разработки и публикации серверных приложений Blazor ASP.NET Core. Blazor — это платформа для создания интерактивных клиентских веб-интерфейсов на основе .NET, которые предоставляют для веб-разработчиков следующие преимущества:

* создавайте код на C#, а не на JavaScript.
* возможность использования существующей экосистемы .NET с библиотеками .NET;
* сохранение единой логики приложений для сервера и клиента;
* высокая производительность, надежность и безопасность платформы .NET;
* возможность сохранения высокого уровня продуктивности с помощью Visual Studio в Windows, Linux и macOS;
* создавайте приложения на основе распространенных языков, платформ и инструментов, которые отличаются стабильностью, широким набором функций и простотой в использовании.

## <a name="creating-a-new-blazor-project"></a>Создание проекта Blazor

1. В **окне запуска** выберите **Новый**, чтобы создать проект:

   ![Окно запуска Visual Studio для Mac с выделенным параметром "Создать"](media/blazor-new-project.png)
1. В диалоговом окне **Новый проект** выберите **.NET Core** > **Приложение** > **Серверное приложение Blazor**, а затем — **Далее**. ![Диалоговое окно "Выберите шаблон из нового проекта" с выбранным шаблоном серверного приложения Blazor](media/blazor-project-template.png)

1. Выберите .NET Core 3.1 в качестве целевой платформы, а затем нажмите кнопку **Далее**. 
   ![Диалоговое окно настройки нового серверного приложения Blazor с выбранной целевой платформой для .NET Core 3.1](media/blazor-select-target-framework.png)

1. Выберите имя проекта и при необходимости добавьте поддержку Git. Выберите **Создать**, чтобы создать проект.
   ![Диалоговое окно настройки нового серверного приложения Blazor, отображаемое при вводе имени проекта](media/blazor-name-project.png)

   Visual Studio для Mac откроет проект в окне макета с кодом.
1. Выберите **Выполнить** > **Запуск без отладки**, чтобы запустить приложение.

   Visual Studio запустит [Kestral](/aspnet/core/fundamentals/servers/kestrel), откроет в браузере адрес `https://localhost:5001` и отобразит ваше веб-приложение Blazor.

   ![Веб-приложение Blazor в Safari](media/blazor-new-app-in-edge.png)

## <a name="blazor-support-in-visual-studio-for-mac"></a>Поддержка Blazor в Visual Studio для Mac

Приложение Visual Studio для Mac (начиная с версии 8.4) включает новые функции для создания серверных проектов Blazor. Кроме того, оно предоставляет стандартную поддержку, необходимую для создания, запуска и отладки проектов Blazor. 

В приведенном выше пошаговом руководстве мы узнали, как шаблон проекта серверного приложения Blazor помогает создать проект серверного приложения Blazor. Рассмотрим некоторые дополнительные функции Visual Studio для Mac для поддержки разработки серверных проектов Blazor.

### <a name="editor-support-for-razor-files"></a>Поддержка редактора *RAZOR*-файлов
Visual Studio для Mac включает поддержку редактирования RAZOR-файлов (большинство файлов, которые будут использоваться при создании приложений Blazor). Версия интегрированной среды разработки для Windows и Mac имеет тот же редактор для RAZOR-файлов. Вы увидите полную поддержку раскраски и завершения RAZOR-файлов, включая завершения для компонентов Razor, объявленных в проекте.

![Окно редактора Visual Studio для Mac с Intellisense для Blazor](media/blazor-intellisense.png)

### <a name="publishing-blazor-applications-to-azure-app-service"></a>Публикация приложений Blazor в службе приложений Azure
Вы также можете опубликовать приложения Blazor непосредственно в службе приложений Azure. Если у вас нет учетной записи Azure для запуска приложения Blazor, вы можете [бесплатно зарегистрироваться](https://azure.microsoft.com/free) и использовать популярные службы в течение 12 месяцев. Вы также получите 200 долл. США на счет и возможность бесплатно работать с более чем 25 службами.

![Диалоговое окно Visual Studio для Mac с параметром публикации в Azure](media/blazor-azure-publish.png)

## <a name="project-anatomy"></a>Структура проекта

По умолчанию веб-приложения Blazor содержат несколько каталогов и файлов. Перед началом работы необходимо ознакомиться с основными из них.

### <a name="pages-folder"></a>Папка Pages

Эта папка содержит веб-страницы проекта с расширением файла *RAZOR*.

### <a name="shared-folder"></a>Папка Shared

Эта папка содержит общие компоненты с расширением *RAZOR*. Сюда входит файл *MainLayout.razor*, который используется для определения общих макетов в приложении. Она также содержит компонент *NavMenu.razor*, используемый на всех страницах. Если вы создаете многократно используемые компоненты, они попадут в папку **Shared**.

### <a name="app-settings"></a>Параметры приложения

Файл *appSettings.json* содержит данные конфигурации, например строки подключения.

Дополнительные сведения о конфигурации см. в статье [Конфигурация в ASP.NET](/aspnet/core/fundamentals/configuration/index).

### <a name="wwwroot-folder"></a>Папка wwwroot

Эта папка содержит статические файлы, такие как HTML-файлы, файлы JavaScript и CSS-файлы. Подробные сведения см. в статье [Статические файлы в ASP.NET Core](/aspnet/core/fundamentals/static-files).

### <a name="programcs"></a>Program.cs

Этот файл содержит точку входа для программы. Подробные сведения см. в статье [Веб-узел ASP.NET Core](/aspnet/core/fundamentals/host/web-host).

### <a name="startupcs"></a>Startup.cs

Этот файл содержит код, который настраивает поведение приложения, например требуется ли согласие для файлов cookie. Подробные сведения см. в статье [Запуск приложения в ASP.NET Core](/aspnet/core/fundamentals/startup).

## <a name="summary"></a>Сводка
Из этого руководства вы узнали, как создать серверное приложение Blazor в Visual Studio для Mac и получили сведения о некоторых функциях Visual Studio для Mac для создания этих приложений.

## <a name="see-also"></a>См. также

Подробное руководство по созданию веб-приложений Blazor см. в статье [Введение в ASP.NET Core Blazor](/aspnet/core/blazor/index).