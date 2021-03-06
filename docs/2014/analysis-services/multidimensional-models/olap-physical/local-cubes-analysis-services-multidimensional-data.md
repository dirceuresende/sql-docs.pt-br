---
title: Cubos locais (Analysis Services - dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], local
ms.assetid: e52e1515-35a7-4dc3-9bbf-736d176ba0c7
caps.latest.revision: 13
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 3cc1e27115d898cc2ba839fb14d2f7edfa8c560f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37149277"
---
# <a name="local-cubes-analysis-services---multidimensional-data"></a>Cubos locais (Analysis Services – Dados Multidimensionais)
  Para criar, atualizar ou excluir cubos locais, você deve escrever e executar um script ASSL ou um programa AMO.  
  
 Os cubos locais e os modelos de mineração locais permitem a análise em uma estação de trabalho cliente enquanto ela estiver desconectada da rede. Por exemplo, um aplicativo cliente pode chamar o OLE DB for OLAP 9.0 Provider (MSOLAP.3), que carrega o mecanismo do cubo local para criar e consultar cubos locais, conforme mostra a seguinte ilustração:  
  
 ![Arquitetura do cliente para cubos locais e modelos](../../../analysis-services/dev-guide/media/as-localcubearch9.gif "arquitetura do cliente para cubos locais e modelos")  
  
 O ADMOD.NET e os Objetos de Gerenciamento de Análise (AMO) também carregam o mecanismo do cubo local ao interagir com cubos locais. Apenas um processo simples pode acessar um arquivo de cubo local, pois o mecanismo de cubo local bloqueia com exclusividade um arquivo de cubo local quando estabelece uma conexão com o cubo local. Com um processo, são permitidas até 5 conexões simultâneas.  
  
 Um arquivo .cub pode conter mais de um cubo ou modelo de mineração de dados. As consultas aos cubos locais e modelos de mineração de dados são tratadas pelo mecanismo de cubo local e não requerem uma conexão com uma instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
> [!NOTE]  
>  Não há suporte para a utilização do [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] nem do [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] para gerenciar cubos locais.  
  
## <a name="local-cubes"></a>Cubos locais  
 Um cubo local pode ser criado e preenchido a partir de um cubo existente em um [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instância ou de uma fonte de dados relacionais.  
  
|Fonte para obter dados para cubo local|Método de criação|  
|------------------------------------|---------------------|  
|Cubo baseado em servidor|Você pode usar a instrução CREATE GLOBAL CUBE ou um [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] script Scripting Language (ASSL) para criar e popular um cubo a partir de um cubo com base em servidor. Para obter mais informações, consulte [instrução CREATE GLOBAL CUBE &#40;MDX&#41; ](/sql/mdx/mdx-data-definition-create-global-cube) ou [Analysis Services Scripting Language &#40;ASSL&#41; referência](../../scripting/analysis-services-scripting-language-assl-for-xmla.md).|  
|Fonte de dados relacionais|Você usa um script ASSL para criar e popular um cubo de um banco de dados relacional OLE DB. Para criar um cubo local usando ASSL, simplesmente conecte-se a um arquivo de cubo local (* .cub) e execute o script ASSL da mesma maneira que faria com um script ASSL em uma instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] para criar um cubo de servidor. Para obter mais informações, consulte [Analysis Services Scripting Language &#40;ASSL&#41; referência](../../scripting/analysis-services-scripting-language-assl-for-xmla.md).|  
  
 Use a instrução REFRESH CUBE para recriar um cubo local e atualizar seus dados. Para obter mais informações, consulte [REFRESH CUBE instrução &#40;MDX&#41;](/sql/mdx/mdx-data-definition-refresh-cube).  
  
### <a name="local-cubes-created-from-server-based-cubes"></a>Cubos locais criados de cubos baseados em servidor  
 Na criação de cubos locais de cubos baseados em servidor, as seguintes considerações se aplicam:  
  
-   Não há suporte para medidas de contagens distintas.  
  
-   Ao adicionar uma medida, você também deve incluir pelo menos uma dimensão relacionada à medida sendo adicionada. Para obter mais informações sobre relações de dimensão para grupos de medidas, consulte [relações de dimensão](../../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).  
  
-   Quando você adiciona uma hierarquia pai-filho, os níveis e filtros dessa hierarquia são ignorados e toda a hierarquia pai-filho é incluída.  
  
-   Não são criadas propriedades do membro.  
  
-   Quando você inclui uma medida semiaditiva, nenhuma fatia é permitida na dimensão Conta ou Tempo.  
  
-   Dimensões de referência sempre são materializadas.  
  
-   Quando uma dimensão muitos para muitos é incluída, as seguintes regras são aplicadas:  
  
    -   Você não pode fatiar a dimensão muitos para muitos.  
  
    -   Você deve adicionar uma medida do grupo de medidas intermediário.  
  
    -   Você não pode fatiar nenhuma das dimensões comuns aos dois grupos de medidas envolvidos na relação muitos para muitos.  
  
-   Somente esses membros calculados, conjuntos nomeados e atribuições que se baseiam em medidas e dimensões adicionadas ao cubo local serão exibidas nele. Membros calculados inválidos, conjuntos nomeados e atribuições serão excluídos automaticamente.  
  
### <a name="security"></a>Segurança  
 Para que um usuário criar um cubo local de um cubo de servidor, o usuário deve ter **detalhamento e cubo Local** permissões no cubo de servidor. Para obter mais informações, consulte [conceder permissões de cubo ou modelo de &#40;Analysis Services&#41;](../../multidimensional-models/grant-cube-or-model-permissions-analysis-services.md).  
  
 Os cubos locais não são protegidos por meio de funções como os cubos de servidor. Qualquer um com acesso no nível de arquivo a um arquivo de cubo local pode consultar os cubos. Você pode usar a propriedade de conexão `Encryption Password` em um arquivo de cubo local para definir uma senha no arquivo de cubo local. A definição de uma senha em um arquivo de cubo local requer que todas as conexões futuras com o arquivo de cubo local utilizem essa senha para consultar o arquivo.  
  
## <a name="see-also"></a>Consulte também  
 [Instrução CREATE GLOBAL CUBE &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-global-cube)   
 [Desenvolvimento com o Analysis Services Scripting Language &#40;ASSL&#41;](../scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)   
 [Instrução do cubo de atualização &#40;MDX&#41;](/sql/mdx/mdx-data-definition-refresh-cube)  
  
  
