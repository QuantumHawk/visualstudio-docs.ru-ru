---
title: Использование нескольких процессоров при сборке проектов | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- multiple processors
- MSBuild, multiple processor systems
ms.assetid: 49fa36c9-8e14-44f5-8a2b-34146cf6807b
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f5dc62112324f7ad19c47b346ac8c1e3f86570b0
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "77631306"
---
# <a name="use-multiple-processors-to-build-projects"></a>Использование нескольких процессоров при построении проектов

В MSBuild реализована поддержка систем с несколькими процессорами или многоядерными процессорами. Для каждого доступного процессора создается отдельный процесс сборки. Например, если в системе есть четыре процессора, создается четыре процесса сборки. MSBuild может обрабатывать эти сборки одновременно, что позволяет сократить продолжительность операции. При этом параллельная сборка несколько изменяет процедуру выполнения процессов сборки. Такие изменения и рассматриваются в этой статье.

## <a name="project-to-project-references"></a>Ссылки проектов на проекты

 Если при использовании параллельной сборки Microsoft Build Engine встречает ссылки проектов на проекты (P2P), ссылка создается только один раз. Если два проекта имеют одинаковые ссылки P2P, они не будут повторно создаваться отдельно для каждого проекта. Вместо этого обработчик сборки возвращает одну и ту же ссылку P2P обоим проектам, которые зависят от нее. В рамках сеанса все последующие запросы для одного целевого объекта возвращают одну и ту же ссылку P2P.

## <a name="cycle-detection"></a>Обнаружение циклов

 Обнаружение циклов работает так же, как и в MSBuild 2.0, — только теперь MSBuild может обнаруживать циклы в другое время или в ходе сборки.

## <a name="errors-and-exceptions-during-parallel-builds"></a>Ошибки и исключения при параллельной сборке

 В сравнении с непараллельной сборкой в ходе параллельной ошибки и исключения могут появляться в другие моменты времени. Если сборка одного проекта завершится неудачей, сборка других проектов продолжится. MSBuild не останавливает сборку проектов, которые создаются параллельно с теми, сборка которых не удалась. Сборка других проектов будет продолжаться, пока не завершится успехом или ошибкой. Однако, если включено свойство <xref:Microsoft.Build.Framework.IBuildEngine.ContinueOnError%2A>, сборки не останавливаются даже при появлении ошибок.

## <a name="c-project-vcxproj-and-solution-sln-files"></a>Файлы решений (SLN-файлы) и проектов (VCPROJ-файлы) C++

 [Задача MSBuild](../msbuild/msbuild-task.md) может принимать файлы решений (*SLN-файлы*) и проектов (*VCХPROJ-файлы*) C++. Для проектов C++ вызывается VCWrapperProject, а затем создается внутренний проект MSBuild. Для решений C++ вызывается SolutionWrapperProject, а затем создается внутренний проект MSBuild. В обоих случаях полученный проект обрабатывается так же, как любой другой проект MSBuild.

## <a name="multi-process-execution"></a>Выполнение нескольких процессов

 Почти для всех действий, связанных со сборкой важно, чтобы текущий каталог оставался неизменным на протяжении всего процесса. Это позволяет избежать ошибок, связанных с правильностью путей. Как следствие, проекты нельзя выполнять в разных потоках MSBuild, так как они будут создавать несколько каталогов.

 Чтобы эта особенность позволяла использовать несколько процессоров для сборки, MSBuild прибегает к изоляции процессов. Изоляция процессов позволяет MSBuild создавать вплоть до `n` процессов, где `n` равно числу процессоров, доступных в системе. Например если MSBuild собирает решение в системе с двумя процессорами, он создает только два процесса сборки. Эти процессы используются многократно для сборки всех проектов, входящих в решение.

## <a name="see-also"></a>См. также

- [Параллельная сборка нескольких проектов](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)
- [Задачи](../msbuild/msbuild-tasks.md)
