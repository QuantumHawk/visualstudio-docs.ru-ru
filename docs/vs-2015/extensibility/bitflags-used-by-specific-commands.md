---
title: Битовые флаги, используемые конкретными командами | Документация Майкрософт
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
- source control plug-ins, bitflags used by specific commands
ms.assetid: 37969977-6f7d-45c9-ba03-1306ae71f5d1
caps.latest.revision: 25
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7f9a633dd88e0018c6c9ccc82438ed99770885c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47568422"
---
# <a name="bitflags-used-by-specific-commands"></a>Битовые флаги, используемые конкретными командами
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [битовые флаги, используемые конкретными командами](https://docs.microsoft.com/visualstudio/extensibility/bitflags-used-by-specific-commands).  
  
Поведение некоторых функций в API подключаемых модулей управления источника можно изменить, установив один или несколько битов в одно значение. Эти значения называются битовые флаги. Различные битовые флаги, используемые API подключаемых модулей управления источника здесь можно увидеть, сгруппированные по функция, которая использует их.  
  
## <a name="checked-out-flag"></a>Извлечен флаг  
 Этот флаг можно задать для либо [SccAdd](../extensibility/sccadd-function.md) или [SccCheckin](../extensibility/scccheckin-function.md).  
  
|Flag|Значение|Описание|  
|----------|-----------|-----------------|  
|`SCC_KEEP_CHECKEDOUT`|0x1000|Оставьте файл извлеченным.|  
  
## <a name="add-flags"></a>Добавьте флаги  
 Эти флаги используются [SccAdd](../extensibility/sccadd-function.md).  
  
|Flag|Значение|Описание|  
|----------|-----------|-----------------|  
|`SCC_FILETYPE_AUTO`|0x00|Ожидается, что подключаемый модуль системы управления версиями автоматически определять, является ли файл текстовых или двоичных.|  
|`SCC_FILETYPE_TEXT`|0x01|Тип файла — текст.|  
|`SCC_FILETYPE_BINARY`|0x04|Имеет двоичный тип файла. **Примечание:** `SCC_FILETYPE_TEXT` и `SCC_FILETYPE_BINARY` флаги являются взаимоисключающими. Задайте один или оба.|  
|`SCC_ADD_STORELATEST`|0x02|Store только последняя версия (не разности).|  
  
## <a name="diff-flags"></a>Флаги Diff  
 [SccDiff](../extensibility/sccdiff-function.md) использует эти флаги для определения области действия операции поиска различий. `SCC_DIFF_QD_xxx` Флаги являются взаимоисключающими. Если указан один из них, не визуальной обратной связи, то должен быть предоставлен. В поле «Быстрый diff» (длина Очереди), подключаемый модуль не определить, как файл отличается, только в том случае, если оно отличается. Если ни один из этих флагов указано, «visual» diff выполняется; Подробный файл различия вычисления и отображения. Если Запрошенная длина Очереди не поддерживается, подключаемый модуль перемещается Далее наиболее подходящий вариант. Например если интегрированной среды разработки запрашивает контрольной суммы и подключаемый модуль не поддерживает его, подключаемый модуль выполняет full содержимое Проверьте (по-прежнему гораздо быстрее, чем визуального представления).  
  
|Flag|Значение|Описание|  
|----------|-----------|-----------------|  
|`SCC_DIFF_IGNORECASE`|0x0002|Игнорируйте различия в регистре.|  
|`SCC_DIFF_IGNORESPACE`|0x0004|Не учитывать различия пустого пространства. **Примечание:** `SCC_DIFF_IGNORECASE` и `SCC_DIFF_IGNORESPACE` флаги имеют необязательно битовые флаги.|  
|`SCC_DIFF_QD_CONTENTS`|0x0010|Длина Очереди, сравнивая все содержимое файла.|  
|`SCC_DIFF_QD_CHECKSUM`|0x0020|Длина Очереди с контрольной суммы.|  
|`SCC_DIFF_QD_TIME`|0x0040|Длина Очереди, метки даты и времени файла.|  
|`SCC_DIFF_QUICK_DIFF`|0x0070|Это маска, используемая для проверки всех битовые флаги длина Очереди. Он не должен быть передан в функцию; три битовые флаги длина Очереди являются взаимоисключающими. Длина Очереди всегда означает без отображения пользовательского интерфейса.|  
  
## <a name="populatelist-flag"></a>Флаг PopulateList  
 Этот флаг используется [SccPopulateList](../extensibility/sccpopulatelist-function.md) в `fOptions` параметра.  
  
|Flag|Значение|Описание|  
|----------|-----------|-----------------|  
|`SCC_PL_DIR`|0x00000001L|Каталоги, файлы не передает интегрированной среды разработки.|  
  
## <a name="populatedirlist-flags"></a>Флаги PopulateDirList  
 Эти флаги используются [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) в `fOptions` параметра.  
  
|Значение параметра|Значение|Описание|  
|------------------|-----------|-----------------|  
|SCC_PDL_ONELEVEL|0x0000|Проверьте только один уровень папок для каталогов (по умолчанию).|  
|SCC_PDL_RECURSIVE|0x0001|Рекурсивно проверить всем каталогам в каждом заданном каталоге.|  
|SCC_PDL_INCLUDEFILES|0x0002|Имена включаемых файлов в процессе проверки.|  
  
## <a name="openproject-flags"></a>Флаги OpenProject  
 Эти флаги используются [SccOpenProject](../extensibility/sccopenproject-function.md) в `dwFlags` параметра.  
  
|Значение параметра|Значение|Описание|  
|------------------|-----------|-----------------|  
|SCC_OP_CREATEIFNEW|0x00000001L|Если проект не существует в системе управления версиями, создайте ее. Если этот флаг не установлен, запрашивать пользователя для проекта для создания (если `SCC_OP_SILENTOPEN` установлен флаг).|  
|SCC_OP_SILENTOPEN|0x00000002L|Не запрашивать пользователя, чтобы создать проект; просто возвратить `SCC_E_UNKNOWNPROJECT`.|  
  
## <a name="get-flags"></a>Получить флаги  
 Эти флаги используются [SccGet](../extensibility/sccget-function.md) и [SccCheckout](../extensibility/scccheckout-function.md).  
  
|Flag|Значение|Описание|  
|----------|-----------|-----------------|  
|`SCC_GET_ALL`|0x00000001L|Интегрированная среда разработки передает каталоги, файлы не: получить все файлы в этих каталогах.|  
|`SCC_GET_RECURSIVE`|0x00000002L|Передает каталоги интегрированной среды разработки: получение этих каталогов и всех подкаталогах.|  
  
## <a name="noption-values"></a>Значения nOption  
 Эти флаги используются [SccSetOption](../extensibility/sccsetoption-function.md) в `nOption` параметра.  
  
|Flag|Значение|Описание|  
|----------|-----------|-----------------|  
|`SCC_OPT_EVENTQUEUE`|0x00000001L|Задать состояние очереди событий.|  
|`SCC_OPT_USERDATA`|0x00000002L|Укажите данные пользователя для `SCC_OPT_NAMECHANGEPFN`.|  
|`SCC_OPT_HASCANCELMODE`|0x00000003L|Интегрированная среда разработки может обрабатывать "Отмена"|  
|`SCC_OPT_NAMECHANGEPFN`|0x00000004L|Задайте обратный вызов для изменения имен.|  
|`SCC_OPT_SCCCHECKOUTONLY`|0x00000005L|Отключите извлечение подключаемого модуля пользовательского интерфейса элемента управления источника и не задан рабочий каталог.|  
|`SCC_OPT_SHARESUBPROJ`|0x00000006L|Добавьте из системы управления версиями, чтобы указать рабочий каталог. Попробуйте для совместного использования в связанный проект, если это является прямым потомком.|  
  
## <a name="dwval-bitflags"></a>dwVal битовые флаги  
 Эти флаги используются [SccSetOption](../extensibility/sccsetoption-function.md) в `dwVal` параметра.  
  
|Flag|Значение|Описание|Используемые `nOption` значение|  
|----------|-----------|-----------------|-----------------------------|  
|`SCC_OPT_EQ_DISABLE`|0x00L|Приостанавливает действие очереди событий.|`SCC_OPT_EVENTQUEUE`|  
|`SCC_OPT_EQ_ENABLE`|0x01L|Включает ведение журнала очереди событий.|`SCC_OPT_EVENTQUEUE`|  
|`SCC_OPT_HCM_NO`|0L|(По умолчанию) Имеет режим без отмены; Подключаемый модуль необходимо указать при необходимости.|`SCC_OPT_HASCANCELMODE`|  
|`SCC_OPT_HCM_YES`|1L|Среда IDE обрабатывает "Отмена".|`SCC_OPT_HASCANCELMODE`|  
|`SCC_OPT_SCO_NO`|0L|(По умолчанию) ОК, чтобы извлечь из пользовательского интерфейса подключаемого модуля; рабочий каталог имеет значение.|`SCC_OPT_SCCCHECKOUTONLY`|  
|`SCC_OPT_SCO_YES`|1L|Нет подключаемый модуль извлечения пользовательского интерфейса, не рабочий каталог.|`SCC_OPT_SCCCHECKOUTONLY`|  
  
## <a name="see-also"></a>См. также  
 [Подключаемые модули системы управления версиями](../extensibility/source-control-plug-ins.md)
