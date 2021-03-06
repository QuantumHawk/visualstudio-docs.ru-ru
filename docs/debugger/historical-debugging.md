---
title: Историческая отладка | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e44e62997cac1060047de03253880bbf577935da
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62895173"
---
# <a name="historical-debugging-c-visual-basic-c"></a>историческая отладка (C#, Visual Basic, C++)

Отладка с ведением журнала — это режим отладки, который зависит от сведений, собранных IntelliTrace. В этом режиме можно переходить назад и вперед по выполнению приложения и проверять его состояние.

 IntelliTrace можно использовать в выпуске Visual Studio Enterprise (но не в выпусках Professional или Community).

## <a name="why-use-historical-debugging"></a>Для чего используется отладка с ведением журнала?

 Задание точек останова для поиска ошибок может быть выполняемой наугад задачей. Точка останова устанавливается в коде ближе к месту, где предполагается возникновение ошибки. Затем приложение запускается в отладчике с надеждой достижения этой точки. В месте прерывания выполнения можно обнаружить источник ошибки. В противном случае придется попробовать установить точку останова в другом месте в коде, повторно запустить отладчик и выполнять тестирование до тех пор, пока проблема не будет найдена.

 ![Установка точки останова](../debugger/media/breakpointprocesa.png "BreakpointProcesa")

 IntelliTrace и режим отладки с ведением журнала позволяют перемещаться по приложению и проверять его состояние (стек вызовов и локальные переменные) без необходимости задания точек останова, перезапуска отладки и многократного выполнения действий по тестированию. Это позволяет сэкономить много времени, особенно если ошибка обнаружена практически в центре тестового сценария, выполнение которого является продолжительным.

## <a name="how-do-i-start-using-historical-debugging"></a>Как приступить к использованию отладки с ведением журнала?

Инструмент IntelliTrace включен по умолчанию. Вам нужно только решить, какие события и вызовы функций представляют для вас интерес и нужно ли просматривать моментальные снимки с полными сведениями о состоянии приложения. Дополнительные сведения об определении нужных компонентов см. в разделе [Возможности IntelliTrace](../debugger/intellitrace-features.md). Поддержка функций зависит от языка и типа приложения.

- Дополнительные сведения о просмотре моментальных снимков с исторической отладкой см. в разделе [Проверка предыдущих состояний приложения с помощью IntelliTrace](../debugger/view-historical-application-state.md).
- Сведения о проверке переменных и навигации по коду см. в статье [Проверка приложения с помощью исторической отладки](../debugger/historical-debugging-inspect-app.md).
- Дополнительные сведения об отладке с использованием событий IntelliTrace см. в разделе [Пошаговое руководство. Использование IntelliTrace](../debugger/walkthrough-using-intellitrace.md).