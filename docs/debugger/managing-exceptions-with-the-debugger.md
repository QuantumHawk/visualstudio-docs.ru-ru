---
title: Управление исключениями с помощью отладчика | Документация Майкрософт
ms.custom: seodec18
ms.date: 10/09/2018
ms.topic: conceptual
f1_keywords:
- vs.debug.exceptions
- vs.debug.exceptions.find
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- run-time errors
- exception handling, during debugging
- errors [debugger]
- debugger, runtime errors
- On Error-style error handlers
- exceptions, Win32
- run-time errors, debugging
- Win32, exceptions
- run time, exceptions
- error handling
- debugging [Visual Studio], exception handling
- common language runtime, exceptions
- native run-time checks
- exceptions, debugging
ms.assetid: 43a77fa8-37d0-4c98-a334-0134dbca4ece
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 00ad5b41dd0a11661d281f24474b7673ea0a342c
ms.sourcegitcommit: 95f26af1da51d4c83ae78adcb7372b32364d8a2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/13/2020
ms.locfileid: "79301125"
---
# <a name="manage-exceptions-with-the-debugger-in-visual-studio"></a>Управление исключениями с помощью отладчика в Visual Studio

Исключение указывает на состояние ошибки, возникающее при выполнении программы. Можно указать отладчику, какие исключения или наборы исключений должны вызывать прерывание и в какой момент нужно прервать выполнение (то есть приостановить отладчик). Когда отладчик прерывает работу, он показывает, где было создано исключение. Кроме того, можно добавлять или удалять исключения. После открытия решения в Visual Studio в разделе **Отладка > Windows > Параметры исключений** откройте окно **Параметры исключений**.

