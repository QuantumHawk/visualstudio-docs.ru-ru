---
title: Представление "Функции" — данные инструментирования памяти .NET | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Functions view
ms.assetid: cd45b379-394b-4b71-828c-92cd89e46ae0
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b020f0101332b7fc192aed7b58befdde64012d12
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47558145"
---
# <a name="functions-view---net-memory-instrumentation-data"></a>Представление "Функции" — данные инструментирования памяти .NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [представление "функции" — данные инструментирования памяти .NET](https://docs.microsoft.com/visualstudio/profiling/functions-view-dotnet-memory-instrumentation-data).  
  
В представлении "Функции" данных профилирования выделения памяти .NET, собранных методом инструментирования, содержатся функции, которые выделяли память в ходе сеанса профилирования. Строка функции содержит размер и число выделений, а также данные о времени, характерные для функции.  
  
## <a name="general"></a>Общие  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Имя функции**|Имя функции.|  
|**Адрес функции**|Адрес функции.|  
|**Номер строки функции**|Номер строки, на которой эта функция начинается в исходном файле.|  
|**Число вызовов**|Общее количество вызовов этой функции.|  
|**Исходный файл**|Исходный файл, содержащий определение данной функции.|  
|**Имя модуля**|Имя модуля, содержащего функцию.|  
|**Путь к модулю**|Путь к модулю, содержащему функцию.|  
|**Идентификатор процесса**|Идентификатор процесса (PID) сеанса профилирования.|  
|**Имя процесса**|Имя процесса.|  
|**Исключающие временные издержки на зонды**|Дополнительные временные затраты для этой функции, вызванные инструментированием. Из всех эксклюзивных значений времени уже вычтены дополнительные временные затраты на зонды.|  
|**Инклюзивные временные издержки на зонды**|Дополнительные временные затраты для этой функции и ее дочерних функций, вызванные инструментированием. Из всех включающих значений времени уже вычтены дополнительные временные затраты на зонды.|  
  
## <a name="net-memory-values"></a>Значения памяти .NET  
 Инклюзивные значения памяти .NET функции указывают число (выделений) и размер (байт) объектов, которые были созданы функцией и ее дочерними функциями.  
  
 Эксклюзивные значения памяти функции указывают число и размер объектов, которые были созданы функцией, но не ее дочерними функциями.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Включающие выделения**|Общее число объектов, созданных в данной функции, и всех вызванных ею функций.|  
|**% инклюзивных выделений**|Процент от общего числа объектов, выделенных при выполнении профилирования, в ходе которого осуществлялись инклюзивные выделения для данной функции.|  
|**Исключающие выделения**|Общее количество объектов, созданных в процессе выполнения функцией кода в теле функции. Это значение не включает объекты, созданные в функциях, которые были вызваны этой функцией.|  
|**% эксклюзивных выделений**|Процент от общего числа объектов, созданных в ходе сеанса профилирования, при котором выполнялись эксклюзивные выделения данной функции.|  
|**Инклюзивные байты**|Число байтов памяти, которые были выделены в данной функции и вызванных ею функциях.|  
|**Включающие байты %**|Процент от общего числа байтов памяти, выделенных при профилировании, которые являются инклюзивными байтами для данной функции.|  
|**Исключающие байты**|Число байтов памяти, которые были выделены данной функцией, но не вызванными ею функциями.|  
|**% эксклюзивных байтов**|Процент от общего числа байтов памяти, выделенных при профилировании, которые являются эксклюзивными байтами для данной функции.|  
  
## <a name="elapsed-inclusive-values"></a>Значения затраченного инклюзивного времени  
 Значения затраченного инклюзивного времени указывают время, в течение которого функция находилась в стеке вызовов. В значении учтено время, которое было затрачено на выполнение дочерних функций и системных операций, например переключение контекста и операции ввода-вывода.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Затраченное инклюзивное время**|Общее затраченное инклюзивное время для всех вызовов этой функции.|  
