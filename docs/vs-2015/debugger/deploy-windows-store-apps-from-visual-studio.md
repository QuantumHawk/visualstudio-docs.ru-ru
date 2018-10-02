---
title: Развертывание приложений Windows Store из Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: ef3a0f36-bfc9-4ca0-aa61-18261f619bff
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1212665b8e7e1c28fa30f50c1cd64a0dc5c217bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47562187"
---
# <a name="deploy-windows-store-apps-from-visual-studio"></a>Развертывание приложений для Магазина Windows из Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [развернуть Windows Store apps из Visual Studio](https://docs.microsoft.com/visualstudio/debugger/deploy-windows-store-apps-from-visual-studio).  
  
Применяется только к Windows] (.. /Image/windows_only_content.PNG «windows_only_content»)  
  
 Функциональность развертывания Visual Studio выполняет сборку и регистрацию приложений Магазина Windows, созданных с помощью Visual Studio на целевом устройстве. Конкретный способ регистрации зависит от того, является ли целевое устройство локальным или удаленным:  
  
-   Когда целевое устройство является локальным компьютером Visual Studio, Visual Studio регистрирует приложение из папки сборки.  
  
-   Когда целевое устройство является удаленным, Visual Studio копирует требуемые файлы на удаленный компьютер и регистрирует приложение на этом устройстве.  
  
 Развертывание осуществляется автоматически при отладке приложения из Visual Studio с помощью **начать отладку** параметр (Клавиатура: F5) или **Запуск без отладки** параметр (Клавиатура: CTRL + F5). Кроме того, приложение можно развернуть вручную. Это удобно в следующих сценариях:  
  
-   Специализированное тестирование на локальном или удаленном компьютере.  
  
-   Развертывание приложения, запускающего другое приложение, которое требует отладки.  
  
-   Развертывание приложения, для которого будет выполнена отладка, при его запуске другим приложением или методом.  
  
##  <a name="BKMK_In_this_topic"></a> Содержание раздела  
 В этом разделе приведены следующие сведения:  
  
 [Развертывание приложения Магазина Windows](#BKMK_How_to_deploy_a_Windows_Store_app)  
  
 [Указание удаленного устройства](#BKMK_How_to_specify_a_remote_device)  
  
 [Параметры развертывания](#BKMK_Deployment_options)  
  
##  <a name="BKMK_How_to_deploy_a_Windows_Store_app"></a> Развертывание приложения Магазина Windows  
 Ручное развертывание приложения не вызывает никаких сложностей:  
  
1.  Если вы выполняете развертывание на удаленное устройство, укажите имя или IP-адрес устройства на странице свойств для запускаемого проекта приложения. (Необходимые для этого действия перечислены ниже в этом разделе.)  
  
2.  На панели инструментов отладчика Visual Studio выберите цель развертывания в раскрывающемся списке рядом с кнопкой **Начать отладку** .  
  
     ![Запуск на локальном компьютере](../debugger/media/vsrun-f5-local.png "VSRUN_F5_Local")  
  
3.  В меню **Сборка** выберите пункт **Развернуть**.  
  
##  <a name="BKMK_How_to_specify_a_remote_device"></a> Указание удаленного устройства  
 **Предварительные требования**  
  
 Для развертывания приложения на удаленном устройстве выполните следующие действия:  
  
-   На удаленном устройстве должна быть установлена лицензия разработчика.  
  
-   На удаленном устройстве должны быть установлены инструменты удаленной отладки для Visual Studio, а также должен быть запущен монитор удаленной отладки.  
  
     Развертывание использует канал сети удаленного отладчика для отправки файлов приложения на удаленное устройство.  
  
#### <a name="to-specify-a-remote-device"></a>Порядок указания удаленного устройства  
  
1.  На странице свойств "Отладка" запускаемого проекта укажите имя или IP-адрес удаленной цели развертывания.  
  
2.  Чтобы открыть страницу свойств "Отладка", выберите проект в обозревателе решений и щелкните пункт **Свойства** в контекстном меню.  
  
3.  После этого выберите узел **Отладка** в окне страниц свойств.  
  
4.  Можно ввести сетевое имя или IP-адрес удаленного устройства или выбрать его в диалоговом окне **Выбрать подключение к удаленному отладчику** .  
  
     ![Выберите диалоговое окно подключения к удаленному отладчику](../debugger/media/vsrun-selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
     В диалоговом окне **Выбрать подключение к удаленному отладчику** отображаются устройства в локальной подсети и устройства, непосредственно подключенные к компьютеру Visual Studio с помощью кабеля Ethernet.  
  
 **Указание удаленного устройства на странице проекта JavaScript или Visual C++**  
  
 ![C&#43; &#43; свойства для удаленной отладки проекта](../debugger/media/vsrun-cpp-projprop-remote.png "VSRUN_CPP_ProjProp_Remote")  
  
1.  Выберите **Удаленный отладчик** из списка **Отладчик для запуска** .  
  
2.  Введите имя сети для удаленного устройства в поле **Имя компьютера** . Либо вы можете выбрать стрелку вниз в поле, чтобы выбрать устройство в диалоговом окне "Выбрать подключение к удаленному отладчику".  
  
 **Указание удаленного устройства на странице проекта Visual C# или Visual Basic**  
  
 ![Свойства управляемого проекта для удаленной отладки](../debugger/media/vsrun-managed-projprop-remote.png "VSRUN_Managed_ProjProp_Remote")  
  
1.  Выберите **Удаленный компьютер** из списка **Целевое устройство** .  
  
2.  Введите сетевое имя удаленного устройства в поле **Удаленный компьютер** или щелкните **Найти** , чтобы выбрать устройство в диалоговом окне **Выбрать подключение к удаленному отладчику** .  
  
##  <a name="BKMK_Deployment_options"></a> Параметры развертывания  
 Вы можете задать следующие параметры развертывания на странице свойств "Отладка" запускаемого проекта.  
  
 **Разрешить замыкание на себя в локальной сети**  
 Из соображений безопасности приложению [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)], установленному стандартным образом, не разрешается выполнять сетевые вызовы к устройству, на котором оно установлено. По умолчанию Visual Studio создает для развертываемого приложения исключение из этого правила. Это исключение позволяет тестировать процедуры обмена данными на одном компьютере. Прежде чем отправлять приложение в [!INCLUDE[win8_appstore_long](../includes/win8-appstore-long-md.md)], необходимо протестировать приложение без этого исключения.  
  
 Чтобы удалить исключение сетевого замыкания на себя из приложения, выполните следующие действия:  
  
-   На странице свойств "Отладка" для C# и VB снимите флажок **Разрешить замыкание на себя в локальной сети** .  
  
-   На странице свойств "Отладка" для JavaScript установите для параметра **Разрешить замыкание на себя в локальной сети** значение **Нет**.  
  
 **"Не запускать, а отлаживать мой код при открытии" (C# и VB)/"Запустить приложение" (JavaScript и C++)**  
 Чтобы настроить развертывание на автоматический запуск сеанса отладки при запуске приложения, выполните следующие действия:  
  
-   На странице свойств "Отладка" для C# и VB установите флажок **Не запускать, а отлаживать мой код при открытии** .  
  
-   На странице свойств "Отладка" для JavaScript установите для параметра **Запустить приложение** значение **Да**.  
  
## <a name="see-also"></a>См. также  
 [Запуск приложения из Visual Studio](../debugger/run-store-apps-from-visual-studio.md)


