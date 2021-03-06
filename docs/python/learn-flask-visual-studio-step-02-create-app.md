---
title: Руководство по Flask в Visual Studio. Шаг 2. Представления и шаблоны
titleSuffix: ''
description: Пошаговое руководство по основам Flask в контексте проектов Visual Studio, в особенности сведения о создании приложения и использовании представлений и шаблонов.
ms.date: 01/07/2019
ms.topic: tutorial
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 03a0eb6808b2298e0727492978d9beb7cfaf2216
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2020
ms.locfileid: "79300879"
---
# <a name="step-2-create-a-flask-app-with-views-and-page-templates"></a>Шаг 2. Создание приложения Flask с представлениями и шаблонами страниц

**Предыдущий шаг. [Создание проекта и решения Visual Studio](learn-flask-visual-studio-step-01-project-solution.md)**

В шаге 1 этого руководства мы создали приложение Flask с одной страницей и всем кодом в одном файле. Для дальнейшей разработки рекомендуется выполнить рефакторинг кода и создать структуру для шаблонов страниц. В частности, отделить код для представлений приложения от других аспектов, таких как код запуска.

На этом шаге вы научитесь делать следующее:

> [!div class="checklist"]
> - рефакторинг кода приложения для разделения представлений и кода запуска (шаг 2.1);
> - преобразование представления с помощью шаблона страницы (шаг 2.2).

## <a name="step-2-1-refactor-the-project-to-support-further-development"></a>Шаг 2-1. Рефакторинг проекта для поддержки дальнейшей разработки

В коде, созданном с помощью шаблона "Пустой веб-проект Flask", у вас есть один файл *app.py*, содержащий код запуска наряду с одним представлением. Для дальнейшей разработки приложения с несколькими представлениями и шаблонами будет лучше разделить эти аспекты.

1. В папке проекта создайте папку приложения с именем `HelloFlask` (щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **Добавить** > **Новая папка**.)

2. В папке *HelloFlask* создайте файл с именем *\_\_init\_\_.py* со следующим содержимым, которое создает экземпляр `Flask` и загружает представления приложения (созданные на следующем шаге):

    ```python
    from flask import Flask
    app = Flask(__name__)

    import HelloFlask.views
    ```

3. В папке *HelloFlask* создайте файл с именем *views.py* со следующим содержимым. Имя *views.py* важно, так как вы использовали `import HelloFlask.views` в *\_\_init\_\_.py*; если имена не будут совпадать, во время выполнения возникнет ошибка.

    ```python
    from flask import Flask
    from HelloFlask import app

    @app.route('/')
    @app.route('/home')
    def home():
        return "Hello Flask!"
    ```

    Помимо переименования функции и маршрутизации к `home`, этот код содержит код отрисовки страницы из *app.py* и импортирует объект `app`, объявленный в *\_\_init\_\_.py*.

4. Создайте вложенную папку в *HelloFlask* с именем *templates*, которая пока остается пустой.

5. В корневой папке проекта переименуйте файл *app.py* в *runserver.py* и сделайте так, чтобы содержимое совпадало со следующим кодом:

    ```python
    import os
    from HelloFlask import app    # Imports the code from HelloFlask/__init__.py

    if __name__ == '__main__':
        HOST = os.environ.get('SERVER_HOST', 'localhost')

        try:
            PORT = int(os.environ.get('SERVER_PORT', '5555'))
        except ValueError:
            PORT = 5555

        app.run(HOST, PORT)
    ```

6. Структура проекта должна выглядеть следующим образом:

    ![Структура проекта после рефакторинга кода](media/flask/step02-project-structure.png)

7. Выберите **Отладка** > **Начать отладку** (**F5**) или нажмите кнопку **Веб-сервер** на панели инструментов (браузер может отличаться), чтобы запустить приложение и открыть браузер. Попробуйте оба маршрута URL-адресов: / и/home.

8. Также можно установить точки останова в разных частях кода и перезапустить приложение для выполнения последовательности запуска. Например, задайте точку останова в первых строках *runserver.py* и *HelloFlask\_* init *_.py*, а также в строке `return "Hello Flask!"` в *views.py*. Затем перезапустите приложение (с помощью пункта **Отладка** > **Перезапуск**, сочетания клавиш **CTRL**+**F5** или кнопки на панели инструментов, показанной ниже) и запустите пошаговое выполнение кода (**F10**) или выполнение из каждой точки останова, нажав клавишу **F5**.

    ![Кнопка перезапуска на панели инструментов отладки в Visual Studio](media/debugging-restart-toolbar-button.png)

