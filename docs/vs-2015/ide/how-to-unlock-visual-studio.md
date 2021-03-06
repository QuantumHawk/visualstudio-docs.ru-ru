---
title: Разблокирование Visual Studio 2015 | Документация Майкрософт
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: ffb580a1-8b5d-48f5-b811-87f8036f50ea
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a71a045661c48fd36733ecd8d2266470667a5c35
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72670596"
---
# <a name="how-to-unlock-visual-studio"></a>Разблокирование Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Вы можете работать с ознакомительной версией Visual Studio бесплатно в течение 30 дней. При входе в интегрированную среду разработки пробный период можно продлить на 90 дней. Чтобы продолжить использование Visual Studio, разблокируйте ее. Для этого:

1. используйте подписку;

2. введите ключ продукта.

## <a name="to-unlock-visual-studio-using-an-online-subscription"></a>Разблокировка Visual Studio с помощью подписки
 Чтобы разблокировать Visual Studio с помощью подписки на Visual Studio или MSDN, связанной с учетной записью Майкрософт, рабочей или школьной учетной записью, выполните следующие действия.

1. Нажмите кнопку "Войти" в верхнем правом углу IDE (или выберите "Файл" > "Параметры учетной записи", чтобы открыть диалоговое окно "Параметры учетной записи", и нажмите кнопку "Вход").

2. Введите учетные данные для учетной записи Майкрософт, рабочей или школьной учетной записи. Visual Studio найдет подписку MSDN или подписку Visual Studio Team Services, связанную с вашей учетной записью.

> [!IMPORTANT]
> Visual Studio автоматически ищет связанные подписки при подключении к учетной записи Visual Studio Team Services из окна Team Explorer. При подключении к учетной записи Visual Studio Team Services вы можете войти, используя учетную запись Майкрософт и рабочую или школьную учетную запись. Если подписка для этой учетной записи пользователя существует, Visual Studio автоматически разблокирует интегрированную среду разработки.

## <a name="to-unlock-visual-studio-with-a-product-key"></a>Разблокирование Visual Studio с помощью ключа продукта

1. Выберите **Файл > Параметры учетной записи**, чтобы открыть диалоговое окно "Параметры учетной записи", а затем щелкните ссылку **Ввести ключ продукта**.

2. Введите в поле ключ продукта.

> [!TIP]
> У предварительных версий Visual Studio нет ключей продукта. Для использования предварительной версии необходимо войти в интегрированную среду разработки.

## <a name="addressing-license-problem-states"></a>Решение проблем с состоянием лицензии

### <a name="updating-stale-licenses"></a>Обновление утративших силу лицензий
 Вы могли увидеть следующее сообщение о том, что ваша лицензия просрочена в Visual Studio.

 ![Диалоговое окно сведений о пользователе Visual Studio](../ide/media/vs2013-userinfo.png "|::ref1::|")

 Это сообщение указывает, что, хотя подписка по-прежнему действительна, маркер лицензии, используемый Visual Studio для обновления подписки, не был обновлен и устарел по одной из следующих причин:

1. вы не использовали Visual Studio или длительное время не были подключены к Интернету;

2. вы вышли из Visual Studio.

   Перед просрочкой маркера лицензии Visual Studio сначала отображает предупреждающее сообщение с запросом на повторный ввод учетных данных.

   Если вы не введете свои учетные данные, маркер устареет. В этом случае в диалоговом окне "Параметры учетной записи" отображается, сколько дней осталось до истечения срока действия. После истечения срока действия маркера необходимо будет повторно ввести учетные данные для этой учетной записи или использовать другой метод лицензирования, описанный выше, прежде чем продолжить работать с Visual Studio.

> [!IMPORTANT]
> При использовании Visual Studio в течение длительного времени в средах с ограниченным или отсутствующим доступом к Интернету следует разблокировать Visual Studio с помощью ключа продукта.

### <a name="updating-expired-licenses"></a>Обновление лицензий с истекшим сроком действия
 Если срок действия лицензии полностью истек и у вас больше нет доступа к Visual Studio, выполните одно из указанных ниже действий.

1. Продлите подписку. Для просмотра дополнительных сведений о лицензии откройте через меню "Файл" диалоговое окно "Параметры учетной записи" и просмотрите сведения о лицензии в правой части окна.

2. При наличии другой подписки, связанной с другой учетной записью, добавьте эту учетную запись в список "Все учетные записи" в левой части диалогового окна "Параметры учетной записи", щелкнув ссылку "Добавить учетную запись..." .

## <a name="see-also"></a>См. также
 [Вход в Visual Studio](../ide/signing-in-to-visual-studio.md)
