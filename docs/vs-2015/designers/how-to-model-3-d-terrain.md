---
title: Практическое руководство. Моделирование трехмерного ландшафта | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ab202ed97ce2056313eb661d51d7150bb9689829
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72664413"
---
# <a name="how-to-model-3-d-terrain"></a>Практическое руководство. Моделирование трехмерного ландшафта
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

В этом документе рассматривается, как с помощью редактора моделей создать простую модель трехмерного ландшафта.

 В этом документе описаны следующие действия.

- Добавление объектов в сцену

- Выбор поверхностей и точек

- Перенос выбранных областей

- Работа с инструментом **Разделить поверхность**

- Заключение объекта в рамку в области конструктора

## <a name="creating-a-3-d-terrain-model"></a>Создание модели трехмерного ландшафта
 Трехмерный ландшафт можно получить, разделив плоскость для создания дополнительных поверхностей и управляя их вершинами для формирования требуемых компонентов ландшафта.

 В итоге модель должна выглядеть так:

 ![3&#45;-я сцена, показывающий модель ландшафта](../designers/media/digit-terrain-model.png "Digit-ландшафта-Model")

 Перед началом убедитесь, что отображаются окно **Свойства** и **Панель элементов**.

#### <a name="to-create-a-3-d-terrain-model"></a>Создание модели трехмерного ландшафта

1. Создайте трехмерную модель, с которой вы будете работать. О том, как добавить в проект модель, см. в подразделе "Начало работы" раздела [Редактор моделей](../designers/model-editor.md).

2. Добавьте в сцену плоскость. В окне **Панель элементов** в разделе **Фигуры** выберите **Плоскость** и переместите элемент в область конструктора.

   > [!TIP]
   > Для упрощения работы с объектом плоскости можно заключить его в рамку в области конструктора. В режиме **Выбрать** выберите объект плоскости, а затем на панели инструментов редактора моделей нажмите кнопку **Frame Object** (Заключить объект в рамку).

3. Перейдите в режим выбора поверхностей. На панели инструментов редактора моделей выберите **Выбор поверхности**.

4. Разделите плоскость. В режиме выбора поверхностей выберите плоскость один раз, чтобы активировать ее для выделения, после чего выберите ее снова, чтобы выделить ее единственную поверхность. На панели инструментов редактора моделей выберите **Разделить поверхность**. На плоскость добавляются новые вершины, разбивающие ее на четыре одинаковые по размеру части.

5. Создайте больше промежуточных частей. Когда новые поверхности выбраны, выберите **Разделить поверхность** еще два раза. В результате получается 64 поверхностей. Создав еще больше промежуточных частей, можно сделать ландшафт более детальным.

6. Перейдите в режим выбора точек. На панели инструментов редактора моделей выберите **Выбор точки**.

7. Измените точку, чтобы создать компонент ландшафта. В режиме выбора точек выберите одну из точек, а затем на панели инструментов редактора моделей выберите инструмент **Перенести**. В области конструктора отображается рамка, представляющая точку. Используйте зеленую стрелку, чтобы переместить поле и тем самым изменить высоту точки. Повторите этот шаг для разных точек, чтобы сформировать требуемые компоненты ландшафта.

   > [!TIP]
   > Можно выбрать сразу несколько точек, чтобы изменить их одинаковым образом.

   Модель ландшафта завершена. Ниже показана окончательная версия модели с примененным к ней затенением по методу Фонга:

   ![3&#45;-я сцена, показывающий модель ландшафта](../designers/media/digit-terrain-model.png "Digit-ландшафта-Model")

   Эту модель ландшафта можно использовать для демонстрации эффекта шейдера градиента, описанного в разделе [Практическое руководство. Создание основанного на геометрии шейдера градиента](../designers/how-to-create-a-geometry-based-gradient-shader.md).

## <a name="see-also"></a>См. также раздел
 [Редактор моделей](../designers/model-editor.md)