Предоставьте обработчики, реагирующие на наиболее важные исключения. Сведения о том, как добавлять обработчики для исключений, см. в разделе [Исправление ошибок путем написания более качественного кода C#](../debugger/write-better-code-with-visual-studio.md). Кроме того, узнайте, как настроить отладчик, чтобы всегда прерывать выполнение для некоторых исключений.

При возникновении исключения отладчик записывает его сообщение в окно **Вывод**. Он может прервать выполнение в следующих случаях.

- Создается исключение, которое не обрабатывается.
- Отладчик настроен на прерывание выполнения до вызова обработчика.
- Задан параметр [Только мой код](../debugger/just-my-code.md), и отладчик настроен на прерывание по любому исключению, не обрабатываемому в коде пользователя.

> [!NOTE]
> В ASP.NET существует обработчик исключений верхнего уровня, отображающий станицы ошибок в браузере. Он не прерывает выполнение до тех пор, пока не будет включен параметр **Только мой код**. Пример см. в разделе [Настройка отладчика для продолжения в случае не обработанных пользователем исключений](#BKMK_UserUnhandled) ниже.

<!-- Two consecutive notes are intentional here...-->

> [!NOTE]
> В приложениях, написанных на Visual Basic, отладчик управляет всеми ошибками как исключениями, даже при использовании обработчиков ошибок типа On Error.

## <a name="tell-the-debugger-to-break-when-an-exception-is-thrown"></a>Настройка отладчика для прерывания выполнения при создании исключения

Отладчик может прервать выполнение приложения в точке возникновения исключения, чтобы вы могли проверить исключение еще до вызова обработчика.

В окне **Параметры исключений** (**Отладка > Windows > Параметры исключений**) разверните узел для категории исключений, например **Исключения среды CLR**. Затем установите флажок для конкретного исключения в этой категории, например **System.AccessViolationException**. Можно также выбрать всю категорию исключений.

![Отмечено AccessViolationException](../debugger/media/exceptionsettingscheckaccess.png "ExceptionSettingsCheckAccess")

> [!TIP]
> Для поиска конкретных исключений можно воспользоваться окном **Поиск** на панели инструментов **Параметры исключений** или применить функцию поиска для фильтрации определенных пространств имен (например, **System.IO**).

Если вы выберете исключение в окне **Параметры исключений**, выполнение отладчика будет прерываться везде, где возникает исключение, независимо от того, обработано ли оно. Теперь исключение называется первым экземпляром исключения. Ниже приведено несколько примеров.

- В следующем консольном приложении C# метод Main создает исключение **AccessViolationException** внутри блока `try/catch`.

  ```csharp
  static void Main(string[] args)
  {
      try
      {
          throw new AccessViolationException();
          Console.WriteLine("here");
      }
      catch (Exception e)
      {
          Console.WriteLine("caught exception");
      }
      Console.WriteLine("goodbye");
  }
  ```

  Если исключение **AccessViolationException** отмечено в окне **Параметры исключений**, при выполнении этого кода в режиме отладчика произойдет останов на строке `throw`. После этого выполнение можно продолжить. В консоли должны отображаться обе строки.

  ```cmd
  caught exception
  goodbye
  ```

  Но в ней не отображается строка `here`.

- Консольное приложение C# ссылается на библиотеку классов с классом, имеющим два метода. Один метод создает исключение и обрабатывает его, в то время как второй метод создает такое же исключение, но не обрабатывает его.

  ```csharp
  public class Class1
  {
      public void ThrowHandledException()
      {
          try
          {
              throw new AccessViolationException();
          }
          catch (AccessViolationException ave)
          {
              Console.WriteLine("caught exception" + ave.Message);
          }
      }

      public void ThrowUnhandledException()
      {
          throw new AccessViolationException();
      }
  }
  ```

  Далее приводится метод Main() консольного приложения:

  ```csharp
  static void Main(string[] args)
  {
      Class1 class1 = new Class1();
      class1.ThrowHandledException();
      class1.ThrowUnhandledException();
  }
  ```

  Если исключение **AccessViolationException** отмечено в окне **Параметры исключений**, при выполнении этого кода в режиме отладчика произойдет останов на строке `throw` в методах **ThrowHandledException()** и **ThrowUnhandledException()** .

Чтобы восстановить параметры исключений до значений по умолчанию, выберите **Восстановить для списка параметры по умолчанию**:

![Восстановить параметры исключения до значений по умолчанию](../debugger/media/restoredefaultexceptions.png "RestoreDefaultExceptions")

## <a name="tell-the-debugger-to-continue-on-user-unhandled-exceptions"></a><a name="BKMK_UserUnhandled"></a>Настройка отладчика для возобновления выполнения при возникновении не обработанных пользователем исключений

При отладке кода .NET или JavaScript с параметром [Только мой код](../debugger/just-my-code.md) можно указать отладчику не прерывать выполнение при возникновении исключений, которые не обрабатываются в пользовательском коде, но обрабатываются в другом месте.

1. В окне **Параметры исключений** откройте контекстное меню, щелкнув правой кнопкой мыши метку столбца, а затем выберите **Показать столбцы > Дополнительные действия**. (Если параметр **Только мой код** отключен, данная команда не отображается.) Отобразится третий столбец с именем **Дополнительные действия**.

   ![Столбец "Дополнительные действия"](../debugger/media/additionalactionscolumn.png "AdditionalActionsColumn")

   Для исключения, у которого отображается **Продолжить, если не обрабатывается в пользовательском коде** в этом столбце, отладчик продолжает работу, если это исключение не обрабатывается в пользовательском коде, но обрабатывается в другом месте.

2. Чтобы изменить этот параметр для конкретного исключения, выберите исключение, щелкните правой кнопкой мыши, чтобы открыть контекстное меню, и выберите пункт **Продолжить, если не обрабатывается в пользовательском коде**. Вы также можете изменить параметр для всей категории исключений, например для всех исключений среды CLR.

   ![Параметр **Продолжить, если не обрабатывается в пользовательском коде**](../debugger/media/continuewhenunhandledinusercodesetting.png "ContinueWhenUnhandledInUserCodeSetting")

Например, веб-приложения ASP.NET обрабатывают исключения путем их преобразования в код состояния HTTP 500 ([Обработка исключений в веб-API ASP.NET](/aspnet/web-api/overview/error-handling/exception-handling)), что может затруднить определение источника исключения. В следующем примере пользовательский код вызывает метод `String.Format()` , который создает <xref:System.FormatException>. Выполнение прерывается следующим образом.

![Прервать для необрабатываемых пользователем исключений](../debugger/media/exceptionunhandledbyuser.png "ExceptionUnhandledByUser")

## <a name="add-and-delete-exceptions"></a>Добавление и удаление исключений

Исключения можно добавлять и удалять. Чтобы удалить тип исключения из категории, выберите исключение и нажмите кнопку **Удалить выбранное исключение из списка** (знак "минус") на панели инструментов **Параметры исключений**. Или щелкните исключение правой кнопкой мыши и выберите **Удалить** в контекстном меню. Удаление исключения аналогично снятию флажка для исключения и заключается в том, что при возникновении исключения отладчик продолжит выполнение.

Добавление исключения

1. В окне **Параметры исключений** выберите одну из категории исключений (например, **Среда CLR**).

2. Нажмите кнопку **Добавить исключение в выбранную категорию** (знак "плюс").

   ![Кнопка **Добавить исключение в выбранную категорию **](../debugger/media/addanexceptiontotheselectedcategorybutton.png "AddAnExceptionToTheSelectedCategoryButton")

3. Введите имя исключения (например, **System.UriTemplateMatchException**).

   ![Введите имя исключения](../debugger/media/typetheexceptionname.png "TypeTheExceptionName")

   Исключение будет добавлено в список (в алфавитном порядке) и будет автоматически выбрано.

Чтобы добавить исключение в категории "Исключения доступа к памяти GPU", "Исключения среды выполнения JavaScript" или "Исключения Win32", необходимо включить код ошибки, а также описание.

> [!TIP]
> Проверьте правильность написания! В окне **Параметры исключений** не проверяется существование добавленного исключения. Поэтому при вводе **Sytem.UriTemplateMatchException** появится запись для этого исключения (а не для **System.UriTemplateMatchException**).

Параметры исключения сохраняются в файл SUO решения и таким образом применяются к конкретному решению. Параметры конкретного исключения нельзя повторно использовать в решениях. Сейчас сохраняются только добавленные исключения. Удаленные исключения не сохраняются. Вы можете добавить исключение, закрыть и повторно открыть решение — исключение будет находиться в нем по-прежнему. Однако при удалении исключения, закрытии и повторном открытии решения исключение появится снова.

В окне **Параметры исключений** поддерживаются универсальные типы исключений на C#, но не на Visual Basic. Чтобы делать останов при возникновении таких исключений, как `MyNamespace.GenericException<T>`, необходимо добавить исключение в виде **MyNamespace.GenericException'1**. То есть, если создано следующее исключение в коде:

```csharp
public class GenericException<T> : Exception
{
    public GenericException() : base("This is a generic exception.")
    {
    }
}
```

Вы можете добавить исключение в окне **Параметры исключений**, используя предыдущую процедуру:

![добавление общего исключения](../debugger/media/addgenericexception.png "AddGenericException")

## <a name="add-conditions-to-an-exception"></a>Добавление условий в исключение

Используйте окно **Параметры исключений**, чтобы задать условия для исключений. В числе поддерживаемых условий есть имена модулей, что позволяет включить или исключить определенное исключение. При задании имен модулей в качестве условий можно приостановить выполнение на исключении только для определенных модулей кода. Вы также можете избежать прерывания в определенных модулях.

> [!NOTE]
> Добавление условий в исключение поддерживается, начиная с [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].

Чтобы добавить условные исключения, выполните следующие действия.

1. Нажмите кнопку **Изменить условия** в окне "Параметры исключений" или щелкните правой кнопкой мыши исключение и выберите **Изменить условия**.

   ![Условия для исключения](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

2. Чтобы добавить дополнительное условие к исключению, выберите **Добавить условие**. Отобразятся строки дополнительные условий.

   ![Дополнительные условия для исключения](../debugger/media/extraconditionsforanexception.png "ExtraConditionsForAnException")

3. Для каждой строки условия введите имя модуля и измените список операторов сравнения на **Равно** или **Не равно**. Можно указать подстановочные знаки ( **\\\*** ) в имени, чтобы выбрать более одного модуля.

4. Если необходимо удалить условие, выберите **X** в конце строки условия.

## <a name="see-also"></a>См. также

- [Возобновление выполнения после исключения](../debugger/continuing-execution-after-an-exception.md)<br/>
- [Практическое руководство. Анализ системного кода после исключения](../debugger/how-to-examine-system-code-after-an-exception.md)<br/>
- [Практическое руководство. Проверки времени выполнения машинного кода](../debugger/how-to-use-native-run-time-checks.md)<br/>
- [Использование проверки кода во время выполнения без библиотеки среды выполнения языка C](../debugger/using-run-time-checks-without-the-c-run-time-library.md)<br/>
- [Первое знакомство с отладчиком](../debugger/debugger-feature-tour.md)
