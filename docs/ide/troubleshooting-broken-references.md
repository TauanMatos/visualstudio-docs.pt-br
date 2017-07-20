---
title: "Solucionando problemas de referências desfeitas | Microsoft Docs"
ms.custom: 
ms.date: 03/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual C# projects, references
- Visual Basic projects, references
- troubleshooting references
- referencing files from projects
- referencing components, troubleshooting
ms.assetid: 00a9ade9-652e-40de-8ada-85f63cd183ee
caps.latest.revision: 15
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3d32d11a430227800cb3ed53831a9565eb6adeb3
ms.openlocfilehash: 61a074110e0a3730c971c319f98498324868067d
ms.contentlocale: pt-br
ms.lasthandoff: 05/30/2017

---
# Solução de problemas de referências desfeitas
<a id="troubleshoot-broken-references" class="xliff"></a>
Se o aplicativo tentar usar uma referência desfeita, um erro de exceção será gerado. A incapacidade de localizar o componente referenciado é o gatilho primário do erro, mas existem várias situações em que uma referência pode ser considerada desfeita. Essas instâncias são mostradas na seguinte lista:  

-   O caminho de referência do projeto está incorreto ou incompleto.  

-   O arquivo que está sendo referenciado foi excluído.  

-   O arquivo que está sendo referenciado foi renomeado.  

-   A conexão de rede ou a autenticação falhou.  

-   A referência indica um componente COM que não está instalado no computador.  

 Veja a seguir as soluções para esses problemas.  

> [!NOTE]
>  Os arquivos em assemblies são referenciados com caminhos absolutos no arquivo de projeto. Portanto, é possível que os usuários que trabalham em um ambiente com vários desenvolvedores tenham um assembly referenciado ausente no ambiente local. Para evitar esses erros, nesses casos, é melhor adicionar referências projeto a projeto. Para obter mais informações, consulte [Programando com Assemblies](/dotnet/framework/app-domains/programming-with-assemblies).

## O caminho de referência está incorreto
<a id="reference-path-is-incorrect" class="xliff"></a>  
 Se os projetos forem compartilhados em computadores diferentes, algumas referências poderão não ser encontradas quando um componente estiver localizado em um diretório diferente de cada computador. As referências são armazenadas no nome do arquivo de componente (por exemplo, MyComponent). Quando uma referência é adicionada a um projeto, o local da pasta do arquivo de componente (por exemplo, C:\MyComponents\\) é acrescentado à propriedade do projeto **ReferencePath**.  

 Quando o projeto é aberto, ele tenta localizar esses arquivos de componentes referenciados procurando nos diretórios no caminho de referência. Se o projeto é aberto em um computador que armazena o componente em um diretório diferente, como D:\MyComponents\\, a referência não pode ser encontrada e um erro é exibido na Lista de Tarefas.  

 Para corrigir esse problema, é possível excluir a referência desfeita e substituí-la usando a caixa de diálogo Adicionar Referência. Outra solução é usar o item **Caminho de Referência** nas páginas de propriedades do projeto e modificar as pastas na lista para que elas apontem para os locais corretos. A propriedade **Caminho de Referência** é persistida para cada usuário em cada computador. Portanto, a modificação do caminho de referência não afeta outros usuários do projeto.  

> [!TIP]
>  Referências projeto a projeto não apresentam esses problemas. Por esse motivo, se possível, use-as, em vez de referências de arquivo.  

#### Para corrigir uma referência de projeto desfeita corrigindo o caminho de referência
<a id="to-fix-a-broken-project-reference-by-correcting-the-reference-path" class="xliff"></a>  

1.  No **Gerenciador de Soluções**, clique com o botão direito do mouse no nó do projeto e clique em **Propriedades**.  

2.  O **Designer de Projeto** é exibido.  

3.  Se você estiver usando o Visual Basic, selecione a página **Referências** e clique no botão **Caminhos de Referência**. Na caixa de diálogo **Caminhos de Referência**, digite o caminho da pasta que contém o item que você deseja referenciar no campo **Pasta** e, em seguida, clique no botão **Adicionar Pasta**.  

     -ou-  

     Se estiver usando o Visual C#, selecione a página **Caminhos de Referência**. No campo **Pasta**, digite o caminho da pasta que contém o item que você deseja referenciar e, em seguida, clique no botão **Adicionar Pasta**.  

## O arquivo referenciado foi excluído
<a id="referenced-file-has-been-deleted" class="xliff"></a>  
 É possível que o arquivo que está sendo referenciado tenha sido excluído e não exista mais na unidade.  

#### Para corrigir uma referência de projeto desfeita de um arquivo que não existe mais na unidade
<a id="to-fix-a-broken-project-reference-for-a-file-that-no-longer-exists-on-your-drive" class="xliff"></a>  

-   Exclua a referência.  

-   Se a referência existir em outro local do computador, leia-a nesse local.  

## O arquivo referenciado foi renomeado
<a id="referenced-file-has-been-renamed" class="xliff"></a>  
 É possível que o arquivo que está sendo referenciado tenha sido renomeado.  

#### Para corrigir uma referência desfeita de um arquivo que foi renomeado
<a id="to-fix-a-broken-reference-for-a-file-that-has-been-renamed" class="xliff"></a>  

-   Exclua a referência e, em seguida, adicione uma referência ao arquivo renomeado.  

-   Se a referência existir em outro local do computador, será necessário lê-la nesse local.

## A conexão de rede ou a autenticação falhou
<a id="network-connection-or-authentication-has-failed" class="xliff"></a>  
 Pode haver várias causas possíveis para arquivos inacessíveis: uma conexão de rede ou uma autenticação com falha, por exemplo. Cada causa pode ter meios exclusivos de recuperação; por exemplo, você poderá precisar contatar o administrador local para acessar os recursos necessários. No entanto, a exclusão da referência e a correção do código que a usou é sempre uma opção.

## O componente COM não está instalado no computador
<a id="com-component-is-not-installed-on-computer" class="xliff"></a>  
 Se um usuário tiver adicionado uma referência a um componente COM e um segundo usuário tentar executar o código em um computador que não tem esse componente instalado, o segundo usuário receberá um erro informando de que a referência está desfeita. Instalar o componente no segundo computador corrigirá o erro. Para obter mais informações sobre como usar referências a componentes COM nos projetos, consulte [Interoperabilidade COM em aplicativos .NET Framework](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications).  

## Consulte também
<a id="see-also" class="xliff"></a>  
 [Página Referências, Designer de Projeto (Visual Basic)](../ide/reference/references-page-project-designer-visual-basic.md)   
