---
title: Представление "Состязание за ресурсы" — данные по состязаниям | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.resourcecontention
helpviewer_keywords:
- Resource Contentions view
ms.assetid: 14a7f774-211f-4ef8-af05-94d1c8f65d2f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b3f18cf1131e61ba88832d59e0e77f462c088bec
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47571747"
---
# <a name="resource-contentions-view---contention-data"></a>Представление "Состязание за ресурсы" — данные по состязаниям
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [ресурсов представление - данные по Состязаниям](https://docs.microsoft.com/visualstudio/profiling/resource-contentions-view-contention-data).  
  
В представлении "Состязание за ресурсы" приводятся данные по состязаниям за ресурсы, являющиеся источниками событий состязания. Событие состязания возникает, когда функция в потоке вынуждена ожидать доступа к ресурсу из-за того, что функции в другом потоке предоставлен монопольный доступ к ресурсу. Каждый из ресурсов является корневым узлом дерева вызовов, в котором представлены пути выполнения функций, приведшие к созданию событий состязания.  
  
## <a name="data-values"></a>Значения данных  
  
### <a name="resource-values"></a>Значения ресурсов  
 Данные в строке ресурса отражают общее время блокирования доступа к ресурсу в данных профилирования, а также общее число событий состязания, созданных по причине конфликта доступа к данному ресурсу. Инклюзивные и эксклюзивные значения для ресурса всегда совпадают.  
  
### <a name="function-values"></a>Значения функции  
 Значения функции основаны на экземплярах функции, имеющих место в представленном в дереве вызове пути выполнения.  
  
-   Эксклюзивные значения основаны на событиях, происходящих при выполнении функцией операторов в теле функции. События, произошедшие в функциях, вызванных данной функцией, не включаются в эксклюзивное время.  
  
-   Инклюзивные значения основаны на событиях, происходящих при выполнении данной функции или вызванной ею функции.  
  
### <a name="percentage-values"></a>Значения в процентах  
 Значения в процентах основаны на суммарном времени или общем количестве событий состязания в данных профилирования. Если к отчету или представлению сеанса профилирования применить фильтр, то в качестве суммарных значений будут использоваться только данные по времени блокировки и количестве состязаний.  
  
## <a name="navigating-the-resource-allocation-view"></a>Навигация по представлению "Выделение ресурсов"  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Name**|Имя ресурса или функции.|  
|**Эксклюзивное время блокировки**|— Для ресурса — общее время блокирования доступа к ресурсу, вызвавшее ожидание потока.<br />— Для функции — время блокирования доступа экземпляров функции к родительскому ресурсу, когда функция выполняла код в теле функции. Время блокирования в функциях, которые были вызваны данной функцией, не включается.|  
|**Эксклюзивное время блокировки %**|— Для ресурса — доля (в процентах) общего времени блокировки из данных профилирования, относящаяся к конкретному ресурсу.<br />— Для функции — доля (в процентах) общего времени блокировки из данных профилирования, затраченная в эксклюзивном времени приложения экземпляров этой функции.|  
|**Эксклюзивные конфликты**|— Для ресурса — общее количество случаев блокирования доступа к ресурсу, вызвавших ожидание потока.<br />— Для функции — количество случаев блокирования доступа экземпляров функции к родительскому ресурсу, когда функция выполняла код в теле функции. События блокировки в функциях, которые были вызваны данной функцией, не включаются.|  
|**Эксклюзивные конфликты %**|— Для ресурса — доля (в процентах) общего числа событий состязания из данных профилирования, относящаяся к доступу к конкретному ресурсу.<br />— Для функции — доля (в процентах) общего числа конфликтов из данных профилирования, выпавшая исключительно на случаи доступа экземпляров данной функции к родительскому ресурсу.|  
|**Включая время блокирования**|— Для ресурса — общее время блокирования доступа к ресурсу, вызвавшее ожидание потока.<br />— Для функции — время блокирования доступа экземпляров функции или других функций, вызванных экземплярами, к родительскому ресурсу, когда функция выполняла код в теле функции.|  
|**Включая % времени блокирования**|— Для ресурса — доля (в процентах) общего времени блокировки из данных профилирования, относящаяся к конкретному ресурсу.<br />— Для функции — доля (в процентах) общего времени блокировки в сеансе профилирования, затраченная в инклюзивном времени блокировки экземпляров этой функции.|  
|**Включая состязания**|— Для ресурса — общее количество случаев блокирования доступа к ресурсу, вызвавших ожидание потока.<br />— Для функции — доля (в процентах) общего числа событий состязания в сеансе профилирования, выпавшая включительно на случаи доступа экземпляров данной функции к родительскому ресурсу.|  
|**Включая % состязаний**|— Для ресурса — доля (в процентах) общего числа событий состязания в сеансе профилирования, относящаяся к доступу к конкретному ресурсу.<br />— Для функции — количество случаев блокирования доступа экземпляров функции к родительскому ресурсу, когда функция выполняла код в теле функции. События блокировки в функциях, которые были вызваны данной функцией, не включаются.|  
|**Уровень**|Глубина функции в дереве вызовов. Только в отчетах командной строки [VSPerfReport](../profiling/vsperfreport.md).|  
|**Номер строки функции**|Номер строки, на которой эта функция начинается в исходном файле.|  
|**Имя модуля**|Имя модуля, содержащего функцию.|  
|**Путь к модулю**|Путь к модулю, содержащему функцию.|  
|**Идентификатор процесса**|Идентификатор процесса, в котором выполнялась функция.|  
|**Имя процесса**|Имя процесса.|  
|**Исходный файл**|Исходный файл, содержащий определение данной функции.|


