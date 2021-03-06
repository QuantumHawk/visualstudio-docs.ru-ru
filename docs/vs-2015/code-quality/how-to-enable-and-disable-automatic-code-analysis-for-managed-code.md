---
title: Включение и отключение автоматического анализа кода для управляемого кода | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 7c22d194-5fea-4f23-b02d-19344fa64a64
caps.latest.revision: 10
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: d87cc57b31e63ae7aafa53c335df2b56f86a0409
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658104"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>Практическое руководство. Включение и отключение автоматического анализа управляемого кода
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Можно настроить выполнение анализа кода перед каждой сборкой проекта управляемого кода. Для каждой конфигурации [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] можно задать различные свойства анализа кода.

### <a name="to-enable-or-disable-automatic-code-analysis"></a>Включение или отключение автоматического анализа кода

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект и выберите пункт **свойства**.

2. В диалоговом окне Свойства проекта щелкните **анализ кода**.

3. Укажите тип сборки в поле **Конфигурация** и Целевая платформа на **платформе**.

4. Чтобы включить или отключить автоматический анализ кода, установите или снимите флажок **Включить анализ кода в сборке (определяет константу CODE_ANALYSIS)** .
