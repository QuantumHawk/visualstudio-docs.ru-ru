---
title: Установка Visual Studio для Mac 2019
description: Инструкции по установке Visual Studio 2019 для Mac и дополнительных компонентов, которые требуются для кроссплатформенной разработки.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 09/18/2019
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.custom: video
ms.openlocfilehash: 45f9756607cbb638d1f69f77bdf8cd2ee30953c5
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2020
ms.locfileid: "75851941"
---
# <a name="install-visual-studio-2019-for-mac"></a>Установка Visual Studio для Mac 2019

Чтобы приступить к разработке собственных кроссплатформенных приложений .NET в macOS, установите Visual Studio 2019 для Mac. Для этого выполните следующие действия.

 > [!div class="button"]
 > [Скачать Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/)

## <a name="requirements"></a>Требования

- Компьютер Mac с macOS High Sierra 10.12 или более поздней версии.

Чтобы создавать приложения Xamarin для iOS или macOS, вам также потребуется:

- Xcode 10.0 или более поздней версии. Обычно рекомендуется использовать последнюю стабильную версию.
- Идентификатор Apple ID. Если у вас нет идентификатора Apple ID, его можно создать на сайте https://appleid.apple.com. Он необходим для установки приложения Xcode и входа в него.

## <a name="installation-instructions"></a>Инструкции по установке

1. Скачайте установщик со [страницы загрузки Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/).
2. После завершения загрузки щелкните **VisualStudioforMacInstaller.dmg**, чтобы подключить установщик, и запустите его, дважды щелкнув значок стрелки:

    [![Щелкните большую стрелку, чтобы начать установку](media/install-installer-sml.png)](media/install-installer.png#lightbox)

3. Может появиться окно с предупреждением о том, что приложение загружено из Интернета. Нажмите кнопку **Открыть**.
4. Подождите, пока программа установки проверяет компьютер:

    [![Установщик проверяет установленные в системе компоненты](media/install-checking-sml.png)](media/install-checking.png#lightbox)

5. Появится оповещение, предлагающее принять условия лицензии и заявления о конфиденциальности. Перейдите по ссылкам, чтобы ознакомиться с ними, а затем нажмите клавишу **Продолжить**, если вы согласны с условиями:

    [![Перейдите по ссылкам на заявление о конфиденциальности и условия лицензии, а затем продолжите установку, если вы согласны](media/install-privacy.png)](media/install-privacy.png#lightbox)

6. Появится список доступных рабочих нагрузок. Выберите нужные компоненты:

    [![Выберите, какие дополнительные функции рабочей нагрузки вы хотите установить](media/install-selection.png)](media/install-selection.png#lightbox)

   Если вы не хотите устанавливать все платформы, выберите нужные с помощью приведенных ниже рекомендаций.


|Тип приложения  |Назначение  |Выбор  |Примечания  |
|---------|---------|---------|---------|
|**Приложения, использующие Xamarin**| Xamarin.Forms|Выберите платформы **Android** и **iOS**. |Потребуется установить [**Xcode**](https://developer.apple.com/xcode/). |
||Только iOS|Выберите платформу **iOS**.|Потребуется установить [**Xcode**](https://developer.apple.com/xcode/).|
||Только Android|Выберите платформу **Android**.|Обратите внимание, что вам также нужно выбрать соответствующие зависимости.|
||Только Mac|Выберите платформу **macOS (Cocoa)** .|Потребуется установить [**Xcode**](https://developer.apple.com/xcode/).|
|**Приложения .NET Core**|         |Выберите платформу **.NET Core**.|         |
|**Веб-приложения ASP.NET Core**|         |Выберите платформу **.NET Core**.|         |
|**Функции Azure**|         |Выберите платформу **.NET Core**.|         |
|**Разработка кроссплатформенных игр Unity**|         |Не нужно устанавливать дополнительные платформы, кроме Visual Studio для Mac.| Дополнительные сведения об установке расширения Unity вы найдете в [руководстве по установке Unity](/visualstudio/mac/setup-vsmac-tools-unity).|


7. Выбрав нужные параметры, нажмите кнопку **Установить**.
8. Установщик будет отображать ход выполнения, по мере загрузки и установки Visual Studio для Mac и выбранных рабочих нагрузок. Вам будет предложено ввести пароль, чтобы предоставить привилегии, необходимые для установки.

    [![Выберите, какие дополнительные функции рабочей нагрузки вы хотите установить](media/installation-progress.png)](media/installation-progress.png#lightbox)

9. После установки Visual Studio для Mac предложит настроить личные параметры, выполнив вход и выбрав нужные настраиваемые сочетания клавиш.

    [![Войдите в интегрированную среду разработки](media/ide-tour-2019-start-signin.png)](media/ide-tour-2019-start-signin.png#lightbox)

    [![Выберите, какие сочетания клавиш вы хотите использовать](media/ide-tour-2019-keyboard-shortcut.png)](media/ide-tour-2019-keyboard-shortcut.png#lightbox)

Если при установке в корпоративной среде возникают проблемы с сетью, см. инструкции по [установке за брандмауэром или прокси-сервером](/visualstudio/mac/installation#install-visual-studio-for-mac-behind-a-firewall-or-proxy-server).

Сведения об изменениях см. в [заметках о выпуске](/visualstudio/releasenotes/vs2019-mac-relnotes).

> [!NOTE]
> Если вы решили не устанавливать платформу или инструмент в рамках исходной установки (отменив выбор этого элемента на шаге 6), позже для установки этих компонентов потребуется снова запустить установщик.

## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Установка Visual Studio для Mac в среде, защищенной брандмауэром или прокси-сервером

Для установки Visual Studio для Mac в среде, защищенной брандмауэром, необходимо сделать доступными ряд конечных точек, чтобы разрешить скачивание необходимых средств и обновлений ПО.

Настройте сеть, разрешив доступ к следующим расположениям:

- [Конечные точки Visual Studio](/visualstudio/mac/install-behind-a-firewall-or-proxy-server)

## <a name="next-steps"></a>Дальнейшие действия

Установка Visual Studio для Mac позволяет перейти к написанию кода для приложений. Следующие руководства помогут вам в создании и развертывании проектов.

### <a name="ios"></a>iOS

1. [Привет, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)
2. [Подготовка устройства](https://developer.xamarin.com/guides/ios/getting_started/installation/device_provisioning) (для запуска приложения на устройстве).

### <a name="android"></a>Android

1. [Использование диспетчера пакетов SDK Android для Xamarin](https://developer.xamarin.com/guides/android/getting_started/installation/android-sdk/?ide=xs)
2. [Эмулятор SDK для Android](https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/)
4. [Настройка устройства для разработки](https://developer.xamarin.com/guides/android/getting_started/installation/set_up_device_for_development/)

### <a name="net-core-apps-aspnet-core-web-apps-unity-game-development"></a>Приложения .NET Core, веб-приложения ASP.NET Core, разработка игр Unity

Другие рабочие нагрузки описаны [на этой странице](workloads.md).

## <a name="related-video"></a>Связанные видео

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Acquisition/player]

## <a name="see-also"></a>См. также раздел

- [Установка Visual Studio (в Windows)](/visualstudio/install/install-visual-studio)
