---
title: 'Ошибка: Сбой удаленного входа в систему рабочей группы | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.workgroup_remote_logon_failure
dev_langs:
- CSharp
- VB
- FSharp
- JScript
- C++
helpviewer_keywords:
- logon failure, remote debugging
- remote debugging, logon failure
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d1ee0cfbd021eb7d6a03a791713d187d3c8877c
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72736263"
---
# <a name="error-workgroup-remote-logon-failure"></a>Ошибка: сбой удаленного входа в систему рабочей группы
Текст сообщения об ошибке:

 "Ошибка входа в систему: неизвестное имя пользователя или неверный пароль"

 **Причина**

 Эта ошибка может возникать, если в ходе отладки с компьютера рабочей группы произведена попытка подключиться к удаленному компьютеру. Возможные причины:

- На удаленном компьютере нет учетной записи с соответствующими именем и паролем.

- Если компьютер с Visual Studio и удаленный компьютер принадлежат рабочим группам, эта ошибка может возникать из-за установленного по умолчанию значения параметра **Локальной политики безопасности** на удаленном компьютере. Значение по умолчанию для параметра **Локальная политика безопасности**: **Гостевая — локальные пользователи удостоверяются как гости**. Чтобы производить отладку при таких настройках, необходимо установить параметр на удаленном компьютере в значение **Обычная — локальные пользователи удостоверяются как они сами**.

> [!NOTE]
> Для выполнения следующих задач необходимо иметь права администратора.

### <a name="to-open-the-local-security-policy-window"></a>Открытие окна "Локальная политика безопасности"

1. Запустите оснастку консоли управления (MMC) **secpol.msc**. Для этого введите secpol.msc в поле поиска файлов, в поле "Выполнить" или в командной строке.

### <a name="to-add-user-rights-assignments"></a>Добавление назначений прав пользователя

1. Откройте окно **Локальная политика безопасности**.

2. Разверните папку **Локальные политики**.

3. Выберите **Назначение прав пользователя**.

4. В столбце **Политика** дважды щелкните **Отладка программ** для просмотра назначений текущей локальной групповой политики в диалоговом окне **Параметр локальной политики безопасности**.

     ![Права пользователя локальной политики безопасности](../debugger/media/dbg_err_localsecuritypolicy_userrightsdebugprograms.png "DBG_ERR_LocalSecurityPolicy_UserRightsDebugPrograms")

5. Чтобы добавить новых пользователей, нажмите кнопку **Добавить пользователя или группу**.

### <a name="to-change-the-sharing-and-security-model"></a>Изменение модели безопасности и совместного использования

1. Откройте окно **Локальная политика безопасности**.

2. Разверните папку **Локальные политики**.

3. Нажмите **Параметры безопасности**.

4. В столбце **Политика** дважды щелкните **Сетевой доступ: модель общего доступа и безопасности для локальных учетных записей**.

5. В диалоговом окне **Сетевой доступ: модель общего доступа и безопасности для локальных учетных записей** измените значение на **Обычная — локальные пользователи удостоверяются как они сами** и нажмите кнопку **Применить**.

     ![Параметры локальной политики безопасности](../debugger/media/dbg_err_localsecuritypolicy_securityoptions_networkaccess.png "DBG_ERR_LocalSecurityPolicy_SecurityOptions_NetworkAccess")

## <a name="see-also"></a>См. также
- [Ошибки удаленной отладки и их устранение](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Remote Debugging](../debugger/remote-debugging.md)