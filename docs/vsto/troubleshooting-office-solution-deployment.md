---
title: Развертывание решения Troubleshoot Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], troubleshooting
- Office development in Visual Studio, troubleshooting
- deploying applications [Office development in Visual Studio], troubleshooting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: de036ce9b0b566a6028b0ccfe45cfe5f2ac49da9
ms.sourcegitcommit: 7b60e81414a82c6d34f6de1a1f56115c9cd26943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81444938"
---
# <a name="troubleshoot-office-solution-deployment"></a>Развертывание решения Troubleshoot Office
  В этом разделе содержатся сведения об устранении неполадок, которые могут возникнуть при развертывании решений Office.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

## <a name="troubleshoot-office-solutions-by-using-the-event-viewer"></a>Решения Troubleshoot Office с помощью просмотра событий
 Вы можете использовать средство просмотра событий в Windows для просмотра сообщений об ошибках, записанных средой выполнения [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] при установке или удалении решений Office. С помощью этих сообщений из журнала событий можно разрешать проблемы развертывания и установки. Для получения дополнительной [Event logging for Office solutions](../vsto/event-logging-for-office-solutions.md)информации см.

## <a name="change-the-assembly-name-causes-conflicts"></a>Изменение имени сборки вызывает конфликты
 Если вы измените значение **названия сборки** на странице **приложения** **конструктора проекта** после того, как вы уже развернули решение, инструменты публикации изменят пакет настройки, чтобы иметь один файл *Setup.exe* и два манифеста развертывания. При развертывании двух файлов манифеста могут возникнуть следующие обстоятельства.

- Если конечный пользователь установит обе версии, приложение будет загружать обе надстройки VSTO.

- Если надстройка VSTO была установлена до изменения имени сборки, конечный пользователь никогда не будет получать обновления.

  Чтобы избежать этих условий, не изменяйте значение **названия сборки** решения после развертывания решения.

## <a name="check-for-updates-takes-a-long-time"></a>Проверка обновлений занимает много времени
 Visual Studio 2010 Tools for Office runtime предоставляет запись в реестре, которую администраторы могут использовать для настройки значения тайм-аута для загрузки манифестов и решения.

#### <a name="to-set-the-time-out-value"></a>Установка значения времени ожидания.

1. В реестре перейдите в следующий раздел:

     **HKEY_CURRENT_USER\Software\Microsoft\VSTA**

2. В подразделе **AddInTimeout** задайте значение времени ожидания в миллисекундах.

     Если подраздел **AddInTimeout** не существует, создайте его как DWORD.

## <a name="cant-update-or-publish-to-a-network-file-share"></a>Не увозможность обновления или публикации в общий ряд сетевого файла
 Офисные решения, находящиеся в общих долях сетевого файла, могут отображать вводящее в заблуждение сообщение во время обновления, если файл *Setup.exe* решения заблокирован в процессе во время публикации обновления. Сообщение может говорить следующее: "Не удается добавить ’setup.exe’ на веб-сайт. Файл ’setup.exe’ уже существует на этом веб-сайте".

 Чтобы предотвратить блокировку файла, можно сделать этот файловый ресурс доступным конечным пользователям только для чтения. Однако если в этом файловом ресурсе имеются документы, они также становятся доступными конечным пользователям только для чтения.

## <a name="prerequisites-for-microsoft-office-arent-installed"></a>Предпосылки для Microsoft Office не установлены
 Вы можете добавить .NET Framework, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]и основные сборки взаимодействия Office в пакет установки в качестве необходимых компонентов, развертываемых вместе с решением Office. Для получения информации о том, как установить первичные межопом сборки, [см. Нанастройка компьютера для разработки решений Office](../vsto/configuring-a-computer-to-develop-office-solutions.md) и [Как: Установка Office первичных межопомнейных сборок](../vsto/how-to-install-office-primary-interop-assemblies.md).

## <a name="publish-using-localhost-can-cause-installation-problems"></a>Публикация с помощью Localhost может вызвать проблемы с установкой
 При использовании `http://localhost` в качестве места публикации или установки для решений уровня документа **мастер публикации** не преобразует строку в реальное имя компьютера. В таком случае необходимо установить решение на компьютере разработки. Чтобы развернутые решения могли использовать службы IIS на компьютере разработки, вместо localhost указывайте полное имя для всех расположений HTTP, HTTPS и FTP.

## <a name="cached-assemblies-are-loaded-instead-of-updated-assemblies"></a>Кэшированные сборки загружаются вместо обновленных сборок
 Fusion, загрузчик сборок .NET Framework, загружает кэшированную копию сборок, если выходной путь проекта указывает на сетевой файловый ресурс, сборка подписана строгим именем и версия сборки настройки не изменена. При обновлении сборки, которая удовлетворяет этим условиям, обновление не будет отображаться при следующем запуске проекта, поскольку будет загружена кэшированная копия.

 Вы можете настроить Visual Studio так, чтобы Fusion загружал сборки при каждом запуске проекта.

### <a name="to-download-assemblies-instead-of-loading-cached-copies"></a>Загрузка сборок вместо загрузки кэшированных копий

1. В меню последовательно выберите **Проект**, _ProjectName_**Свойства**.

2. На странице **Приложения** выберите **Сведения о сборке**.

3. Установите номер пересмотра, третье поле, **версии Собрания**\*, на wild card (). Например, "1,0".  Затем выберите кнопку **OK.**

   После изменения версии сборки вы можете продолжить подписывать сборку строгим именем, и Fusion будет загружать последнюю версию настройки.

 [!NOTE]
