---
title: Вкладка "сообщения", диалоговое окно "Параметры сообщения" | Документация Майкрософт
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
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8048c63ed9b9f049ed171002dfcc612fc9361569
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47564159"
---
# <a name="messages-tab-message-options-dialog-box"></a>Вкладка "Сообщения" диалогового окна "Параметры сообщения"
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [вкладка "сообщения", диалоговое окно "Параметры сообщения"](https://docs.microsoft.com/visualstudio/debugger/messages-tab-message-options-dialog-box).  
  
Используйте **сообщений** tab, чтобы выбрать список типов сообщений [представления сообщений](../debugger/messages-view.md)и для указания условий поиска сообщений. Для отображения [диалоговое окно "Параметры сообщения"](../debugger/message-options-dialog-box.md), выберите **сообщений журнала** из **Spy** меню.  
  
 Как правило, сначала выберите **группы сообщений**и настраивать их выделение, выбрав отдельные **сообщения для просмотра**. **Все** кнопку выбора всех типов сообщений и **None** кнопка отменяет выделение всех типов.  
  
 Следующие параметры доступны на **сообщений** вкладке:  
  
 **Сообщения для просмотра**  
 Выберите конкретное сообщение для просмотра. При создании нового окна сообщений, она может отображать все сообщения. При фильтрации сообщений от **сообщений** вкладку, фильтр применяется только к новым сообщениям, не, которые уже отображены в представлении Windows.  
  
 **Группы сообщений**  
 Выберите группы сообщений для просмотра. Доступны следующие группы:  
  
-   WM_USER: с кодом не меньше WM_USER  
  
-   Зарегистрированные: зарегистрировано **RegisterWindowMessage** вызова  
  
-   Неизвестно: неизвестные сообщения в диапазоне от 0 до (WM_USER – 1)  
  
 Обратите внимание, что они **группы сообщений** не сопоставлены с определенных записей в разделе **сообщения для просмотра**. При выборе группы выделение применяется непосредственно к потоку сообщений.  
  
 Затененный флажок в **группы сообщений** указывает, что **сообщения для просмотра** поле со списком был изменен для сообщений в этой группе; выбираются не все типы сообщений в этой группе.  
  
 **Сохранить параметры по умолчанию**  
 Сохраните текущие параметры для последующего использования в качестве параметров поиска сообщений. Эти параметры также сохраняются при выходе из Spy ++.