9. По завершении остановите приложение.

### <a name="commit-to-source-control"></a>Фиксация в системе управления версиями

Так как вы внесли изменения в код и успешно их протестировали, пришло время просмотреть и зафиксировать изменения в системе управления версиями. В дальнейших шагах этой статьи указано соответствующее время для повторной фиксации изменений в системе управления версиями, после чего необходимо будет вернуться к этому разделу.

1. Нажмите кнопку изменения в нижней части Visual Studio (выделена кружком ниже), чтобы перейти к **Team Explorer**.

    ![Кнопка изменения системы управления версиями в строке состояния Visual Studio](media/flask/step02-source-control-changes-button.png)

1. В **Team Explorer** введите сообщение фиксации, например "Рефакторинг кода", и выберите **Зафиксировать все**. После завершения фиксации отобразится сообщение **Фиксация \<хэша > создана локально. Синхронизируйте, чтобы использовать изменения совместно с сервером.** Если вы хотите отправить изменения в удаленный репозиторий, выберите **Синхронизировать**, а затем — **Отправить** в разделе **Исходящие фиксации**. Кроме того, вы можете накапливать несколько локальных фиксаций перед отправкой в удаленный репозиторий.

    ![Отправка фиксаций в удаленный репозиторий в Team Explorer](media/flask/step02-source-control-push-to-remote.png)

### <a name="question-how-frequently-should-one-commit-to-source-control"></a>Вопрос. Как часто следует выполнять фиксации в системе управления версиями?

Ответ. При фиксации изменений в системе управления версиями создается запись в журнале изменений и точка, к которой можно вернуть репозиторий при необходимости. Кроме того, в каждой фиксации можно проверить конкретные изменения. Поскольку фиксации в Git стоят недорого, рекомендуется чаще выполнять фиксации, а не накапливать большое число изменений в одной фиксации. Очевидно, что фиксировать каждое небольшое изменение в отдельном файле тоже не стоит. Обычно фиксация выполняется при добавлении возможности, изменении структуры (как в этом шаге) или осуществлении некоторого рефакторинга кода. Кроме того, рекомендуется обсудить частоту и условия фиксаций с другими участниками команды.

Не стоит путать частоту фиксации и частоту отправки фиксаций в удаленный репозиторий. Несколько фиксаций можно накапливать в локальном репозитории перед отправкой в удаленный репозиторий. Опять же, частота фиксаций зависит от решения, принятого командой в отношении управления репозиторием.

## <a name="step-2-2-use-a-template-to-render-a-page"></a>Шаг 2-2. Использование шаблона для отображения страницы

Функция `home` в *views.py* создает только ответы HTTP в простом текстовом формате для страницы. Тем не менее большинство реальных веб-страниц предоставляют ответы с большим количеством страниц HTML, которые часто содержат фактические данные. На самом деле основной причиной для определения представления с помощью функции является возможность создавать содержимое динамически.

Поскольку возвращаемое значение для представления — просто строка, можно создать любой нужный код HTML в строке, используя динамическое содержимое. Тем не менее, поскольку рекомендуется разделять разметку и данные, будет лучше разместить разметку в шаблоне и хранить данные в коде.

1. Для начинающих разработчиков рекомендуется изменить файл *views.py* так, чтобы он содержал следующий код, который использует встроенный HTML-код для страницы с некоторым динамическим содержимым:

    ```python
    from datetime import datetime
    from flask import render_template
    from HelloFlask import app

    @app.route('/')
    @app.route('/home')
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        html_content = "<html><head><title>Hello Flask</title></head><body>"
        html_content += "<strong>Hello Flask!</strong> on " + formatted_now
        html_content += "</body></html>"

        return html_content
    ```

1. Запустите приложение и обновите страницу несколько раз, чтобы увидеть, что дата и время обновляются. По завершении остановите приложение.

1. Чтобы преобразовать механизм отрисовки страницы для использования шаблона, создайте файл с именем *index.html* в папке *templates* со следующим содержимым, где `{{ content }}` — заполнитель или маркер заполнителя (также называется *переменной шаблона*), для которого необходимо указать значение в коде:

    ```html
    <html>
        <head><title>Hello Flask</title></head>

        <body>
            {{ content }}
        </body>
    </html>
    ```

