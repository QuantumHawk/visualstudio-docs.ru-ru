---
title: Варианты точечной, билинейной, трилинейной и анизотропной фильтрации текстур
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 57d14fc9-b5f7-45ee-9717-48086886742d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 314ec61da7ed61cc8bdd573e201d98a53862a32c
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "66262924"
---
# <a name="point-bilinear-trilinear-and-anisotropic-texture-filtering-variants"></a>Варианты точечной, билинейной, трилинейной и анизотропной фильтрации текстур
Переопределяет режим фильтрации для соответствующих дискретизаторов текстур.

## <a name="interpretation"></a>Интерпретация
 Различные способы дискретизации текстур по-разному сказываются на производительности и качестве изображения. Ниже перечислены режимы фильтрации в порядке возрастания влияния на производительность и качества изображения:

1. точечная фильтрация (наименьшие затраты и качество изображения);

2. билинейная фильтрация;

3. трилинейная фильтрация;

4. анизотропная фильтрация (наибольшие затраты и наивысшее качество изображения).

   Если потери производительности для каждого варианта значительны или растут при использовании более ресурсозатратных режимов фильтрации, можно сравнить эти потери со степенью повышения качества изображения. В соответствии с результатами оценки можно признать допустимыми потери производительности, за счет которых повышается качество изображения, либо снизить качество изображения, чтобы увеличить частоту кадров или повысить производительность для решения других задач.

   Если потери производительности оказываются пренебрежимо малы или стабильны вне зависимости от режима фильтрации, например, если GPU имеет очень высокую пропускную способность шейдеров и широкую полосу пропускания памяти, рекомендуем использовать анизотропную фильтрацию, чтобы обеспечить максимальное качество изображения.

## <a name="remarks"></a>Примечания
 Эти варианты переопределяют состояния дискретизатора при вызове `ID3D11DeviceContext::PSSetSamplers`, при котором режим фильтрации предоставленного приложением дискретизатора имеет одно из следующих значений:

- `D3D11_FILTER_MIN_MAG_MIP_POINT`

- `D3D11_FILTER_MIN_MAG_POINT_MIP_LINEAR`

- `D3D11_FILTER_MIN_POINT_MAG_LINEAR_MIP_POINT`

- `D3D11_FILTER_MIN_POINT_MAG_MIP_LINEAR`

- `D3D11_FILTER_MIN_LINEAR_MAG_MIP_POINT`

- `D3D11_FILTER_MIN_LINEAR_MAG_POINT_MIP_LINEAR`

- `D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT`

- `D3D11_FILTER_MIN_MAG_MIP_LINEAR`

- `D3D11_FILTER_ANISOTROPIC`

  Для варианта **Точечная фильтрация текстур** определенный приложением режим фильтрации заменяется на `D3D11_FILTER_MIN_MAG_MIP_POINT`, для варианта **Билинейная фильтрация текстур** он заменяется на `D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT`, а для варианта **Трилинейная фильтрация текстур** он заменяется на `D3D11_FILTER_MIN_MAG_MIP_LINEAR`.

  Для варианта **Анизотропная фильтрация текстур** определенный приложением режим фильтрации заменяется на `D3D11_FILTER_ANISOTROPIC`, а свойству "Максимальная анизотропия" присваивается значение 16.

## <a name="restrictions-and-limitations"></a>Ограничения
 В Direct3D на функциональном уровне 9.1 максимальная анизотропия равна 2x. Так как вариант **Анизотропная фильтрация текстур** пытается использовать исключительно 16-кратную анизотропию, воспроизведение завершается сбоем при запуске анализа кадров на устройстве с функциональным уровнем 9.1. К современным устройствам, на которые распространяется это ограничение, относятся планшеты Surface RT и Surface 2 с ОС Windows на основе архитектуры ARM. Ограничение также может распространяться на более старые GPU, которые, однако, выходят из употребления и встречаются все реже.

## <a name="example"></a>Пример
 Вариант **Точечная фильтрация текстур** можно воспроизвести с помощью следующего кода:

```cpp
D3D11_SAMPLER_DESC sampler_description;

// ... other sampler description setup ...

sampler_description.Filter = D3D11_FILTER_MIN_MAG_MIP_POINT;

d3d_device->CreateSamplerState(&sampler_desc, &sampler);
d3d_context->PSSetSamplers(0, 1, &sampler
```

## <a name="example"></a>Пример
 Вариант **Билинейная фильтрация текстур** можно воспроизвести с помощью следующего кода:

```cpp
D3D11_SAMPLER_DESC sampler_description;

// ... other sampler description setup ...

sampler_description.Filter = D3D11_FILTER_MIN_MAG_LINEAR_MIP_POINT;

d3d_device->CreateSamplerState(&sampler_desc, &sampler);
d3d_context->PSSetSamplers(0, 1, &sampler
```

## <a name="example"></a>Пример
 Вариант **Трилинейная фильтрация текстур** можно воспроизвести с помощью следующего кода:

```cpp
D3D11_SAMPLER_DESC sampler_description;

// ... other sampler description setup ...

sampler_description.Filter = D3D11_FILTER_MIN_MAG_MIP_LINEAR;

d3d_device->CreateSamplerState(&sampler_desc, &sampler);
d3d_context->PSSetSamplers(0, 1, &sampler
```

## <a name="example"></a>Пример
 Вариант **Анизотропная фильтрация текстур** можно воспроизвести с помощью следующего кода:

```cpp
D3D11_SAMPLER_DESC sampler_description;

// ... other sampler description setup ...

sampler_description.Filter = D3D11_FILTER_ANISOTROPIC;
sampler_description.MaxAnisotropy = 16;

d3d_device->CreateSamplerState(&sampler_desc, &sampler);
d3d_context->PSSetSamplers(0, 1, &sampler
```
