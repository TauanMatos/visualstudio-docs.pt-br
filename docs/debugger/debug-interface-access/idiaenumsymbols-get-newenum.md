---
title: "IDiaEnumSymbols::get__NewEnum | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Método IDiaEnumSymbols::get__NewEnum"
ms.assetid: 879609ea-8e5a-4fa3-afa6-d24870fb4392
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaEnumSymbols::get__NewEnum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Recupera o <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> versão deste enumerador.  
  
## Sintaxe  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### Parâmetros  
 pRetVal  
 \[out\] Retorna o `IUnknown` interface que representa o <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> versão deste enumerador.  
  
## Valor de retorno  
 Se bem\-sucedida, retorna `S_OK`; Caso contrário, retorna um código de erro.  
  
## Consulte também  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)