1. Измените функцию `home` так, чтобы она использовала `render_template` для загрузки шаблона, и укажите значение для свойства content, для чего требуется указать именованный аргумент, соответствующий имени заполнителя. Flask автоматически выполняет поиск шаблонов в папке *templates*, поэтому путь к шаблону указывается относительно этой папки:

    ```python
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        return render_template(
            "index.html",
            content = "<strong>Hello, Flask!</strong> on " + formatted_now)
    ```

1. Запустите приложение, чтобы увидеть результаты, и обратите внимание на то, что встроенный HTML-код в значении `content` не преобразуется *как* HTML, так как модуль шаблонов (Jinja) автоматически экранирует HTML-содержимое. Автоматическое экранирование предотвращает случайные уязвимости к атакам путем внедрения кода: разработчики часто собирают входные данные с одной страницы и используют их в качестве значения на другой странице с помощью заполнителя шаблона. Экранирование служит напоминанием о том, что HTML-код не рекомендуется хранить в коде.

    Соответственно, просмотрите файл *templates\index.html*, чтобы задать четкие заполнители для каждой части данных в разметке:

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
        </head>
        <body>
            <strong>{{ message }}</strong>{{ content }}
        </body>
    </html>
    ```

    Затем обновите функцию `home` для предоставления значений для всех заполнителей:

    ```python
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        return render_template(
            "index.html",
            title = "Hello Flask",
            message = "Hello, Flask!",
            content = " on " + formatted_now)
    ```

1. Запустите приложение еще раз, чтобы увидеть правильно выводимые данные.

    ![Запуск приложения с помощью шаблона](media/flask/step02-result.png)

1. Зафиксируйте изменения в системе управления версиями и обновите удаленный репозиторий при необходимости, как описано в [шаге 2.1](#commit-to-source-control).

### <a name="question-do-page-templates-have-to-be-in-a-separate-file"></a>Вопрос. Следует ли хранить шаблоны страницы в отдельном файле?

Ответ. Хотя шаблоны обычно хранятся в отдельных HTML-файлах, вы также можете использовать встроенный шаблон. Чтобы сохранить четкое разделение между исправлением и кодом, рекомендуется использовать отдельный файл.

### <a name="question-must-templates-use-the-html-file-extension"></a>Вопрос. Следует ли использовать в шаблонах расширение файлов HTML?

Ответ. Использовать расширение *.html* для файлов шаблона страницы совсем необязательно, так как вы всегда определяете точный относительный путь к файлу в первом аргументе функции `render_template`. Однако Visual Studio (и другие редакторы) обычно предоставляет такие функции, как завершение кода или разметка синтаксиса, для файлов *HTML*, что значительно важнее того, что шаблоны страниц не имеют строгого формата HTML.

На самом деле при работе с проектом Flask Visual Studio автоматически определяет, является ли HTML-файл, который вы редактируете, шаблоном Flask, и предоставляет несколько функций с автоматическим завершением. Например, когда вы начинаете вводить комментарий шаблона страницы Flask, `{#`, Visual Studio автоматически предоставляет вам закрывающие символы `#}`. В командах **Закомментировать выделенный фрагмент** и **Раскомментировать выделенный фрагмент** (в меню **Изменить** > **Дополнительно** или на панели инструментов) также используются комментарии шаблона, а не HTML.

### <a name="question-can-templates-be-organized-into-further-subfolders"></a>Вопрос. Можно ли поместить шаблоны в дополнительные вложенные папки?

Ответ. Да, можно использовать вложенные папки и ссылаться на относительный путь в *templates* в вызовах `render_template`. Это позволяет эффективно создавать пространства имен для шаблонов.

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Обработка статических файлов, добавление страниц и использование наследования шаблонов](learn-flask-visual-studio-step-03-serve-static-files-add-pages.md)

## <a name="go-deeper"></a>Дополнительные подробности

- [Flask Quickstart - Rendering Templates](https://flask.palletsprojects.com/en/1.0.x/quickstart/#rendering-templates) (Краткое руководство по Flask — отрисовка шаблонов) (flask.pocoo.org)
- Исходный код учебника на GitHub: [Microsoft/python-sample-vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)
