---
title: Запустите сеанс отладки для приложений магазина (JavaScript) Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: fb91203f-2cf4-44d3-8ed9-93bc5aaa50b8
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4b4e861c8985ee37a8c2d9b7f9286d6284bb4f91
ms.sourcegitcommit: 95f26af1da51d4c83ae78adcb7372b32364d8a2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2020
ms.locfileid: "79301383"
---
# <a name="start-a-debugging-session-for-store-apps-in-visual-studio-javascript"></a>Запуск сеанса отладки для приложений Магазина в Visual Studio (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Применяется к Windows и Windows Phone (. /Изображение/windows_and_phone_content.png "windows_and_phone_content")

 В этом разделе описывается запуск сеанса отладки приложений Магазина Windows, написанных на JavaScript и HTML5. Вы можете начать отладку одним нажатием или настроить сеанс отладки под конкретные сценарии, а затем выбрать способ запуска приложения.

> [!NOTE]
> Для приложений, написанных в XAML и Visual C, Visual C, или Visual Basic, [см. Начало сеанса отладки (VB, C, C и XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)

## <a name="in-this-topic"></a><a name="BKMK_In_this_topic"></a>В этой теме
 [В этой теме](#BKMK_In_this_topic)

 [Простой способ запуска отладки](#BKMK_The_easy_way_to_start_debugging)

 [Настройка сеанса отладки](#BKMK_Configure_the_debugging_session)

- [Откройте страницу свойств отладки для данного проекта.](#BKMK_Open_the_debugging_property_page_for_the_project)

- [Выберите параметры конфигурации сборки](#BKMK_Choose_the_build_configuration_options)

- [Выберите цель развертывания](#BKMK_Choose_the_deployment_target)

- [Выберите отладчик для использования](#BKMK_Choose_the_debugger_to_use)

- [(Необязательно) Задержка запуска приложения в сеансе отладки](#BKMK__Optional__Delay_starting_app_in_the_debug_session)

- [(Необязательно) Отключите сетевое замыкание на себя](#BKMK__Optional__Disable_network_loopbacks)

  [Запуск сеанса отладки](#BKMK_Start_the_debugging_session)

- [Начало отладки (F5)](#BKMK_Start_debugging__F5_)

- [Начать отладку (F5), но отложить запуск приложения](#BKMK_Start_debugging__F5__but_delay_the_app_start)

  [Запуск установленного приложения в отладчике](#BKMK_Start_an_installed_app_in_the_debugger)

  [Прикрепите отладчик к запущенному приложению](#BKMK_Attach_the_debugger_to_a_running_app_)

- [Установите приложение для запуска в режиме отладки](#BKMK_Set_the_app_to_run_in_debug_mode)

- [Подключение отладчика](#BKMK_Attach_the_debugger)

## <a name="the-easy-way-to-start-debugging"></a><a name="BKMK_The_easy_way_to_start_debugging"></a>Простой способ начать отладку
 ![Применимо только к Windows](../debugger/media/windows-only-content.png "windows_only_content")

1. Откройте приложение в Visual Studio.

2. Если решение содержит проекты как для приложений Магазина Windows, так и для приложений Магазина Windows Phone, убедитесь, что проект, отладку которого вы хотите выполнить, является запускаемым. В Solution Explore выберите проект, а затем выберите **Set as StartUp Project** из контекстного меню.

3. Нажмите клавишу F5.

   ![Применимо только к Windows Phone](../debugger/media/phone-only-content.png "phone_only_content")

   Visual Studio создает и запускает приложение с прикрепленным отладчиком. Выполнение продолжается до достижения точки останова, приостановления выполнения вручную, необработанного исключения или завершения приложения. Для получения дополнительной информации [см.](../debugger/quickstart-debug-html-and-css.md)

## <a name="configure-the-debugging-session"></a><a name="BKMK_Configure_the_debugging_session"></a>Настройка сеанса отладки
 Поскольку скрипт не компилируется, конфигурация сборки и параметры платформы не применяются. Если вы отлажаете компонент C-е или управляемый компонент, установите **конфигурацию** для **оттачки** и выберите целевую платформу из диалога **Configuration.**

### <a name="open-the-debugging-property-page-for-the-project"></a><a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>Откройте страницу отладки свойств для проекта

1. В обозревателе решений выберите проект. В контекстном меню выберите **Свойства**.

2. Расширьте узлы **свойств конфигурации,** а затем выберите **отладку**

### <a name="choose-the-build-configuration-options"></a><a name="BKMK_Choose_the_build_configuration_options"></a> Выберите параметры конфигурации построения

1. В списке **Конфигурация** выберите **Отладка** или **(Активный) Debug**.

2. В списке **Платформа** выберите целевую платформу для построения. В большинстве **случаев, любой процессор** является лучшим выбором.

### <a name="choose-the-deployment-target"></a><a name="BKMK_Choose_the_deployment_target"></a> Выберите целевой объект развертывания
 Можно развернуть и отладить приложение на компьютере с Visual Studio, в симуляторе Visual Studio на локальном компьютере или на удаленном компьютере. Вы выбираете цель из **Debugger для запуска** списка на странице свойств **debugging** для проекта.

 ![Применимо только к Windows](../debugger/media/windows-only-content.png "windows_only_content")

 Для приложения Магазина Windows выберите один из этих вариантов из списка **целевых устройств:**

|||
|-|-|
|**Местная машина**|Отладка приложения в текущем сеансе на локальном компьютере. Смотрите [приложения Run Windows Store на локальной машине.](../debugger/run-windows-store-apps-on-the-local-machine.md)|
|**Симулятор**|Отладка приложения в имитаторе Visual Studio для приложений [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] . Имитатор представляет собой окно на рабочем столе, которое позволяет отлаживать недоступные на локальном компьютере функциональные возможности устройства, такие как сенсорный ввод и поворот устройства. Смотрите [приложения Run Windows Store в симуляторе.](../debugger/run-windows-store-apps-in-the-simulator.md)|
|**Удаленная машина**|Отладка приложения на устройстве, подключенном к локальному компьютеру по интрасети или подсоединенном с помощью кабеля Ethernet напрямую. Для удаленной отладки на удаленном устройстве должны быть установлены и запущены удаленные средства Visual Studio. Смотрите [приложения Run Windows Store на удаленной машине.](../debugger/run-windows-store-apps-on-a-remote-machine.md)|

 При выборе пункта **Удаленный компьютер**укажите имя или IP-адрес удаленного компьютера одним из следующих способов.

- Введите имя или IP-адрес удаленной машины в коробке **Сименом Машины.**

- Выберите вниз стрелка в поле **имя машины** и выбрать ** \<Найти ... >**. Затем выберите пульт дистанционного управления из окна диалога **Select Remote Debugger Connection.**

   ![Выбор подключения к удаленному отладчику](../debugger/media/vsrun-pro-selectremotedebuggerdlg.png "VSRUN_PRO_SelectRemoteDebuggerDlg")

  > [!NOTE]
  > В диалоговом окне "Выбрать подключение к удаленному отладчику" отображаются компьютеры в локальной подсети и компьютеры, непосредственно подключенные к компьютеру Visual Studio с помощью кабеля Ethernet. Чтобы указать другой компьютер, введите имя в поле **Имя компьютера** .

  ![Применимо только к Windows Phone](../debugger/media/phone-only-content.png "phone_only_content")

  Для приложения Windows Store Phone выберите **устройство** или один из эмуляторов из списка **целевых устройств.**

### <a name="choose-the-debugger-to-use"></a><a name="BKMK_Choose_the_debugger_to_use"></a> Выбор отладчика
 По умолчанию отладчик вкладывается в код JavaScript в приложении. Вы можете выполнить отладку машинного кода C++ и управляемого кода компонентов приложения вместо кода JavaScript. Указать код для отладки можно в списке **Тип отладчика** на странице свойств **Отладка** проекта приложения.

 Выберите один из этих отладчиков из списка **типа Debugger:**

|||
|-|-|
|**Только скрипт**|Отладка кода JavaScript в приложении. Управляемый код и машинный код игнорируются.|
|**Только коренные**|Отладка машинного кода C/C++ в приложении. Управляемый код и код JavaScript игнорируются.|
|**Машинный код со скриптом**|Отладка машинного кода C++ и кода JavaScript в приложении.|
|**Только управляемый код**|Отладка управляемого кода в приложении. Код JavaScript и машинный код C/C++ игнорируются.|
|**Смешанный (управляемый и машинный)**|Отладка машинного кода C/C++ и управляемого кода в приложении. Код JavaScript игнорируется.|

### <a name="optional-delay-starting-the-app-in-the-debug-session"></a><a name="BKMK__Optional__Delay_starting_app_in_the_debug_session"></a>(Необязательно) Задержка запуска приложения в сеансе отладки
 По умолчанию Visual Studio немедленно запускает приложение при запуске отладки. Однако можно начать сеанс отладки, но отложить запуск приложения. Приложение открывается в отладчике при запуске приложения из меню "Пуск", по контракту активации или запуске другим процессом или методом. Вы также можете использовать отложенный запуск для отладки фоновых событий в приложении, которые должны возникать, пока приложение не выполняется.

 Вы указываете, следует ли отложить запуск приложения в списке **приложений запуска** на странице свойств **отладки** проекта приложения. Выберите один из следующих параметров.

- Выберите **Нет,** чтобы отсрочить запуск приложения.

- Выберите **Да,** чтобы запустить приложение немедленно.

### <a name="optional-disable-network-loopbacks"></a><a name="BKMK__Optional__Disable_network_loopbacks"></a>(Необязательно) Отключить сеть петлибэков
 ![Применимо только к Windows](../debugger/media/windows-only-content.png "windows_only_content")

 Из соображений безопасности приложению для Магазина Windows, установленному стандартным образом, не разрешается выполнять сетевые вызовы к устройству, на котором оно установлено. По умолчанию Visual Studio создает для развертываемого приложения исключение из этого правила. Это исключение позволяет тестировать процедуры обмена данными на одном компьютере. Прежде чем отправлять приложение в Магазин Windows, необходимо протестировать приложение без этого исключения.

 Чтобы удалить освобождение от возврата сетевого цикла, выберите **Нет** из списка **Loopback Allow Network** на странице свойств **debugging.**

## <a name="start-the-debugging-session"></a><a name="BKMK_Start_the_debugging_session"></a>Запуск сеанса отладки

### <a name="start-debugging-f5"></a><a name="BKMK_Start_debugging__F5_"></a> Начать отладку (F5)
 При выборе **start Debugging** в меню **Debug** (Keyboard: F5) Visual Studio запускает приложение с прикрепленным отладчиком. Выполнение продолжается до достижения точки останова, приостановления выполнения вручную, необработанного исключения или завершения приложения.

### <a name="start-debugging-f5-but-delay-the-app-start"></a><a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a>Начать отладку (F5), но отложить запуск приложения
 Приложение можно настроить для выполнения в режиме отладки, но запускать его нужно не отладчиком, а другим методом. Например, может потребоваться выполнить отладку запуска приложения из меню "Пуск" или отладку какого-либо фонового процесса в приложении без запуска приложения. Чтобы задержать запуск приложения, выполните следующие действия.

1. На странице **Debug** свойств проекта приложения выберите **Нет** из списка **приложений запуска.**

2. Выберите **«Старт отладку»** в меню **Debug** (клавиатура: F5).

3. Запустите приложение из меню "Пуск", по контракту исполнения или другой процедурой.

   Приложение запускается в режиме отладки. Выполнение продолжается до достижения точки останова, приостановления выполнения вручную, необработанного исключения или завершения приложения.

   . Для получения дополнительной информации об отладке фоновых задач см. [Триггер приостановить, резюме и фоновые события для Магазина Windows)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).

## <a name="start-an-installed-app-in-the-debugger"></a><a name="BKMK_Start_an_installed_app_in_the_debugger"></a> Запуск установленного приложения в отладчике
 При запуске отладки нажатием клавиши F5 Visual Studio выполняет построение приложения и развертывает его, настраивает приложение для выполнения в режиме отладки и затем запускает его. Чтобы запустить приложение, уже установленное на устройстве, используйте диалоговое окно "Отлаживать установленный пакет приложения". Эта процедура применима при необходимости выполнить отладку приложения, установленного из Магазина Windows, или при наличии исходных файлов для приложения, но отсутствии для него проекта Visual Studio. Например, установлена специальная система построений, в которой не используются проекты и решения Visual Studio.

 Приложение может быть установлено на локальном или удаленном устройстве.  Его можно запустить немедленно или настроить для выполнения в отладчике при запуске другим процессом или методом, например из меню "Пуск" или по контракту на активацию. Приложение также можно настроить для выполнения в режиме отладки, если требуется выполнить отладку какого-либо фонового процесса, не запуская приложение. Для получения дополнительной информации см. [Триггер приостановить, резюме и фоновые события для Магазина Windows) .](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)

 Чтобы настроить установленное приложение для выполнения в режиме отладки, выполните следующие действия.

> [!NOTE]
> В начале выполнения этой процедуры приложение не должно выполняться.

1. В меню **Отладка** выберите команду **Отладка Installed App Package**.

2. Выберите в списке один из следующих вариантов.

   |                    |                                                                                                                                                                                                                                                                                                                                                                                                           |
   |--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Местная машина**  |                                                                                                                Отладка приложения в текущем сеансе на локальном компьютере. Смотрите [приложения Run Windows Store на локальной машине.](../debugger/run-windows-store-apps-on-the-local-machine.md)                                                                                                                 |
   |   **Симулятор**    | Отладка приложения в имитаторе Visual Studio для приложений [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] . Имитатор представляет собой окно на рабочем столе, которое позволяет отлаживать недоступные на локальном компьютере функциональные возможности устройства, такие как сенсорный ввод и поворот устройства. Смотрите [приложения Run Windows Store в симуляторе.](../debugger/run-windows-store-apps-in-the-simulator.md) |
   | **Удаленная машина** |                          Отладка приложения на устройстве, подключенном к локальному компьютеру по интрасети или подсоединенном с помощью кабеля Ethernet напрямую. Для удаленной отладки на удаленном устройстве должны быть установлены и запущены удаленные средства Visual Studio. Смотрите [приложения Run Windows Store на удаленной машине.](../debugger/run-windows-store-apps-on-a-remote-machine.md)                           |

3. Выберите приложение в списке **Установленные пакеты приложений** .

4. Выберите подлежащий использованию модуль отладки в списке **Отлаживать этот тип кода** .

5. (необязательно). Выберите **Не запускать, а отлаживать мой код при открытии** , чтобы выполнить отладку приложения при его запуске некоторым другим методом или отладку фонового процесса.

   При щелчке **Запуск**приложение запускается или настраивается для выполнения в режиме отладки.

## <a name="attach-the-debugger-to-a-running-app"></a><a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> Подключение отладчика к выполняемому приложению
 Чтобы подключить отладчик к приложению [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] , нужно воспользоваться диспетчером отлаживаемых пакетов и настроить приложение на выполнение в режиме отладки. Диспетчер отлаживаемых пакетов устанавливается вместе с инструментами удаленной отладки Visual Studio.

 Подключение отладчика к приложению полезно, когда требуется отладить уже установленное приложение, например приложение, установленное из Магазина Windows. Подключение необходимо, когда имеются исходные файлы приложения, но отсутствует проект Visual Studio для приложения. Например, установлена специальная система построений, в которой не используются проекты и решения Visual Studio.

 Для вложения в приложение выполните следующие действия:

1. Настройте приложение для запуска в режиме отладки. Это нужно делать, когда приложение не выполняется.

2. Запустите приложение. Можно запустить приложение из меню "Пуск", по контракту исполнения или другим методом.

3. Подключите отладчик к выполняемому приложению.

### <a name="set-the-app-to-run-in-debug-mode"></a><a name="BKMK_Set_the_app_to_run_in_debug_mode"></a> Настройте приложение для запуска в режиме отладки.

1. Установите инструменты удаленной отладки Visual Studio на устройстве, на котором установлено приложение. Смотрите [Установка удаленных инструментов.](https://msdn.microsoft.com/library/windows/apps/hh441469.aspx#BKMK_Installing_the_Remote_Tools)

2. В меню "Пуск" найдите и запустите `Debuggable Package Manager`.

     Отобразится окно PowerShell, настроенное для работы с командлетами AppxDebug.

3. Чтобы включить отладку приложения, необходимо задать идентификатор приложения PackageFullName. Чтобы просмотреть список всех приложений с идентификатором PackageFullName, введите `Get-AppxPackage` в командной строке PowerShell.

4. В командной строке PowerShell введите `Enable-AppxDebug` *ПолноеИмяПакета* , где *ПолноеИмяПакета* — идентификатор "ПолноеИмяПакета" данного приложения.

### <a name="attach-the-debugger"></a><a name="BKMK_Attach_the_debugger"></a>Прикрепите отладчик

> [!TIP]
> Приложения JavaScript выполняются в экземпляре процесса wwahost.exe. Если при вложении в приложение выполняются другие приложения JavaScript, вам потребуется знать числовой идентификатор процесса того wwahost.exe, где выполняется приложение.
>
> Самый простой способ решения данной проблемы заключается в закрытии всех других приложений JavaScript. В противном случае вы можете открыть диспетчер задач Windows перед запуском приложения и записать идентификаторы процессов wwahost.exe. При указании процесса, который следует прикрепить к в диалоговом окне **доступных процессов,** wwahost.exe приложения будет иметь идентификатор, который отличается от тех, которые вы отметили.

 Чтобы подключить отладчик, выполните следующие действия.

1. В меню **Отладка** выберите пункт **Присоединение к процессу**.

    Откроется диалоговое окно **Присоединение к процессу** .

2. Чтобы подключить отладчик к приложению на удаленном устройстве, укажите это удаленное устройство в поле **Квалификатор** . Вы можете:

   - Введите имя в поле **Квалификатор** .

   - Выберите вниз стрелка в поле **квалификатора** и выберите устройство из списка устройств, которые вы прикрепили к ранее.

   - Выберите **«Найти»** устройство из списка устройств в локальной подсети.

3. Укажите тип кода, который нужно отладить, в поле **Присоединить к** .

    Щелкните **Выбрать** и выполните одно из следующих действий.

   - Щелкните **Автоматически определять тип отлаживаемого кода**

   - Щелкните **Выполнять отладку кода следующих типов** и выберите один или несколько типов из списка.

4. В списке **доступных процессов** выберите подходящий процесс **wwahost.exe.** Используйте столбец **"Заголовок"** для идентификации приложения.

5. Выберите **Присоединиться**.

   Visual Studio подключает отладчик к процессу. Выполнение продолжается до достижения точки останова, приостановления выполнения вручную, необработанного исключения или завершения приложения.

## <a name="see-also"></a>См. также:
 [Управление выполнением в сеансе отладки (JavaScript)](../debugger/control-execution-of-a-store-app-in-a-visual-studio-debug-session-for-windows-store-apps-javascript.md) [Быстрый запуск: отладка HTML и CSS](../debugger/quickstart-debug-html-and-css.md) [Триггер приостановить, резюме и фоновые события для Магазина Windows)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md) [Отожобляты приложений в Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)