|**% затраченного инклюзивного времени**|Процент общего затраченного инклюзивного времени в сеансе профилирования в затраченном инклюзивном времени этой функции.|  
|**Среднее затраченное инклюзивное время**|Среднее затраченное инклюзивное время для вызова этой функции.|  
|**Максимальное затраченное инклюзивное время**|Максимальное затраченное инклюзивное время для вызова данной функции.|  
|**Минимальное затраченное инклюзивное время**|Минимальное затраченное инклюзивное время для вызова данной функции.|  
  
## <a name="elapsed-exclusive-values"></a>Значения затраченного эксклюзивного времени  
 Значения затраченного эксклюзивного времени соответствуют времени выполнения функции непосредственно вверху стека вызовов. В значении учтено время, которое было затрачено на выполнение дочерних функций и системных операций, например переключение контекста и операции ввода-вывода, но не входит время, которое было затрачено на выполнение дочерних функций.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Затраченное эксклюзивное время**|Общее затраченное эксклюзивное время для всех вызовов этой функции.|  
|**% затраченного эксклюзивного времени**|Процент общего затраченного эксклюзивного времени в сеансе профилирования в общем затраченном эксклюзивном времени данной функции.|  
|**Среднее затраченное эксклюзивное время**|Среднее затраченное эксклюзивное время для вызова этой функции.|  
|**Максимальное затраченное эксклюзивное время**|Максимальное затраченное эксклюзивное время для вызова данной функции.|  
|**Минимальное затраченное эксклюзивное время**|Минимальное затраченное эксклюзивное время для вызова данной функции.|  
  
## <a name="application-inclusive-values"></a>Значения инклюзивного времени приложения  
 Значения инклюзивного времени указывают время, в течение которого функция находилась в стеке вызовов. В значении не учтено время, которое было затрачено на выполнение вызовов системных операций, например переключение контекста и операции ввода-вывода, но учтено время, которое было затрачено на выполнение дочерних функций.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Инклюзивное время приложения**|Общее инклюзивное время приложения всех вызовов данной функции.|  
|**% инклюзивного времени приложения**|Процент общего затраченного инклюзивного времени в сеансе профилирования в общем затраченном инклюзивном времени приложения для данной функции.|  
|**Среднее инклюзивное время приложения**|Среднее инклюзивное время приложения для вызова данной функции.|  
|**Среднее инклюзивное время приложения**|Максимальное инклюзивное время приложения для вызова данной функции.|  
|**Среднее инклюзивное время приложения**|Минимальное инклюзивное время приложения для вызова данной функции.|  
  
## <a name="application-exclusive-values"></a>Значения эксклюзивного времени приложения  
 Значения эксклюзивного времени приложения соответствуют времени выполнения функции непосредственно в верхней части стека вызовов. В значении не учтено время, которое было затрачено на выполнение вызовов системных операций, например переключение контекста и операции ввода-вывода, и сюда не входит время, затраченное на выполнение дочерних функций.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Эксклюзивное время приложения**|Общее эксклюзивное время приложения всех вызовов данной функции.|  
|**% эксклюзивного времени приложения**|Процент общего затраченного эксклюзивного времени в сеансе профилирования в общем затраченном эксклюзивном времени приложения для данной функции.|  
|**Среднее эксклюзивное время приложения**|Среднее эксклюзивное время приложения для вызова данной функции.|  
|**Максимальное эксклюзивное время приложения**|Максимальное эксклюзивное время приложения для вызова данной функции.|  
|**Минимальное эксклюзивное время приложения**|Минимальное эксклюзивное время приложения для вызова данной функции.|  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Настройка столбцов представлений отчета](../profiling/how-to-customize-report-view-columns.md)   
 [Представление "Функции" — выборка](../profiling/functions-view-dotnet-memory-sampling-data.md)   
 [Представление "Функции"](../profiling/functions-view-instrumentation-data.md)   
 [Представление "Функции"](../profiling/functions-view-sampling-data.md)


