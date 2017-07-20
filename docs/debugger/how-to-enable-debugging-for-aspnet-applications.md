---
title: "Como habilitar a depura&#231;&#227;o para aplicativos ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "depurando aplicativos Web ASP.NET"
  - "Arquivo de configuração Web. config, o modo de depuração"
  - "depuração [Visual Studio], ASP.NET"
ms.assetid: 3beed819-cece-4864-8184-bd410000973a
caps.latest.revision: 37
caps.handback.revision: 37
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Como habilitar a depura&#231;&#227;o para aplicativos ASP.NET
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Para habilitar a depuração, você deve habilitá-lo em ambos os **Propriedades do projeto** página e no arquivo de Web. config do aplicativo.  
  
> [!NOTE]  
> Caixas de diálogo e comandos de menu que você vê podem diferir daqueles descritos na Ajuda, dependendo de suas configurações ativas ou edição. Para alterar suas configurações, escolha **Import and Export Settings** sobre o **ferramentas** menu. Para obter mais informações, consulte [Personalizando configurações de desenvolvimento no Visual Studio](http://msdn.microsoft.com/en-us/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-enable-aspnet-debugging-in-the-project-properties-visual-basicc"></a>Para habilitar a depuração ASP.NET nas propriedades de projeto (Visual Basic/C#)  
  
1.  Em **Solution Explorer**, clique no nome de um projeto da Web e selecione **propriedades**.  
  
2.  Na página de propriedades do projeto, clique o **Web** guia.  
  
3.  Em **depuradores**, selecione o **ASP.NET** caixa de seleção.  
  
### <a name="to-enable-debugging-in-the-webconfig-file"></a>Para habilitar a depuração no arquivo web.config  
  
1.  Abra o arquivo web.config usando qualquer editor de texto ou analisador XML padrão.  
  
    > [!NOTE]  
    > No entanto, você não pode acessar o arquivo remotamente usando um navegador da Web. Por razões de segurança, o [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] configura o servidor IIS da Microsoft para ajudar a impedir o acesso direto do navegador aos arquivos Web.config. Se você tentar acessar um arquivo de configuração usando um navegador, receberá o erro de acesso HTTP 403 (proibido).  
  
2.  Web.config é um arquivo XML e, assim, contém as seções aninhadas marcadas por aspas. Localize o elemento `configuration/system.web/compilation`. Se o elemento de compilação não existir, crie-o.  
  
3.  Se o elemento `compilation` não contiver um atributo `debug`, adicione o atributo ao elemento.  
  
4.  Verifique se o valor do atributo `debug` está definido como `true`.  
  
O arquivo web.config deve parecer com o exemplo a seguir. Observe que pode haver seções entre a configuração e os elementos system.web  
  
-   seções de elementos entre a configuração e os elementos system.web  
  
-   seções de elementos entre system.web e os elementos de compilação  
  
-   Um elemento de compilação pode conter outros atributos e elementos  
  
## <a name="example"></a>Exemplo  
  
```  
<configuration>  
    ...  
    <system.web>  
        <compilation  
            debug="true"  
            ...  
        >  
        ...  
        </compilation>  
    </system.web>  
</configuration>  
```  
  
## <a name="robust-programming"></a>Programação robusta  
O [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] detecta automaticamente todas as alterações nos arquivos Web.config e aplica novos parâmetros de configuração. Você não precisa reiniciar o computador ou reiniciar o servidor IIS para que as alterações entrem em vigor.  
  
Um site pode conter vários diretórios e subdiretórios virtuais, e arquivos Web.config podem existir em cada um. Os aplicativos [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] herdam as configurações de arquivos Web.config em níveis mais altos no caminho da URL. Os arquivos de configuração hierárquicos permitem modificar configurações de vários aplicativos [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] ao mesmo tempo, como, por exemplo, para todos os aplicativos abaixo deles na hierarquia. No entanto, se `debug` for definido em um arquivo mais baixo na hierarquia, ele substituirá o valor mais alto.  
  
Por exemplo, você poderia especificar `debug="true"` em www.microsoft.com/aaa/Web.config e qualquer aplicativo na pasta aaa ou qualquer subpasta aaa herdaria essa configuração. Por isso, se o aplicativo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] estiver em www.microsoft.com/aaa/bbb, ele herdará essa configuração, como todos os aplicativos [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] em www.microsoft.com/aaa/ccc, www.microsoft.com/aaa/ddd e assim por diante. A única exceção será se um desses aplicativos substituir a configuração por meio de seu próprio arquivo mais baixo Web.config.  
  
Habilitar o modo de depuração afetará significativamente o desempenho do aplicativo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]. Lembre-se de desabilitar o modo de depuração antes de implantar um aplicativo de versão ou conduzir medidas de desempenho.  
  
## <a name="see-also"></a>Consulte também  
[Depurando aplicativos ASP.NET e AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)  
  