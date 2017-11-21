---
title: "Método SetWefProcessId | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 404eec23-a67e-4f5b-b27d-86651f08be03
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0821c799a4d6385997704724c00a2aff4669eb17
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2017
---
# <a name="setwefprocessid-method"></a>Método SetWefProcessId
  Fornece o identificador do processo que executará o conteúdo da estrutura de extensões da Web (WEF).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT SetWefProcessId(  
    [in] DWORD dwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|*dwProcessId*|O identificador do processo que será usado para executar o WEF conteúdo.|  
  
## <a name="return-value"></a>Valor de retorno  
 Um valor HRESULT que indica se o método foi concluída com êxito.  
  
## <a name="remarks"></a>Comentários  
 Esse método deve ser chamado depois que o processo de conteúdo WEF é criado, mas antes de qualquer conteúdo WEF é executado.  
  
 Se você quiser que o ambiente de desenvolvimento para anexar um depurador ao processo WEF conteúdo, o ambiente deve executar esta operação em sua implementação deste método.  
  
  