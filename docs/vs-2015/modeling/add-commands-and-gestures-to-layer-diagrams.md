---
title: Adicionar comandos e gestos a diagramas de camada | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- layer diagrams, adding custom commands
- layer diagrams, adding custom gestures
ms.assetid: ac9c417b-0b40-4a90-86f5-ee3cbdce030b
caps.latest.revision: 40
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: ae57d950b20fc6e342056b8c89738fa895c48c28
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733381"
---
# <a name="add-commands-and-gestures-to-layer-diagrams"></a>Adicionar comandos e gestos a diagramas de camada
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Você pode definir comandos de menu de contexto e manipuladores do gesto em diagramas de camada no Visual Studio. Você pode empacotar essas extensões em um Visual Studio Integration extensão (VSIX) que você pode distribuir a outros usuários do Visual Studio.  
  
 Você pode definir vários manipuladores de comando e de gesto no mesmo projeto do Visual Studio se você quiser. Você também pode combinar vários desses projetos em um VSIX. Por exemplo, você pode definir um único VSIX que inclui comandos de camada, uma linguagem específica de domínio e comandos para diagramas de UML.  
  
> [!NOTE]
>  Você também pode personalizar a validação da arquitetura, na origem dos quais usuários o código é comparado com diagramas de camada. Você deve definir a validação de arquitetura em um projeto separado do Visual Studio. Você pode adicioná-lo ao mesmo VSIX que outras extensões. Para obter mais informações, consulte [adicionar validação de arquitetura personalizada a diagramas de camada](../modeling/add-custom-architecture-validation-to-layer-diagrams.md).  
  
## <a name="requirements"></a>Requisitos  
 Ver [requisitos de](../modeling/extend-layer-diagrams.md#prereqs).  
  
## <a name="defining-a-command-or-gesture-in-a-new-vsix"></a>Definindo um comando ou gesto em um novo VSIX  
 O método mais rápido de criação de uma extensão é usar o modelo de projeto. Isso coloca o código e o manifesto do VSIX no mesmo projeto.  
  
#### <a name="to-define-an-extension-by-using-a-project-template"></a>Para definir uma extensão usando um modelo de projeto  
  
1. Criar um projeto em uma nova solução, usando o **novo projeto** comando as **arquivo** menu.  
  
2. No **novo projeto** caixa de diálogo **projetos de modelagem**, selecione **extensão de comando do Designer de camada** ou **extensão de gesto do Designer de camada** .  
  
    O modelo cria um projeto que contém um pequeno exemplo de trabalho.  
  
3. Para testar a extensão, pressione **CTRL+F5** ou **F5**.  
  
    Uma instância experimental do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] é iniciado. Nesse caso, crie um diagrama de camada. Sua extensão de comando ou gesto deve trabalhar neste diagrama.  
  
4. Feche a instância experimental e modifique o código de exemplo. Para obter mais informações, consulte [navegar e atualizar modelos no código do programa de camada](../modeling/navigate-and-update-layer-models-in-program-code.md).  
  
