---
title: Consultar Editar consulta salvar (VSPackage de controle de origem) | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- QEQS events
- Query Edit Query Save events
- source control packages, Query Edit Query Save events
ms.assetid: c360d2ad-fe42-4d65-899d-d1588cc8a322
caps.latest.revision: 17
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
ms.openlocfilehash: da34c3bd33bdff66a340bad43d0cce3266153cf3
ms.lasthandoff: 02/22/2017

---
# <a name="query-edit-query-save-source-control-vspackage"></a>Editar consulta salvar (VSPackage de controle de origem)
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]editores podem transmitir eventos de consulta Editar consulta salvar (QEQS). [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Stub de controle de origem implementa o serviço QEQS, para que ele é o destinatário de eventos QEQS. Esses eventos, em seguida, são delegados ao controle de origem ativa atualmente VSPackage. O controle de origem ativa VSPackage implementa o <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>e seus métodos.</xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> Os métodos do `IVsQueryEditQuerySave2` interface costumam ser chamados imediatamente antes de um documento é editado pela primeira vez e imediatamente antes de um documento é salvo.  
  
## <a name="queryeditquerysave-events"></a>Eventos de QueryEditQuerySave  
 O controle de origem VSPackage deve tratar os eventos QEQS Implementando o `IVsQueryEditQuerySave2` interface e os métodos necessários. Abaixo está uma breve descrição dos dois métodos que o VSPackage deve implementar no mínimo. A implementação real deve estar de acordo com a lógica do modelo de controle de origem.  
  
### <a name="queryeditfiles-method"></a>Método QueryEditFiles  
 O <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>é chamado quando qualquer editor ou projeto quer modificar um arquivo.</xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> Idealmente, esse método é chamado *antes de* o arquivo é modificado e quando um arquivo é salvo. Quando invocado, o `IVsQueryEditQuerySave2::QueryEditFiles` método verifica se os arquivos de determinado estão sob controle de origem, se eles precisam fazer check-out e se eles podem ser recarregados. Se circunstâncias impedir que os arquivos que está sendo editado, o `IVsQueryEditQuerySave2::QueryEditFiles` método informa o programa de chamada para cancelar a edição. Também é possível que o chamador pode especificar um modo de chamada. No modo "silencioso", este método executa a ação somente se não causa nenhuma interface do usuário seja exibido. Se a interface do usuário é inevitável, um sinalizador deve ser retornado para indicar o problema.  
  
 O método se comporta de forma transacional; ou seja, se a edição será cancelada em um único arquivo, a edição é cancelada para todos os arquivos. Por outro lado, se a edição é permitida, é permitido para todos os arquivos. Se esse método permite a edição de uma vez para um determinado conjunto de arquivos, ele sempre deve permitir a edição em chamadas subsequentes para o mesmo conjunto de arquivos. Permitir edição loop continuará até que os arquivos são fechados, salvo e recarregados. até que alteram seus atributos (Propriedades). ou até que o pacote de controle de origem é alterado. Casos a serem considerados na implementação de `IVsQueryEditQuerySave2::QueryEditFiles` método incluir vários arquivos, arquivos especiais, cancelar de usuário e edições de memória.  
  
### <a name="querysavefiles-method"></a>Método QuerySaveFiles  
 O <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>é chamado quando qualquer editor ou projeto precisa salvar um conjunto de arquivos.</xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> Quando invocado, o `IVsQueryEditQuerySave2::QuerySaveFiles` método verifica se os arquivos de determinado são somente leitura e que estão sob controle de origem. Se os arquivos precisam fazer check-out, a chamada é delegada para o pacote de controle de origem. Se circunstâncias impedir que os arquivos sejam salvos, o `IVsQueryEditQuerySave2::QuerySaveFiles` método deve informar o editor para cancelar a gravação. Assim como acontece com o `IVsQueryEditQuerySave2::QueryEditFiles` método, é possível que o chamador pode especificar um modo de chamada. No modo "silencioso", este método executa a ação somente se não causa nenhuma interface do usuário seja exibido. Se a interface do usuário é inevitável, um sinalizador deve ser retornado para indicar o problema.  
  
 Esse método deve se comportar de forma transacional; ou seja, se o salvamento for cancelado em um único arquivo, o salvamento é cancelado para todos os arquivos. Por outro lado, se o salvamento for permitido, ele deve ser permitido para todos os arquivos. Assim como acontece com o `IVsQueryEditQuerySave2::QueryEditFiles` casos a serem considerados na implementação de um método, o `IVsQueryEditQuerySave2::QuerySaveFiles` método incluir vários arquivos, arquivos especiais, cancelar de usuário e edições de memória.  
  
## <a name="see-also"></a>Consulte também  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2></xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>