> Начиная с Visual Studio 2017, если вы попытаетесь использовать дикие карты в версии сборки, произойдет ошибка сборки.  Это потому, что дикие карты в сборочной версии нарушит функцию MSBuild Deterministic. Вам будет поручено либо удалить подстановочные знаки из версии сборки, либо отключить детерминизм.  Чтобы узнать больше о функции Deterministic см.: [Общие свойства проекта MSBuild](../msbuild/common-msbuild-project-properties.md) и [настроить сборку](../msbuild/customize-your-build.md)

## <a name="installation-fails-when-the-uri-has-characters-that-arent-us-ascii"></a>Установка не удается, когда URI имеет символы, которые не ЯВЛЯЮТСЯ US-ASCII
 При публикации решения Office в расположении HTTP, HTTPS и FTP путь не может содержать какие-либо символы Юникода, не входящие в набор US-ASCII. Такие символы могут привести к непредсказуемому поведению программы установки. Используйте для пути установки только символы US-ASCII.

## <a name="prompt-to-manually-uninstall-appears-when-you-publish-and-install-a-solution-on-the-development-computer"></a>Быстрый ручной удалить появляется при публикации и установке решения на компьютере разработки
 При сборке решения Office версия сборки регистрируется автоматически. Если ранее вы опубликовали и установили то же решение на свой компьютер разработки, то после следующей сборки, перестроения или публикации решения среда выполнения [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] обнаруживает, что путь установки для опубликованной версии и версия сборки отличаются. Появляется сообщение об ошибке "Не удается установить настройку, поскольку уже установлена другая версия, обновление которой из этой папки невозможно". Разделы реестра обновляются при каждом перестроении решения. Таким образом, необходимо удалить предыдущую версию перед публикацией, отладкой или запуском новой версии.

 Чтобы предотвратить появление этого сообщения, создайте другую учетную запись пользователя на компьютере разработки для тестирования развертывания. Вы также можете удалить версию из списка программ, установленных на компьютере, перед следующей публикацией, отладкой или перестроением решения.

## <a name="uncaught-exception-or-method-not-found-error-when-you-install-a-solution"></a>Непойманное исключение или метод, не найденный ошибки при установке решения
 При установке решений Office, открывая манифест развертывания (файл *.vsto),* приложение Office, документ или трудовую книжку, могут отображаться сообщения об ошибках для следующих условий:

- Метод не найден.

- MissingMethodException.

- Неперехваченное исключение.

  Чтобы предотвратить эти сообщения об ошибках, устанавливайте решение путем запуска программы установки.

  При установке решения без запуска программы установки установщик не проверяет и не устанавливает необходимые компоненты. Программа установки проверяет наличие соответствующих версий необходимых компонентов и устанавливает их по мере необходимости.

## <a name="manifest-registry-keys-for-add-ins-change-after-an-installshield-limited-edition-project-is-built"></a>Манифест ключей реестра для изменения адъютантов после того, как будет построен проект InstallShield Limited Edition
 Ключ манифеста реестра, который является частью программы установки vsTO Add-in, иногда меняется с *.vsto to* *.dll.manifest* при создании проекта InstallShield Limited Edition.

 Чтобы обойти эту проблему, создайте проект InstallShield Limited Edition в другом решении или используйте CompanyName.AddinName в качестве значения раздела реестра, содержащего имя надстройки VSTO.

## <a name="the-clickonce-installer-for-your-office-solution-doesnt-install-the-primary-interop-assemblies"></a>ClickOnce Установщик для вашего решения Office не устанавливает первичные сборки interop
 При запуске программы установки, созданной ClickOnce для решения Office, установщик для основных сборок взаимодействия Office запускается только в том случае, если никакие основные сборки взаимодействия еще не установлены.

 Если программа настройки не устанавливает PIAs правильно, установите их вручную, запустив файл установки, названный *o2007pia.msi* из каталога установки.

## <a name="reinstall-office-solutions-causes-an-argument-out-of-range-exception"></a>Переустановка решений Office вызывает аргумент вне диапазона исключения
 При повторной установке решения Office может возникать исключение <xref:System.ArgumentOutOfRangeException> со следующим сообщением об ошибке: "Заданный аргумент находится вне диапазона допустимых значений".

 Такая ситуация возникает, если регистр URL-адреса для местоположения установки отличается. Например, эта ошибка будет отображаться, `http://fabrikam.com/ExcelSolution.vsto` если вы установили `http://fabrikam.com/excelsolution.vsto` решение Office с первого раза, а затем использовали второй раз.

 Чтобы предотвратить появление этого сообщения, используйте один и тот же регистр при установке решения Office.

## <a name="cant-install-a-clickonce-solution-by-opening-the-deployment-manifest-from-the-web"></a>Не усваиваем решение ClickOnce, открыв манифест развертывания из Интернета
 Пользователи могут установить решение Office путем открытия манифеста развертывания из Интернета. Тем не менее, некоторые установки Интернет информационных служб (IIS) блокировать расширение имени *файла .vsto.* Прежде чем использовать его для развертывания решения Office, необходимо определить тип MIME в IIS.

 Для получения информации о том, как определить тип MIME в IIS 7, [см.](https://technet.microsoft.com/library/cc725608(WS.10).aspx)

 Установите **.vsto** в качестве расширения и **application/x-ms-vsto**в качестве типа MIME.

## <a name="see-also"></a>См. также

- [Устранение неполадок развертываний ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)
- [Развертывание решения Office](../vsto/deploying-an-office-solution.md)
