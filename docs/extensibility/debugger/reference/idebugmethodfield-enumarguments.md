---
title: IDebugMethodField::EnumArguments | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugMethodField::EnumArguments
helpviewer_keywords:
- IDebugMethodField::EnumArguments method
ms.assetid: 3ab55488-2437-4ff6-a9ae-78ea6d7b23a8
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 588dc55a0648be494f2c2fc0f82937c0efded701
ms.lasthandoff: 02/22/2017

---
# <a name="idebugmethodfieldenumarguments"></a>IDebugMethodField::EnumArguments
Cria um enumerador para o tipo de cada argumento necessário para chamar o método.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
HRESULT EnumArguments(   
   IEnumDebugFields** ppParams  
);  
```  
  
```c#  
int EnumArguments(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ppParams`  
 [out] Retorna um [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objeto que representa a lista de tipos de argumento. Retorna um valor nulo se não houver nenhum argumento.  
  
## <a name="return-value"></a>Valor de retorno  
 Se for bem-sucedido, Retorna S_OK ou retorna S_FALSE se não houver nenhum argumento. Caso contrário, retornará um código de erro.  
  
## <a name="remarks"></a>Comentários  
 Cada elemento é um [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objeto que representa os tipos de cada parâmetro. Chamar o [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) método para recuperar informações sobre o tipo de cada parâmetro.  
  
 Se o nome do parâmetro é necessário juntamente com o tipo, em seguida, chame o [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md) método.  
  
## <a name="see-also"></a>Consulte também  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)