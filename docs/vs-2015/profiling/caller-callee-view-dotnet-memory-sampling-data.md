---
title: Представление "Вызывающий/вызываемый" — данные выборки памяти .NET   Документы Майкрософт
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
- Caller/Callee view
ms.assetid: 36f5b4de-5686-4f40-9e72-f4aee27d833c
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04ba2a522c6accb9dcb5e316ea8c63beb260e739
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47562073"
---
# <a name="callercallee-view---net-memory-sampling-data"></a>Представление "Вызывающий/вызываемый" — данные выборки памяти .NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [представление "Вызывающий-вызываемый" — данные выборки памяти .NET](https://docs.microsoft.com/visualstudio/profiling/caller-callee-view-dotnet-memory-sampling-data).  
  
В представлении "Вызывающий/вызываемый" отображаются данные профилирования памяти .NET для выбранной функции и ее родительских и дочерних функций. Представление "Вызывающий/вызываемый" содержит три таблицы.  
  
 **Текущая функция** отображается в средней таблице, в которой указываются данные профилирования памяти выбранной функции. Значения включают все вызовы функции, попавшие в выборку.  
  
 **Функции, вызывавшие текущую функцию**, отображаются в верхней таблице, в которой указывается значение выбранной (текущей) функции, созданное в результате вызовов вызывающей (родительской) функции.  
  
 **Функции, которые были вызваны текущей функцией**, отображаются в нижней таблице, в которой указываются данные профилирования памяти для вызываемых (дочерних) функций выбранной функции, когда дочерняя функция вызывалась текущей функцией.  
  
 Дважды щелкните строку вызывающей или вызываемой функции, чтобы обозначить эту строку как текущую функцию.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Идентификатор процесса**|Идентификатор процесса (PID) сеанса профилирования.|  
|**Имя процесса**|Имя процесса.|  
|**Имя модуля**|Имя модуля, содержащего функцию.|  
|**Путь к модулю**|Путь к модулю, содержащему функцию.|  
|**Исходный файл**|Исходный файл, содержащий определение данной функции.|  
|**Имя функции**|Полное имя функции.|  
|**Номер строки функции**|Номер строки, на которой эта функция начинается в исходном файле.|  
|**Адрес функции**|Адрес функции.|  
|**Type**|Контекст функции:<br /><br /> **0** — текущая функция;<br /><br /> **1** — функция, вызывающая текущую функцию;<br /><br /> **2** — функция, вызываемая текущей функцией.<br /><br /> Только в отчетах командной строки [VSPerfReport](../profiling/vsperfreport.md).|  
|**Уровень**|Глубина функции в дереве вызовов. Только в отчетах командной строки [VSPerfReport](../profiling/vsperfreport.md).|  
|**Включающие выделения**|- Для текущей функции — число объектов, которые были выделены функцией в ходе сеанса профилирования. Это число включает объекты, созданные в вызываемых функциях.<br />- Для вызывающей функции — число инклюзивных выделений текущей функции, созданных в результате вызова из этой функции.<br />- Для вызываемой функции — число объектов, выделенных экземплярами этой функции, вызванной текущей функцией. Это число включает выделения, выполненные функциями, вызванными этой вызываемой функцией.|  
|**Включающие выделения %**|Процент от общего числа объектов, созданных в ходе сеанса профилирования, в ходе которого осуществлялись инклюзивные выделения для данной функции.|  
|**Исключающие выделения**|- Для текущей функции — число объектов, которые были созданы при выполнении функцией кода в теле функции (то есть когда функция была непосредственно вверху стека вызовов). Это число не включает объекты, созданные в функциях, которые были вызваны данной функцией.<br />- Для вызывающей функции — число эксклюзивных выделений текущей функции, созданных в результате вызова из этой функции.<br />- Для вызываемой функции — число объектов, созданных экземплярами этой функции, вызванной текущей функцией. Это значение не включает объекты, созданные в функциях, которые были вызваны этой вызываемой функцией.|  
|**Исключающие выделения %**|Процент от общего числа объектов, созданных в ходе сеанса профилирования, в ходе которого осуществлялись инклюзивные выделения для данной функции.|  
|**Включающие байты**|- Для текущей функции — число байтов памяти, которые были выделены функцией в ходе сеанса профилирования. Это значение включает память, которая была выделена в функциях, вызванных этой функцией.<br />- Для вызывающей функции — число инклюзивных байтов текущей функции, созданных в результате вызова этой вызывающей функцией.<br />- Для вызываемой функции — число байтов, выделенных для всех экземпляров этой функции, созданных при вызовах из текущей функции. Это значение включает байты, которые были выделены функциями, вызванными вызываемой функцией.|  
|**Включающие байты %**|Процент от общего числа байтов памяти, выделенных при профилировании, при котором выполняется инклюзивное выделение для данной функции.|  
|**Исключающие байты**|- Для текущей функции — число байтов памяти, которые были выделены функцией в ходе сеанса профилирования. Это значение не включает память, которая была выделена функциями, вызванными текущей функцией.<br />- Для вызывающей функции — число эксклюзивных байтов текущей функции, созданных в результате вызовов из вызывающей функцией.<br />- Для вызываемой функции — число байтов, выделенных для экземпляров этой функции, созданных при вызовах из текущей функции. Это значение не включает байты, которые были выделены функциями, вызванными вызываемой функцией.|  
|**Исключающие байты %**|Процент от общего числа байтов памяти, выделенных при профилировании, при котором выполняется эксклюзивное выделение для данной функции.|  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Настройка столбцов представлений отчета](../profiling/how-to-customize-report-view-columns.md)   
 [Представление "Вызывающий/вызываемый" — данные инструментирования памяти .NET](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Caller / Callee View - Sampling Data](../profiling/caller-callee-view-sampling-data.md)  (Представление "Вызывающий/вызываемый" — данные выборки)  
 [Caller/Callee View - Instrumentation Data](../profiling/caller-callee-view-instrumentation-data.md) (Представление "Вызывающий/вызываемый" — данные инструментирования)


