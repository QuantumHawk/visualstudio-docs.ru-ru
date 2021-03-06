---
title: 'Ошибка: у вас нет разрешения на идентификацию процесса | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cad229f80676c3d1f7a7d23ad7a29729c834929b
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72736224"
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Ошибка: у вас нет разрешения на идентификацию процесса.
У вас нет разрешения на идентификацию процесса. Это может быть следствием системной конфигурации.

 Отладчику не удалось идентифицировать процесс, что является необходимым для отладки. Наиболее вероятной причиной является отключение служб терминалов. По умолчанию службы терминалов включены. Выполните следующие действия, чтобы включить их снова.

### <a name="to-enable-terminal-services"></a>Чтобы включить службы терминалов

1. Нажмите кнопку **Пуск** и выберите пункт **Панель управления**.

2. На панели управления при необходимости выберите **Переключение к классическому виду**, а затем дважды щелкните пункт **Администрирование**.

3. В окне **Администрирование** дважды щелкните **Управление компьютером**.

4. В окне "Управление компьютером" разверните узел **Службы и приложения**.

5. В группе **Службы и приложения** выберите **Службы**.

     В правой области окна появится список служб.

6. В списке **Службы** щелкните правой кнопкой мыши **Службы терминалов** и выберите **Свойства**.

7. В окне **Свойства служб терминалов** найдите вкладку **Общие** и установите **Тип запуска** в значение **Вручную**.

8. Нажмите кнопку **ОК**.

9. Перезагрузите компьютер.

     Эта процедура не включает автоматически удаленный рабочий стол. Если необходимо включить удаленный рабочий стол на компьютере, выполните следующие дополнительные действия.

### <a name="to-enable-remote-desktop"></a>Чтобы включить удаленный рабочий стол

1. Нажмите кнопку **Пуск** и щелкните правой кнопкой мыши **Мой компьютер**.

2. Выберите **Свойства**.

     Откроется окно **Свойства системы**.

3. Нажмите **Удаленные сеансы**.

4. В области **Удаленный рабочий стол** выберите **Разрешить удаленный доступ к этому компьютеру**.

5. Нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также
- [Ошибки удаленной отладки и их устранение](../debugger/remote-debugging-errors-and-troubleshooting.md)