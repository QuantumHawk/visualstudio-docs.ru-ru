---
title: VSPerf | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b5854e62-279e-4850-bfeb-0c6ef82f4805
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 051c983920ddc80909d721e569c5efb5ecd33a7c
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "74779939"
---
# <a name="vsperf"></a>VSPerf
С помощью программы командной строки **VsPerf** можно выполнять следующие задачи:

1. профилирование приложений универсальной платформы Windows из командной строки, когда среда Visual Studio не установлена на устройстве;

2. профилирование классических приложений Windows 8 и приложений Windows Server 2012 с помощью метода профилирования с выборкой.

   Дополнительные сведения о вариантах профилирования см. в разделе [Средства производительности в приложениях Windows 8 и Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="uwp-apps-only"></a>Только приложения универсальной платформы Windows
 Эти параметры применяются только к приложениям универсальной платформы Windows.

|||
|-|-|
|**/app:{имя_приложения}**|Запускает профилировщик и ожидает запуска указанного приложения из меню "Пуск".<br /><br /> Чтобы просмотреть имена и полные имена пакетов для установленных приложений, выполните команду `vsperf /listapps`.|
|**/package:{полное_имя_пакета}**|Запускает профилировщик и ожидает запуска указанного приложения из меню "Пуск".<br /><br /> Чтобы просмотреть имена и полные имена пакетов для установленных приложений, выполните команду `vsperf /listapps`.|
|**/js**|Требуется для профилирования приложений, написанных на JavaScript.<br /><br /> Соберите данные производительности из приложений, написанных на JavaScript.<br /><br /> Используется только с параметром /package или /attach.|
|**/noclr**|Необязательный параметр. Не собирать данные среды CLR.<br /><br /> Используется только с параметром /package или /attach.<br /><br /> Оптимизация, управляемые символы разрешаться не будут.|
|**/listapps**|Вывод списка имен и полных имен пакетов для установленных приложений.|

## <a name="windows-8-desktop-applications-and-windows-server-2012-applications-only"></a>Только классические приложения Windows 8 и приложения Windows Server 2012
 Эти параметры не работают в приложениях универсальной платформы Windows.

|||
|-|-|
|**/launch:{исполняемый_файл}**|Запускает профилирование заданного исполняемого файла.|
|**/args:{аргументы_исполняемого_файла}**|Задает аргументы командной строки для передачи целевому объекту **/launch**.|
|**/console**|Запускает целевой объект **/launch** в новом командном окне.|

## <a name="all-applications"></a>Все приложения
 Этот параметр применяется к любому приложению Windows 8 или Windows Server 2012.

|||
|-|-|
|**/attach:{идентификатор_процесса&#124;имя_процесса}[,идентификатор_процесса&#124;имя_процесса]...**|Сбор данных из указанных процессов.<br /><br /> Используйте диспетчер задач Windows для просмотра идентификатора процесса (PID) и обработайте имена запущенных приложений.|
|**/file:{имя_отчета}**|Необязательный параметр. Указывает выходной файл (перезаписывает существующий файл).<br /><br /> Используется только с параметром /package или /attach.|
|**/pause**|Приостановить сбор данных.|
|**/resume**|Возобновить сбор данных.|
|**/stop**|Остановить сбор данных и завершить работу целевых процессов.|
|**/detach**|Остановить сбор данных без прекращения работы целевых процессов.|
|**/status**|Показать состояние профилировщика.|

## <a name="see-also"></a>См. также раздел
- [Средства оценки производительности в приложениях Windows 8 и Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)
- [Профилирование из командной строки](../profiling/using-the-profiling-tools-from-the-command-line.md)
