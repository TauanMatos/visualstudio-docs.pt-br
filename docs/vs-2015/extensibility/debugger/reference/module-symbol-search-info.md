---
title: MODULE_SYMBOL_SEARCH_INFO | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MODULE_SYMBOL_SEARCH_INFO
helpviewer_keywords:
- MODULE_SYMBOL_SEARCH_INFO structure
ms.assetid: 432aff03-08a5-4c5a-b2d5-e212090fc70a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 074e837a1c0449420d7042539fb4c8dfa0396fe6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47467881"
---
# <a name="modulesymbolsearchinfo"></a>MODULE_SYMBOL_SEARCH_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [MODULE_SYMBOL_SEARCH_INFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/module-symbol-search-info).  
  
Contém informações de status sobre os caminhos de pesquisa de símbolo que foram pesquisados.  
  
## <a name="syntax"></a>Sintaxe  
  
```cpp#  
typedef struct _tagSYMBOL_SEARCH_INFO  
{  
   SYMBOL_SEARCH_INFO_FIELDS dwValidFields;  
   BSTR                      bstrVerboseSearchInfo;  
} MODULE_SYMBOL_SEARCH_INFO;  
```  
  
```csharp  
public struct MODULE_SYMBOL_SEARCH_INFO {  
   public uint   dwValidFields;  
   public string bstrVerboseSearchInfo;  
}  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `dwValidFields`  
 Uma combinação de sinalizadores do [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) enumeração que especifica o tipo de informações de pesquisa descritos nessa estrutura.  
  
 `bstrVerboseSearchInfo`  
 Caminho de pesquisa e os resultados concatenados em uma única cadeia de caracteres.  
  
## <a name="remarks"></a>Comentários  
 Essa estrutura é retornada de uma chamada para o [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md) método.  
  
 Se o `bstrVerboseSearchInfo` campo não estiver vazio, ele contém uma lista de caminhos pesquisados e os resultados da pesquisa. A lista é formatada com um caminho, seguido por reticências (""...), seguidas pelo resultado. Se houver mais de um par de resultado do caminho, em seguida, cada par é separado por um par de "\r\n" (carro-retorno/avanço de linha). O padrão tem esta aparência:  
  
 \<caminho >... \<resultado > \r\n\<caminho >... \<resultado > \r\n\<caminho >... \<resultado >  
  
 Observe que a última entrada não tem uma sequência \r\n.  
  
 Aqui está uma possível `bstrVerboseSearchInfo` cadeia de caracteres que foi enviada para saída padrão.  
  
 `c:\symbols\user32.pdb... File not found.`  
  
 `c:\winnt\symbols\user32.pdb... Version does not match.`  
  
 `\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symbols loaded.`  
  
## <a name="requirements"></a>Requisitos  
 Cabeçalho: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Consulte também  
 [Estruturas e uniões](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)
