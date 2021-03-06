---
title: Возможности доступа
description: В этой статье описаны специальные возможности в Visual Studio для Mac и способы их включения.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 08/15/2017
ms.assetid: 2C4AAC2E-3B4A-4496-8BE0-1F5A7F81D1CA
ms.openlocfilehash: c0f056643a8cea0c9a5eca9801d2bd008e0793a8
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2020
ms.locfileid: "79306659"
---
# <a name="accessibility"></a>Возможности доступа

Кроме функций и служебных программ для macOS, Visual Studio для Mac предоставляет дополнительные возможности для людей с ограниченными возможностями:

- увеличение текста в панелях решения и редактора;
- настройка размера текста в редакторах;
- настройка цвета в редакторах;
- настройка сочетаний клавиш;
- автозавершение методов и параметров.

Дополнительные сведения о специальных возможностях для macOS см. на [веб-сайте Apple](https://www.apple.com/accessibility/mac/).

## <a name="using-accessibility-features-in-visual-studio-for-mac"></a>Использование специальных возможностей в Visual Studio для Mac

Специальные возможности в Visual Studio для Mac отключены по умолчанию. Включить их можно так:

1. Последовательно выберите **Visual Studio > Preferences > Other > Accessibility** (Visual Studio > Параметры > Другое > Специальные возможности).

2. Установите флажок **Enable Accessibility** (Включить специальные возможности), как показано ниже:

    ![Установка флажка специальных возможностей](media/accessibility-image1.png)

3. Нажмите кнопку **Restart Visual Studio** (Перезапустить Visual Studio), чтобы изменения вступили в силу.

Также включить специальные возможности можно в командной строке. Для этого введите следующую команду в окне терминала:

```bash
defaults write com.microsoft.visual-studio com.monodevelop.AccessibilityEnabled 1
```

Включив специальные возможности, перезапустите Visual Studio.

## <a name="how-to-use-keyboard-navigation"></a>Навигация с помощью клавиатуры

Навигацию с помощью клавиатуры можно включить, выбрав **System Preferences > Keyboard > Shortcuts** (Системные настройки > Клавиатура > Ярлыки) и установив для параметра Full Keyboard Access (Полный доступ с клавиатуры) значение **All Controls** (Все элементы управления):

![Панель системных настроек в macOS](media/accessibility-image2.png)

Настройка параметра доступа с клавиатуры включает прямоугольник фокуса. Теперь элементы управления можно выбирать следующим образом:

- используя клавишу TAB для перехода по элементам управления вперед;
- используя клавиши SHIFT+TAB для перехода по элементам управления назад;
- используя клавиши со стрелками для перемещения между элементами управления в направлении стрелки.

Нажатие клавиши ПРОБЕЛ активирует элемент управления с наведенным фокусом.

## <a name="how-to-enable-and-use-voice-over"></a>Включение и использование функции VoiceOver

Чтобы включить или отключить функцию VoiceOver, нажмите клавиши **CMD+F5**.

Для навигации между командами пользовательского интерфейса VoiceOver используйте следующие команды:

- Перемещение курсора VoiceOver между элементами управления: **CTRL+ALT+СТРЕЛКА ВЛЕВО или СТРЕЛКА ВПРАВО**.

   VoiceOver считывает имя элементов управления и некоторые сведения о них, а также определяет возможные действия с ними.

- Ввод групп и элементов управления (например, панели решения, панели инструментов и других панелей): **CTRL+ALT+SHIFT+СТРЕЛКА ВНИЗ**.

   Перемещаться в пределах элемента управления можно с помощью клавиш **CTRL+ALT+СТРЕЛКИ**.

Общие сведения об использовании VoiceOver в macOS см. в следующих руководствах:

- [VoiceOver Getting Started Guide](https://help.apple.com/voiceover/info/guide/10.12/) (Руководство по началу работы с VoiceOver)
- [OS X VoiceOver Commands](https://lab.dotjay.com/notes/voiceover-commands/) (Команды VoiceOver в OS X)

## <a name="see-also"></a>См. также раздел

- [Специальные возможности Visual Studio (в Windows)](/visualstudio/ide/reference/accessibility-features-of-visual-studio)