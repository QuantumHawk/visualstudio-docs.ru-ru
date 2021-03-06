---
title: Оценка выражения часов (ru) Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, watch expressions
- watch expressions
ms.assetid: 8317cd52-6fea-4e8f-a739-774dc06bd44b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9a239e430338e88a0be4bc35ad1c357925f7d8f5
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80738853"
---
# <a name="evaluate-a-watch-expression"></a>Оценить выражение часов
> [!IMPORTANT]
> В Visual Studio 2015 этот способ внедрения оценщиков экспресс-выражений унижается. Для получения информации о реализации оценщиков экспрессии [Managed expression evaluator sample](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)CLR [см.](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)

Когда Visual Studio готова отображать значение выражения часов, она называет [EvaluateSync,](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)который, в свою очередь, вызывает [EvaluateSync.](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) Этот процесс создает объект [IDebugProperty2,](../../extensibility/debugger/reference/idebugproperty2.md) содержащий значение и тип выражения.

В этой `IDebugParsedExpression::EvaluateSync`реализации, выражение разбирается и оценивается в то же время. Эта реализация выполняет следующие задачи:

1. Сравнивает и оценивает выражение для создания общего объекта, который содержит значение и его тип. В C, это представлено `object` как некоторое время в СЗ, `VARIANT`это представлено как .

2. Мгновения класса `CValueProperty` (называется в этом `IDebugProperty2` примере), который реализует интерфейс и хранит в классе значение, которое будет возвращено.

3. Возвращает `IDebugProperty2` интерфейс с `CValueProperty` объекта.

## <a name="managed-code"></a>Управляемый код
Это реализация управляемого `IDebugParsedExpression::EvaluateSync` кода. Метод `Tokenize` помощника разбирает выражение в дереве разбора. Функция `EvalToken` помощника преобразует маркер в значение. Функция `FindTerm` помощника повторяется через дерево разбора, требуя `EvalToken` для каждого узла, представляющего значение и применяя любые операции (дополнение или вычитание) в выражении.

```csharp
namespace EEMC
{
    public class CParsedExpression : IDebugParsedExpression
    {
        public HRESULT EvaluateSync(
            uint evalFlags,
            uint timeout,
            IDebugSymbolProvider provider,
            IDebugAddress address,
            IDebugBinder binder,
            string resultType,
            out IDebugProperty2 result)
        {
            HRESULT retval = COM.S_OK;
            this.evalFlags = evalFlags;
            this.timeout = timeout;
            this.provider = provider;
            this.address = address;
            this.binder = binder;
            this.resultType = resultType;

            try
            {
                IDebugField field = null;
                // Tokenize, then parse.
                tokens = Tokenize(expression);
                result = new CValueProperty(
                        expression,
                        (int) FindTerm(EvalToken(tokens[0], out field),1),
                        field,
                        binder);
            }
            catch (ParseException)
            {
                result = new CValueProperty(expression, "Huh?");
                retval = COM.E_INVALIDARG;
            }
            return retval;
        }
    }
}
```

## <a name="unmanaged-code"></a>Неуправляемый код
Это реализация неуправляемого `IDebugParsedExpression::EvaluateSync` кода. Функция `Evaluate` помощника разбирает и оценивает выражение, `VARIANT` возвращая удерживая полученное значение. Функция `VariantValueToProperty` помощника объединяет `VARIANT` `CValueProperty` объект в объект.

```cpp
STDMETHODIMP CParsedExpression::EvaluateSync(
    in  DWORD                 evalFlags,
    in  DWORD                 dwTimeout,
    in  IDebugSymbolProvider* pprovider,
    in  IDebugAddress*        paddress,
    in  IDebugBinder*         pbinder,
    in  BSTR                  bstrResultType,
    out IDebugProperty2**     ppproperty )
{
    // dwTimeout parameter is ignored in this implementation.
    if (pprovider == NULL)
        return E_INVALIDARG;

    if (paddress == NULL)
        return E_INVALIDARG;

    if (pbinder == NULL)
        return E_INVALIDARG;

    if (ppproperty == NULL)
        return E_INVALIDARG;
    else
        *ppproperty = 0;

    HRESULT hr;
    VARIANT value;
    BSTR    bstrErrorMessage = NULL;
    hr = ::Evaluate( pprovider,
                     paddress,
                     pbinder,
                     m_expr,
                     &bstrErrorMessage,
                     &value );
    if (hr != S_OK)
    {
        if (bstrErrorMessage == NULL)
            return hr;

        //we can display better messages ourselves.
        HRESULT hrLocal = S_OK;
        VARIANT varType;
        VARIANT varErrorMessage;

        VariantInit( &varType );
        VariantInit( &varErrorMessage );
        varErrorMessage.vt      = VT_BSTR;
        varErrorMessage.bstrVal = bstrErrorMessage;

        CValueProperty* valueProperty = new CValueProperty();
        if (valueProperty != NULL)
        {
            hrLocal = valueProperty->Init(m_expr, varType, varErrorMessage);
            if (SUCCEEDED(hrLocal))
            {
                hrLocal = valueProperty->QueryInterface( IID_IDebugProperty2,
                        reinterpret_cast<void**>(ppproperty) );
            }
        }

        VariantClear(&varType);
        VariantClear(&varErrorMessage); //frees BSTR
        if (!valueProperty)
            return hr;
        valueProperty->Release();
        if (FAILED(hrLocal))
            return hr;
    }
    else
    {
        if (bstrErrorMessage != NULL)
            SysFreeString(bstrErrorMessage);

        hr = VariantValueToProperty( pprovider,
                                     paddress,
                                     pbinder,
                                     m_radix,
                                     m_expr,
                                     value,
                                     ppproperty );
        VariantClear(&value);
        if (FAILED(hr))
            return hr;
    }

    return S_OK;
}
```

## <a name="see-also"></a>См. также
- [Оценить выражение окна часов](../../extensibility/debugger/evaluating-a-watch-window-expression.md)
- [Пример реализации оценки выражений](../../extensibility/debugger/sample-implementation-of-expression-evaluation.md)
