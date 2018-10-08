---
title: Gravação da função de gancho de depuração | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5761b0a32e7739a5611f2d3d07183f0c529fc60c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476173"
---
# <a name="debug-hook-function-writing"></a>Gravação da função de gancho de depuração
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [gravação da função de gancho de depuração](https://docs.microsoft.com/visualstudio/debugger/debug-hook-function-writing).  
  
Esta seção descreve várias funções de gancho de depuração personalizadas que você pode escrever que permitem inserir seu código em alguns pontos predefinidos no processamento normal do depurador.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Funções de gancho do bloco de clientes](../debugger/client-block-hook-functions.md)  
 Fornece orientação e um protótipo para escrever funções que validam ou reportam o conteúdo dos dados armazenados nos blocos _CLIENT_BLOCK.  
  
 [Funções de gancho de alocação](../debugger/allocation-hook-functions.md)  
 Define uma função de gancho de alocação, explora seus usos diferentes, indica limitações e fornece um protótipo.  
  
 [Ganchos de alocação e alocações de memória CRT](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)  
 Descreve a limitação de funções de gancho de alocação de ignorar explicitamente blocos de `_CRT_BLOCK` se eles fizerem chamadas para as funções da biblioteca em tempo de execução C que alocam a memória interna. Este tópico também listará as consequências se seu gancho de alocação não ignorar `_CRT_BLOCK` blocos (com exemplos) e como alterar a alocação padrão de função de gancho, **CrtDefaultAllocHook**.  
  
 [Funções de gancho de relatório](../debugger/report-hook-functions.md)  
 Discute `_CrtSetReportHook`, que você pode usar para filtrar relatórios para enfatizar tipos específicos de alocações. Este tópico também fornece um protótipo.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Técnicas de depuração CRT](../debugger/crt-debugging-techniques.md)  
 Links para técnicas de depuração para a biblioteca em tempo de execução C, incluindo o uso da biblioteca de depuração do CRT, macros para relatório, diferenças entre `malloc` e `_malloc_dbg`, escrevendo funções de gancho de depuração, e o heap de depuração do CRT.