5. Você pode adicionar mais manipuladores de comando ou gesto no mesmo projeto. Para obter mais informações, consulte uma das seções a seguir:  
  
    [Definindo um comando de Menu](#command)  
  
    [Definindo um manipulador de gesto](#gesture)  
  
6. Para instalar a extensão na instância principal do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], ou em outro computador, localize o **. VSIX** de arquivos em *bin\\*. Copie-o para o computador no qual você deseja instalá-lo e, em seguida, clique duas vezes nele. Para desinstalar, use **extensões e atualizações** sobre o **ferramentas** menu.  
  
## <a name="adding-a-command-or-gesture-to-a-separate-vsix"></a>Adicionando um comando ou gesto a um VSIX separado  
 Se você quiser criar um VSIX que contém comandos, validadores de camada e outras extensões, é recomendável que você crie um projeto para definir o VSIX e projetos separados para os manipuladores. Para obter informações sobre outros tipos de extensão de modelagem, consulte [modelos e diagramas UML estender](../modeling/extend-uml-models-and-diagrams.md).  
  
#### <a name="to-add-layer-extensions-to-a-separate-vsix"></a>Para adicionar extensões de camada a um VSIX separado  
  
1.  Crie um projeto de biblioteca de classes em uma solução nova ou existente do Visual Studio. No **novo projeto** caixa de diálogo, clique em **Visual c#** e, em seguida, clique em **biblioteca de classes**. Este projeto irá conter comando ou classes de manipulador de gesto.  
  
    > [!NOTE]
    >  Você pode definir mais de uma classe de manipulador de gesto ou comando em uma biblioteca de classes, mas você deve definir classes de validação de camada em uma biblioteca de classes separado.  
  
2.  Identifique ou crie um projeto de VSIX em sua solução. Um projeto do VSIX contém um arquivo chamado **vsixmanifest**. Para adicionar um projeto VSIX:  
  
    1.  No **novo projeto** diálogo caixa, expanda **Visual c#**, em seguida, clique em **extensibilidade**e, em seguida, clique em **projeto VSIX**.  
  
    2.  No Gerenciador de soluções, clique com botão direito do projeto VSIX e, em seguida, clique em **definir como projeto de inicialização**.  
  
    3.  Clique em **selecionar edições** e certifique-se de que **Visual Studio** é verificada.  
  
3.  Na **vsixmanifest**, em **ativos**, adicione o comando ou gesto de projeto do manipulador como um componente MEF.  
  
    1.  No **ativos**. TAB, escolha **New**.  
  
    2.  No **tipo**, selecione **mefcomponent**.  
  
    3.  No **fonte**, selecione **projeto na solução atual** e selecione o nome do seu projeto do manipulador de gesto ou comando.  
  
    4.  Salve o arquivo.  
  
4.  Retornar para o projeto do manipulador de gesto ou comando e adicione as seguintes referências de projeto.  
  
|**Referência**|**O que isso permite que você faça**|  
|-------------------|------------------------------------|  
|Programar \Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.dll Files\Microsoft Visual Studio [versão]|Criar e editar camadas|  
|Microsoft.VisualStudio.Uml.Interfaces|Criar e editar camadas|  
|Microsoft.VisualStudio.ArchitectureTools.Extensibility|Modificar formas em diagramas|  
|System.ComponentModel.Composition|Definir componentes usando Managed Extensibility Framework (MEF)|  
|Microsoft.VisualStudio.Modeling.Sdk.[version]|Definir as extensões de modelagem|  
|Microsoft.VisualStudio.Modeling.Sdk.Diagrams.[version]|Atualizar formas e diagramas|  
  
1.  Edite o arquivo de classe na classe biblioteca projeto c# para conter o código para a sua extensão. Para obter mais informações, consulte uma das seções a seguir:  
  
     [Definindo um comando de Menu](#command)  
  
     [Definindo um manipulador de gesto](#gesture)  
  
     Consulte também [navegar e atualizar modelos no código do programa de camada](../modeling/navigate-and-update-layer-models-in-program-code.md).  
  
2.  Para testar o recurso, pressione CTRL + F5 ou F5. Uma instância experimental do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] é aberta. Nesse caso, crie ou abra um diagrama de camada.  
  
3.  Para instalar o VSIX na instância principal do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], ou em outro computador, localize o **. VSIX** arquivo o **bin** diretório do projeto VSIX. Copie-o no computador em que você deseja instalar o VSIX. Clique duas vezes no arquivo VSIX no Windows Explorer (Explorador de arquivos no Windows 8).  
  
     Para desinstalar, use **extensões e atualizações** sobre o **ferramentas** menu.  
  
##  <a name="command"></a> Definindo um comando de Menu  
 Você pode adicionar mais definições de comando de menu a um projeto de comando ou gesto existente. Cada comando é definido por uma classe que tem as seguintes características:  
  
- A classe é declarada da seguinte maneira:  
  
   `[LayerDesignerExtension]`  
  
   `[Export(typeof(ICommandExtension))]`  
  
   `public class`  *MyLayerCommand*  `: ICommandExtension { ... }`  
  
- O namespace e o nome da classe não são importantes.  
  
- Os métodos que implementam `ICommandExtension` são da seguinte maneira:  
  
  -   `string Text {get;}` -O rótulo que aparece no menu.  
  
  -   `void QueryStatus(IMenuCommand command)` -chamado quando o usuário clica o diagrama e determina se o comando deve ser visível e habilitado para a seleção do usuário atual.  
  
  -   `void Execute(IMenuCommand command)` -chamado quando o usuário seleciona o comando.  
  
- Para determinar a seleção atual, você pode importar `IDiagramContext`:  
  
   `[Import]`  
  
   `public IDiagramContext DiagramContext { get; set; }`  
  
   `...`  
  
   `DiagramContext.CurrentDiagram.SelectedShapes.Count()...`  
  
  Para obter mais informações, consulte [navegar e atualizar modelos no código do programa de camada](../modeling/navigate-and-update-layer-models-in-program-code.md).  
  
  Para adicionar um novo comando, crie um novo arquivo de código que contém o exemplo a seguir. Em seguida, teste e editá-lo.  
  
```  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;  
using System.ComponentModel.Composition;  
using System.Linq;  
  
namespace MyLayerExtension // Change to your preference.  
{  
  // This is a feature for Layer diagrams:  
  [LayerDesignerExtension]  
  // This feature is a menu command:  
  [Export(typeof(ICommandExtension))]  
  // Change the class name to your preference:  
  public class MyLayerCommand : ICommandExtension  
  {  
    [Import]  
    public IDiagramContext DiagramContext { get; set; }  
  
    [Import]  
    public ILinkedUndoContext LinkedUndoContext { get; set; }  
  
    // Menu command label:  
    public string Text  
    {  
      get { return "Duplicate layers"; }  
    }  
  
    // Called when the user right-clicks the diagram.  
    // Defines whether the command is visible and enabled.  
    public void QueryStatus(IMenuCommand command)  
    {   
      command.Visible =   
      command.Enabled = DiagramContext.CurrentDiagram  
        .SelectedShapes.Count() > 0;  
    }  
  
    // Called when the user selects the command.  
    public void Execute(IMenuCommand command)  
    {  
      // A selection of starting points:  
      IDiagram diagram = this.DiagramContext.CurrentDiagram;  
      ILayerModel lmodel = diagram.GetLayerModel();  
      foreach (ILayer layer in lmodel.Layers)  
      { // All layers in model.  
      }  
      // Updates should be performed in a transaction:  
      using (ILinkedUndoTransaction t =  
        LinkedUndoContext.BeginTransaction("copy selection"))  
      {  
        foreach (ILayer layer in   
          diagram.SelectedShapes  
            .Select(shape=>shape.GetLayerElement())  
            .Where(element => element is ILayer))  
        {  
          ILayer copy = lmodel.CreateLayer(layer.Name + "+");  
          // Position the shapes:  
          IShape originalShape = layer.GetShape();  
          copy.GetShape().Move(  
            originalShape.XPosition + originalShape.Width * 1.2,  
            originalShape.YPosition);  
        }  
        t.Commit();  
      }  
    }  
  }  
}  
```  
  
##  <a name="gesture"></a> Definindo um manipulador de gesto  
 Um manipulador de gesto responde quando o usuário arrasta itens no diagrama de camada, e quando o usuário clica duas vezes em qualquer lugar no diagrama.  
  
 Para o seu comando existente ou um projeto VSIX do manipulador de gesto, você pode adicionar um arquivo de código que define um manipulador de gesto:  
  
```  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;  
using System.ComponentModel.Composition;  
using System.Linq;  
namespace MyLayerExtensions // change to your preference  
{  
  [LayerDesignerExtension]  
  [Export(typeof(IGestureExtension))]  
  public class MyLayerGestureHandler : IGestureExtension  
  {  
  }  
}  
```  
  
 Observe os seguintes pontos sobre manipuladores de gesto:  
  
- Os membros de `IGestureExtension` são da seguinte maneira:  
  
   **OnDoubleClick** -chamado quando o usuário clica duas vezes em qualquer lugar no diagrama.  
  
   **CanDragDrop** - chamado repetidamente conforme o usuário move o mouse ao arrastar um item no diagrama. Ele deve trabalhar rapidamente.  
  
   **OnDragDrop** -chamado quando o usuário solta um item no diagrama.  
  
- O primeiro argumento para cada método é um `IShape`, do qual você pode obter o elemento de camada. Por exemplo:  
  
  ```  
  public void OnDragDrop(IShape target, IDataObject data)  
  {  
      ILayerElement element = target.GetLayerElement();  
      if (element is ILayer)  
      {  
          // ...  
      }  
  }  
  ```  
  
- Manipuladores para alguns tipos de item arrastado já estão definidos. Por exemplo, o usuário pode arrastar itens do Gerenciador de soluções para um diagrama de camada. Você não pode definir um manipulador de arraste para esses tipos de item. Nesses casos, seu `DragDrop` métodos não serão chamados.  
  
  Para obter mais informações sobre como decodificar outros itens quando são arrastados no diagrama, consulte [definir um manipulador de gesto em um diagrama de modelagem](../modeling/define-a-gesture-handler-on-a-modeling-diagram.md).  
  
## <a name="see-also"></a>Consulte também  
 [Navegar e atualizar modelos de camada no código do programa](../modeling/navigate-and-update-layer-models-in-program-code.md)   
 [Adicionar validação de arquitetura personalizada a diagramas de camada](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)   
 [Definir e instalar uma extensão de modelagem](../modeling/define-and-install-a-modeling-extension.md)



