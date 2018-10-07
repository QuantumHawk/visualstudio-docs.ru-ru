---
title: Текст пользовательского интерфейса и справки для Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8747d07-6c90-46cc-b425-55b589f7e9e4
caps.latest.revision: 3
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4f3e8f7541c83372c0d822c3db4bc0e20b3af1a9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47557495"
---
# <a name="ui-text-and-help-for-visual-studio"></a>Текст пользовательского интерфейса и справки для Visual Studio
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [текст пользовательского интерфейса и справки для Visual Studio](https://docs.microsoft.com/visualstudio/extensibility/ux-guidelines/ui-text-and-help-for-visual-studio).  
  
##  <a name="BKMK_UITextAndTerminology"></a> Текст пользовательского интерфейса и терминология  
 Понятный текст крайне важно для эффективной пользовательского интерфейса. Пользователям программного обеспечения, как правило, для чтения метки во-первых, а именно те лучше всего подходят для выполнения поставленной задачи. Статический текст читается с частотой меньше. Планирование пользователям запускать свои сеансы работы с быстрой проверки всего окна, следуют чтения пользовательского интерфейса в этом примерном порядке:  
  
1.  Интерактивные элементы управления в центре  
  
2.  Зафиксировать кнопок  
  
3.  Интерактивные элементы управления, в других приложениях  
  
4.  Основные инструкции  
  
5.  Дополнительные пояснения  
  
6.  Заголовок окна  
  
7.  Другой статический текст, в основном тексте  
  
### <a name="usage-patterns-for-ui-text"></a>Шаблоны использования для текста пользовательского интерфейса  
  
#### <a name="title-bar-text"></a>Текст заголовка  
 Текст заголовка должны совпадать, порожденных пользовательского интерфейса команды.  
  
#### <a name="instructional-text-helper-text"></a>Пояснительный текст (Вспомогательная)  
 В некоторых диалоговых окнах полезно для предоставления важных основных инструкций, чтобы объяснить, что делать в окне или на странице. Иногда это называется «вспомогательный text».  
  
##### <a name="writing-style-rules-for-helper-text"></a>Написание правил стиля для текста вспомогательный  
  
-   Не смогут объяснить тем очевидным. Если он совершенно не требуется, не включайте пояснительный текст.  
  
-   Пояснительный текст всегда помещается в верхней части диалогового окна и должен указывать на выполняемой задаче.  
  
-   Точно Объясните пользователям им необходимо сделать. Избегайте чрезмерного связи и избыточность.  
  
-   Просмотрите каждое окно, чтобы исключить повторяющиеся слова и операторы.  
  
-   Сохраните короткий текст инструкции. Если Дополнительные сведения, необходимые для определенных пользователей или сценариев, затем укажите ссылку на подробные online раздела, посвященного понятию.  
  
-   Напишите текст, чтобы каждое слово содержит вес и не требуется.  
  
-   Выполните существующих рекомендаций корпорации Microsoft по [текста пользовательского интерфейса](https://msdn.microsoft.com/library/windows/desktop/dn742478\(v=vs.85\).aspx) и [стиль и тон](https://msdn.microsoft.com/library/windows/desktop/dn742477\(v=vs.85\).aspx).  
  
#### <a name="supplemental-instructions"></a>Дополнительные инструкции  
 Дополнительные инструкции содержат дополнительные сведения, которое поможет пользователю понять, элементы управления или группы управления. Это также могут быть текстом подсказки, необходимо понимать, какой формат, ожидающий элемент управления для ввода. Используйте дополнительные инструкции только в случае необходимости. Зарезервируйте их для случаев, где вполне вероятно, что пользователь не будет полностью понимать последствия этих выбранную они берут.  
  
 ![Пояснительный текст в Visual Studio](../../extensibility/ux-guidelines/media/0601-b-supplementaltext1.png "0601 b_SupplementalText1")  
  
 **Пояснительный текст в Visual Studio**  
  
 ![Пояснительный текст в Visual Studio](../../extensibility/ux-guidelines/media/0601-c-supplementaltext2.png "0601 c_SupplementalText2")  
  
 **Пояснительный текст в Visual Studio**  
  
#### <a name="infotips"></a>Всплывающих подсказках  
 Часто пояснительного текста может быть слишком длинным для размещения на месте в пользовательском Интерфейсе или можно использовать только для новых пользователей, походили помехи для опытных пользователей. В этом случае инструкции или информационный текст должен размещаться как подсказка под всплывающую подсказку.  
  
 Всплывающих подсказках должны располагаться рядом с элементами управления, что они связаны и следует использовать определенные всплывающая подсказка значок, который ненавязчивый заметно.  
  
 ![Подсказка в Visual Studio](../../extensibility/ux-guidelines/media/0601-d-infotip.png "0601 d_InfoTip")  
  
 **Пример всплывающую подсказку в Visual Studio**  
  
##### <a name="writing-style-rules-for-infotips"></a>Создание правила стиля для всплывающих подсказках  
  
-   Запись всплывающих подсказках в виде полных предложений. Они необходимы определенные команды, прописная и завершение знаки препинания.  
  
-   Использование всплывающих подсказках для дополнения основные инструкции или сведения. Отметим еще раз основную идею просто при использовании различных слов, не требуется всплывающую подсказку.  
  
-   Сохраните всплывающих подсказках короткий и приятный. Используйте служебные слова и обычные, используемом языке, который поддерживает и предлагает пользователю.  
  
-   Выполните существующих рекомендаций корпорации Microsoft по [текста пользовательского интерфейса](https://msdn.microsoft.com/library/windows/desktop/dn742478\(v=vs.85\).aspx) и [стиль и тон](https://msdn.microsoft.com/library/windows/desktop/dn742477\(v=vs.85\).aspx).  
  
#### <a name="control-labels"></a>Метки элементов управления  
 Метки элементов управления должны быть кратких и следуйте [Windows Desktop рекомендации для элементов управления](https://msdn.microsoft.com/library/windows/desktop/dn742399\(v=vs.85\).aspx).  
  
 Дополнительные сведения о формат метки элемента управления и размещения в пользовательском Интерфейсе, см. [макет для Visual Studio](../../extensibility/ux-guidelines/layout-for-visual-studio.md).  
  
#### <a name="help-links"></a>Ссылки на разделы справки  
 Ссылки на разделы справки можно разместить либо пояснительного текста или в теле пользовательского интерфейса. Они могут быть ссылки на справку для или запустите внутренней диалоговые окна.  
  
##### <a name="visual-style-rules-for-help-links"></a>Правила стиля оформления для ссылки на справку  
  
-   Используйте цвета правильную среду для гиперссылки. Правильно оформленного гиперссылки не будет кратко мигать красным при щелчке. Если вы видите, это, то это означает, что цвета среды не используются.  
  
-   Подчеркивание следует использовать только при наведении курсора мыши или когда ссылку внедряется в абзаце.  
  
-   Более подробные сведения о стилях визуальный элемент и взаимодействие для гиперссылок см. в разделе кнопок и гиперссылок.  
  
##### <a name="writing-style-rules-for-help-links"></a>Написание правил стиля для ссылки на справку  
  
-   При запуске диалоговых окон, соблюдения стандартов для многоточие: нет кнопку с многоточием для навигации, эллипсы, если для задачи требуется дополнительный пользовательский Интерфейс.  
  
     ![Ссылка на справку в Visual Studio](../../extensibility/ux-guidelines/media/0601-e-helplink.png "0601 e_HelpLink")  
  
     **Многоточие (...) в ссылке справки указывает, что задача будет требовать дополнительный пользовательский Интерфейс.**  
  
-   Ссылки не должно начинаться с «Сведения», так как не намерения пользователя. Пользователю необходимо ответить на конкретный вопрос, не будут получать общее образование.  
  
-   Таким образом, чтобы они вопрос ответят что раздела, ссылки справки фразы.  
  
     Неправильный:  
     «Дополнительные сведения о ценах на мобильные службы Windows Azure»  
  
     Правильно:  
     «Какие параметры ценообразования доступны для мобильных служб Windows Azure»?  
  
-   Никогда не используйте *нажмите кнопку...* Чтобы текст ссылки.  
  
-   Никогда не ссылку только слово «сюда». Это вызывает неудобства для некоторых средств чтения с экрана, которые будут голосовая связь только с гиперссылкой слово.  
  
     Неправильный:  
     «Сведения о мобильных служб Windows Azure **здесь**"  
  
     Правильно:  
     «Какие параметры ценообразования доступны для мобильных служб Windows Azure»?  
  
-   Дополнительные сведения о стиль правильные записи для ссылки на справку, см. в разделе [рекомендации рабочего стола Windows для получения справки](https://msdn.microsoft.com/library/windows/desktop/dn742494\(v=vs.85\).aspx).  
  
#### <a name="hint-text"></a>Текст подсказки  
 Текст подсказки отображается в качестве водяного знака в элементе управления или под элементом управления. Правильное форматирование будет применено, используя соответствующий маркер VSColors, `Environment.GrayText`.  
  
 Он может присутствовать в различных видов.  
  
-   Вместо метки элемента управления:  
  
     ![Указание текста в Visual Studio](../../extensibility/ux-guidelines/media/0601-f-hinttext1.png "0601 f_HintText1")  
  
-   С глагола инструкций:  
  
     ![Указание текста в Visual Studio](../../extensibility/ux-guidelines/media/0601-g-hinttext2.png "0601 g_HintText2")  
  
-   С текстом, указывающее, требуется запись:  
  
     ![Указание текста в Visual Studio](../../extensibility/ux-guidelines/media/0601-h-hinttext3.png "0601 h_HintText3")  
  
#### <a name="watermark-text"></a>Текст водяного знака  
 В пустой конструктора текст должен указывать, что нужно сделать, а также приведены ссылки для открытия других связанных окон, при необходимости:  
  
 ![Текст в Visual Studio для нижнего предела](../../extensibility/ux-guidelines/media/0601-i-watermarktext.png "0601 i_WatermarkText")  
  
 **Пример текста водяного знака в Visual Studio**  
  
### <a name="common-terminology"></a>Общие термины  
  
|Термин|Объяснение|Комментарий|  
|----------|-----------------|-------------|  
|Вход / выход|Команды, используемые как синонимы, веб-для проверки подлинности в веб-свойство представления. В клиентов мы будем использовать этот раз как понятие верхнего уровня для подписи входящего и исходящего соединения пользователя интегрированной среды разработки, которое представляет удостоверение верхнего уровня, обеспечивающие более высокого уровня возможности, такие как роуминг и лицензирования, не доступны вместе с другими подключениями.|Пользователь интегрированной среды разработки является единственной возможностью, должен представляют входа / выхода verb, так как он представляет пользователя верхнего уровня IDE.|  
|Подключение / отключение|Использовать в местах, где функция хранит одно подключение к веб-службы.|Обозреватель серверов, где можно задать только одно активное подключение Azure одновременно, является примером/разрыв подключения.|  
|Добавление и удаление|Неразрушающее. Используется при добавлении или удалении что-то из списка.|Диалоговое окно списка сервер TFS диспетчер соединений является примером добавить или удалить.|  
|Удаление|Уничтожения данных. Используйте только в том случае, если удаляемый элемент будут окончательно удалены или удален с диска.|Обычно «Удалить» требуется строка, если результат является удаление файла с диска.|  
  
## <a name="error-messages"></a>Сообщения об ошибках  
  
### <a name="overview"></a>Обзор  
 Ошибки возникают. Установка ограничения на разрешенные действия пользователя является разумным первым шагом не вызывает ошибок. Тем не менее при возникновении ошибки, сообщение об ошибке правильно составленный можно перейти в сторону устранения проблемы. Сообщения об ошибках пожалуй, являются одной из наиболее важных типов уведомлений, который видит пользователь, так как они являются синхронными и указывает на проблему, которую необходимо решить. Непродуманная ошибках оставить пользователи на свои собственные, чтобы определить причину возникновения ошибок, а также возможные решения.  
  
 Пользователи могут отключить основное внимание уделяется вопросам, поскольку вызовет перегрузку или толку сообщений об ошибках, в том случае, поэтому сообщения только необходимые записи, которые увеличивают ценность для пользователя. Если сообщение является просто уведомления, используйте альтернативное представление.  
  
### <a name="rules-for-creating-an-error-message"></a>Правила создания сообщения об ошибке  
  
-   При создании сообщения об ошибках, выберите уровень соответствующее сообщение об ошибке для аудитории. Цель для простой кратких описаний, укажите действие, которое пользователь может делать, если применимо. Все, что пользователю не нужно знать не состояние.  
  
-   Предоставление помощи конструктивные. Это упрощает чтение и отреагировать на сообщение об ошибке, содержащая инструкцию.  
  
-   Не следует использовать двойной отрицательных результатов.  
  
-   Выполните оба автоматическое и вручную грамматики и орфографии проверить все сообщения об ошибках, который вы пишете.  
  
-   Для сложных ошибок Избегайте последовательного обмена данными. Никогда не используйте привязку F1 сообщения об ошибке. Само сообщение должно быть достаточно.  
  
-   Используйте правильный значок.  
  
-   Упростить вопросы для понимания и использования кнопки, снимите выбор, например «Удалить» и «Отмена».  
  
-   Для предупреждения иметь четкое представление о каким будет результат продолжением. Кнопки должно быть указано, результат.  
  
-   Для ошибок приведено, пользователь может сделать для устранения проблемы. Кнопки должны быть действия или сказать «Закрыть». Не используйте кнопку «ОК» для сообщения об ошибке.  
  
-   Некоторые вопросы, которые задаться вопросом при создании сообщения об ошибке:  
  
    -   Выяснить, как решить проблему с этой ошибкой только пользователь?  
  
    -   Используется ли пользователь же словаря этой ошибкой?  
  
    -   Является неоднозначной этой ошибки или совместно в нескольких ситуациях? Если это так, как вы предоставляют пользователям указания для решения, которые необходимы?  
  
#### <a name="build-errors"></a>Ошибки построения  
 Так как Visual Studio — это средство разработки программного обеспечения, многие из ее компонентов имеют компиляции, преобразование или кодирование шаг, чтобы преобразовать работу разработчика в двоичной форме. Эти преобразования могут вызвать ошибки, если компилятор не может обработать неправильно созданные файлы или не были правильно задать параметры компилятора.  
  
 Пользователи Visual Studio могут тратить огромное количество часов разработки, устранение ошибок сборки. Это время разрешения увеличивается, когда ошибки имеют зависимости или когда сообщения об ошибках плохо написаны, поэтому может оказаться сложно обнаружить источник ошибки.  
  
 Лучшие ошибки сборки являются те, которые не возникают в первую очередь, поэтому Visual Studio предоставляет автозаполнения и подчеркивание слов IntelliSense. Проверяющие элементы управления схемы и аналогичные средства предоставляют одинаковые обратной связи. Эти механизмы заранее помочь пользователю для создания правильного кода, уменьшая вероятность возникновения ошибки сборки.  
  
 Visual Studio предоставляет окно инструментов, где пользователи могут считывать и просматривать ошибки, возникшие в окнах своих документов. Сочетания клавиш предоставляются, так что пользователь может быстро перейти больших объемов кода и перейти непосредственно к местоположению, неполадки. Visual Studio также позволяет каждой ошибки сборки должны быть привязаны к определенным кодом ключевое слово или контекста справки, таким образом, пользователь может перейти непосредственно к раздел справки, которое позволяет получить более подробные сведения об ошибке.  
  
 Ошибки построения краткими, записи:  
  
-   **Использование простого языка** , разъясняющее проблему с незначительной или нулевой жаргоне компилятора. Текст ошибки сборки не может быть излишне технической.  
  
-   **Описываются возможные причины.** Например «отсутствует двоеточие между свойством и значением в "(свойство): (значение)" объявление.»  
  
-   Получите подробные сведения о возможные решения. Если не хватает места, Дополнительные сведения могут быть помещены в соответствующий раздел справки.  
  
### <a name="components-of-a-well-written-error-message"></a>Компоненты сообщения об ошибке правильно составленный  
  
#### <a name="use-the-shell-dialog-service-for-error-messages"></a>Используйте службу диалоговое окно оболочки для сообщений об ошибках.  
 С помощью диалогового окна службы оболочки позволяет управлять внешним видом сообщения — шрифты, в частности, без существенных изменений к отдельным элементам. Используйте **IErrorInfo** механизмы и сообщите о них с помощью **IVsUIShell::SetErrorInfo/ReportErrorInfo**.  
  
#### <a name="choose-an-effective-and-appropriate-notification-presentation"></a>Выберите презентацию на эффективный и соответствующие уведомления.  
 Используйте модальное диалоговое окно с критическое предупреждение, если требуется немедленное действие во избежание потери данных (синхронного уведомления). Важные значки зарезервированы для ситуаций, в какие Закрытие сообщения без чтения, это может привести к отрицательным последствиям. Потеря данных является критической ситуации, требующий ответ уровня сигнала. Злоупотребление значок "критический" desensitizes пользователям его важности. Если сообщение об ошибке информационными по природе, рассмотрите альтернативы для модального диалогового окна (асинхронное уведомление).  
  
#### <a name="provide-a-clean-succinct-explanation-of-why-the-problem-occurred-rather-than-a-technical-explanation"></a>Предоставляет чистую и краткое объяснение, почему проблема вместо того чтобы технические сведения.  
 Пользователи, содержащие технические сведения, в объяснении overburdening сделает их более вероятно игнорировать сообщения об ошибках. Примеры хороший обмена сообщениями:  
  
-   «Не удается открыть запрошенный файл».  
  
-   «Не удалось подключиться к Интернету».  
  
#### <a name="provide-information-about-how-to-fix-the-problem"></a>Укажите сведения о том, как устранить проблему.  
 Предложить пользователю того, как устранить проблему. Будем честными с пользователем, если нет подсказок. Предоставляют прямые ссылки на альтернативные online источников, таких как техническую поддержку или поддержку сообщества. Попробуйте для направления пользователей к определенной сети информации, необходимой для проблемы. Если код ошибки рассмотрите возможность связывание пользователей с обсуждений об этой конкретной ошибке. Примеры хороший обмена сообщениями:  
  
-   «Убедитесь, что вы подключены к Интернету и повторите попытку.»  
  
-   «Убедитесь, что файл существует и имеется разрешение, чтобы открыть его.»  
  
#### <a name="write-a-message-that-is-short-and-to-the-point"></a>Написать сообщение, короткие и точными.  
 Сообщение об ошибке можно уведомить, объяснить и предлагают решения но по-прежнему игнорироваться, если это слишком много слов. Одним из решений является использование постепенного развертывания с кнопкой "Сведения". Например, не дает краткое описание/решения, а затем указать дополнительные подробные сведения о кнопке сведения. Если пользователи выбирают Дополнительные сведения об ошибке, это так.  
  
 Язык в сообщении должно быть:  
  
-   **Соответствующий домен.** Используйте язык, который пользователь будет понимать. Несмотря на то, что наши клиенты являются разработчиками, часто у них нет контекста и терминология, которая у нас есть.  
  
-   **Определенные.** Избегайте неопределенным формулировки и предоставить определенные имена и расположение объектов, участвующих. Например сообщение об ошибке, например «недопустимый символ» бесполезно. Какой символ? «Файл не найден». Какой файл?  
  
-   **Учтивость.** Не обвиняйте пользователя и сделать их недомыслия. Избегайте враждебного или оскорбительного характера языка (kill, выполнение, завершить работу, Неустранимая, недопустимое). Избегайте прописные текст, который часто рассматривается как крик и как нечитаем. Не используйте юмор.  
  
-   **Правильно.** Используйте правильный вариант правописания и грамматики (даже в альфа). Опечатки непрофессионально и неудобно.  
  
-   **Соответствующие зависимости от контекста.** Используйте соответствующую кнопку текст. Избегайте кнопки «ОК» и вместо этого использовать «Продолжить» или «Да/нет».  
  
### <a name="error-message-examples"></a>Примеры сообщения ошибки  
  
|Хорошо|Неправильный|  
|----------|---------|  
|«Номер набирается больше не в службе. Проверьте номер и наберите его еще раз или набрать 0 для оператора.»|-«(449) Ошибка: недопустимый номер»<br />-«Эта ошибка необработанное исключение означает, что операция завершилась успешно».<br /><br /> ![Сообщение об ошибке в Visual Studio](../../extensibility/ux-guidelines/media/0602-a-errordialog.png "0602 a_ErrorDialog")|  
  
## <a name="accessing-help"></a>Доступ к справке  
  
### <a name="overview"></a>Обзор  
 В дополнение к документации в библиотеке MSDN Visual Studio пользователь имеет несколько точек доступа для упрощения работы пользователя в пользовательском Интерфейсе. Убедитесь, что эти точки доступа постоянно доступны, специализированных групп необходима для использования в справке, предлагаемые средой. Ниже приведены эти точки доступа.  
  
-   **Инструкции и дополнительные текст в диалоговых окнах.** Статический текст, который предоставляет направление или описание, либо в пользовательском Интерфейсе поверхности или доступным при наведении курсора мыши над значком подсказку.  
  
-   **Справка F1** (редактор). В редакторе Visual Studio, и пользователь может доверять, что в любое время, при нажатии клавиши F1 откроется раздел справки для текущего выделения. Убедитесь, что разделы, связанные с F1 соответствующий и информативным.  
  
-   **Ссылки на разделы справки.** Гиперссылки в диалоговое окно, окно инструмента или конструктора, который запускает темой, чтобы помочь пользователю узнать больше о технологии, возможностей или сведения о способах выполнения задачи.  
  
-   **Механизмы вспомогательный пользовательского интерфейса, такие как смарт-тегов и стандартных диалоговых окон.** Эти механизмы призвано помочь пользователю понять элемент пользовательского интерфейса или упрощения задач, таких как смарт-теги или диалоговые окна построителя.  
  
-   **Кнопки справки пользовательского интерфейса** (устаревшая версия). Отображается индикатор в строке заголовка, который предоставляет доступ к в связанном разделе справки F1.  
  
### <a name="text"></a>Текста  
  
#### <a name="instructional-and-supplemental-text-in-dialogs"></a>Инструкции и дополнительные текст в диалоговых окнах  
 В диалоговых окнах, которые поддерживают сложные задачи может возникнуть необходимость предоставить пояснительный текст в пользовательском Интерфейсе, часто в верхней части диалогового окна или рядом с ним сложных элементов управления. См. в разделе [пользовательского интерфейса текст и терминология](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) подробные сведения о написании стиля.  
  
#### <a name="infotips"></a>Всплывающих подсказках  
 Часто пояснительный текст может быть слишком длинным для размещения на месте в пользовательском Интерфейсе или можно использовать только для новых пользователей, походили помехи для опытных пользователей. В этом случае инструкции или информационный текст должен размещаться как подсказка под всплывающую подсказку.  
  
 Всплывающих подсказках должны располагаться рядом с элементами управления, что они связаны и следует использовать определенные всплывающая подсказка значок, который ненавязчивый заметно.  
  
 ![Подсказка в Visual Studio](../../extensibility/ux-guidelines/media/0601-d-infotip.png "0601 d_InfoTip")  
  
 **Пример всплывающую подсказку в Visual Studio**  
  
### <a name="interactive-help-mechanisms"></a>Интерактивного механизма справки  
  
#### <a name="f1-help"></a>Справка F1  
 Необходим справки F1 редактора или конструктора, но не в другом месте в среде Visual Studio.  
  
#### <a name="hyperlinks-to-help-topics"></a>Ссылки на разделы справки  
 Гиперссылки можно использовать для выполнения действий, перемещение по интегрированной среде разработки или запустить справку в браузере. См. в разделе [пользовательского интерфейса текст и терминология](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) Дополнительные сведения о языке и 07.10.01 кнопок и гиперссылок рекомендации по использованию visual и макет.  
  
#### <a name="help--buttons-in-dialog-title-bars-deprecated"></a>Справка [?] кнопок в диалоговое окно заголовки окон (устаревшая версия)  
 По большей части кнопки справки [?] в строке заголовка диалоговых окон являются устаревшими. Разделы пользовательского интерфейса больше не являются частью нашей модели doc и поэтому может быть соответствующем разделе для связывания. По сути кнопка панели заголовка было то же самое справки F1, а, больше не требуется в диалоговых окнах. В некоторых случаях это по-прежнему используется как индикатор, что дополнительные концептуальные и методические сведения недоступны, несмотря на то, что гиперссылки чаще используются в пользовательском Интерфейсе новой.  
  
##### <a name="dialogs-created-through-the-environment"></a>Диалоговые окна, созданными с помощью среды  
 Многие диалоговые окна оболочки создаются с помощью **VBDialogBoxParam** функции. Этот общей функции был обновлен для помощи при перемещении **помочь** кнопку из диалогового окна, чтобы **?** Кнопка, при этом сохраняя архитектуру, которая обеспечивает обратную совместимость и расширяемые.  
  
 В частности **VBDialogBoxParam** функция просматривает шаблона диалогового окна для кнопки с идентификатором **IDHELP** (9) или метка **помочь** или **& помочь**. Если кнопка справки, обнаруживается, она скрыта и **WS_EX_CONTEXTHELP** стиля добавляется к диалоговому окну, который помещает **?** Кнопка в строке заголовка диалогового окна.  
  
 При создании диалогового окна, он помещает proc диалоговое окно, в стек и вызывает диалоговое окно с предварительной обработки proc диалоговое окно с именем **DialogPreProc**. Когда **?** кнопки, он отправляет **WM_SYSCOMMAND** из **SC_CONTEXTHELP** в диалоговом окне. **DialogPreProc** фиксирует эту команду и изменяет его на **WM_HELP** сообщения, которое передается исходное процедуре диалогового окна  
  
 Большинство диалоговых окон, среда создана иметь кнопку "Справка" в диалоговом окне. При отображении диалогового окна «Справка» автоматически скрыто и только **?** кнопка работает. Если **?** когда-нибудь кнопки удаляется или изменяется в Windows, это решение позволяет быстро вернуться к исходной кнопки «Справка».  
  
 Это решение четыре предположения, которые могут вызвать ошибки:  
  
-   Кнопка справки диалогового окна **IDHELP** (9).  
  
-   При скрытии кнопку "Справка", диалоговое окно выглядит правильно.  
  
-   Диалоговое окно не заменяет его winproc.  
  
-   Диалоговое окно не встроено в другое диалоговое окно.  
  
 Если диалоговое окно находится в пределах msenv и не использует **VBDialogBoxParam**, изучить использование **VBDialogBoxParam** перед реализацией собственного обработчика.  
  
##### <a name="dialogs-created-through-other-packages"></a>Диалоги, созданные в других пакетах  
 Вы можете реализовать свое собственное решение для диалоговых окон, которые находятся за пределами msenv. Для класса общего диалогового окна в пакете VSPackage рассмотрите возможность перемещения кнопки в строке заголовка или реализации обработчика на каждое диалоговое окно. Следующий код, который составляет основу реализации помогут вам приступить к работе:  
  
```  
struct DLGPROCITEM  
{  
    FARPROC proc; // The info used to create the dialog.  
    DLGPROCITEM* procPrev;  
};  
  
DLGPROCITEM* g_dlgProcStack = NULL;  
  
// A dialog starter/wrapper function is used to push the new  
// dialog proc to the top of our dialog proc stack.  
  
int SomeDialogStarterFunction(hinst, id, proc, etc)  
{  
    if (g_dlgProcStack == NULL)  
    {  
        g_dlgProcStack = new DLGPROCITEM;  
        g_dlgProcStack->procPrev = NULL;  
    }  
    else  
    {  
        DLGPROCITEM* procItem = new DLGPROCITEM;  
        g_dlgProcStack->procPrev = g_dlgProcStack;  
        g_dlgProcStack = procItem;  
    }  
}  
  
// Pop this dialog proc off the dialog proc stack.  
  
DialogBoxIndirectParam...(...)  
{  
    DLGPROCITEM* procItem = g_dlgProcStack->procPrev;  
    delete g_dlgProcStack;  
    g_dlgProcStack = procItem;  
}  
  
// A wrapper dialog procedure will allow us to capture the  
// SC_CONTEXTHELP button on the title bar from Windows and  
// forward it as a simple WM_HELP message back to the dialog.  
  
INT_PTR CALLBACK DialogPreProc(HWND hwndDlg, UINT uMsg,  
    WPARAM wParam, LPARAM lParam)  
{  
    if (uMsg == WM_SYSCOMMAND && wParam == SC_CONTEXTHELP)  
    {  
        uMsg = WM_HELP;  
        wParam = 0;  
        lParam = 0;  
    }  
    return CallWindowProc((WNDPROC)g_dlgProcStack->proc,  
        hwndDlg, uMsg, wParam, lParam);  
}  
```  
  
##### <a name="help-buttons-in-managed-code"></a>Кнопки «Справка» в управляемом коде  
 Переопределение поведения по умолчанию окна кнопка панели заголовка справки очень просто в управляемом коде. Ниже приведен полный демонстрационного приложения, демонстрирующий такие действия. По сути, необходимо переопределить формы **WndProc** метод и затем fire off Справка F1 запросов, когда **SC_CONTEXTHELP** перехватывается сообщение.  
  
```  
using System;  
using System.Windows.Forms;  
  
public class HelpForm : Form  
{  
    private const int SC_CONTEXTHELP = 0xF180;  
    private const int WM_SYSCOMMAND = 0x0112;  
  
    public HelpForm()  
    {  
        this.ClientSize = new System.Drawing.Size(300, 250);  
        this.HelpButton = true;  
        this.MaximizeBox = false;  
        this.MinimizeBox = false;  
        this.Name = "HelpForm";  
        this.Text = "Help Form";  
    }  
  
    protected override void WndProc(ref Message m)  
    {  
        if (m.Msg == WM_SYSCOMMAND && SC_CONTEXTHELP == (int)m.WParam)  
            ShowHelp();  
        else  
            base.WndProc(ref m);  
    }  
  
    private void ShowHelp()  
    {  
        MessageBox.Show("F1 Help goes here.");  
    }  
  
     [STAThread]  
    static void Main()  
    {  
        Application.EnableVisualStyles();  
        Application.EnableRTLMirroring();  
        Application.Run(new HelpForm());  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Шрифты и форматирование для Visual Studio](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md)   
 [Макет для Visual Studio](../../extensibility/ux-guidelines/layout-for-visual-studio.md)   
 [Уведомления и ход выполнения для Visual Studio](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)
