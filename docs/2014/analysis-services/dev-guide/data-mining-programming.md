---
title: Programação de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- data mining [Analysis Services], developer's guide
ms.assetid: 9fd77b16-0b89-44ce-bcf1-7c04b62499da
caps.latest.revision: 19
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: fce4bd16cdc64aeabb2367d757b0b68a5cab6144
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37297366"
---
# <a name="data-mining-programming"></a>Programação de mineração de dados
  Se você considerar que ferramentas e visualizadores internos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não atendem às suas necessidades, poderá ampliar a capacidade do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] codificando suas próprias extensões. Nessa abordagem, você tem duas opções:  
  
-   **XMLA**  
  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] dá suporte a XML for Analysis (XMLA) como protocolo para comunicação com aplicativos cliente. Comandos adicionais têm suporte do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que estende a especificação do XML for Analysis.  
  
     Como o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usa XMLA para definição de dados, manipulação de dados e suporte a controle de dados, você pode criar estruturas de mineração e modelos de mineração usando as ferramentas visuais fornecidas pelo [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e, em seguida, estender os objetos de data mining criados usando os scripts de extensão DMX e de linguagem ASSL.  
  
     Você pode criar e pode modificar objetos de data mining completamente em scripts de XMLA e executar consultas de previsão em modelos programaticamente de seus próprios aplicativos.  
  
-   **Analysis Management Objects (AMO)**  
  
     O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] também fornece uma estrutura completa que permite aos provedores de mineração de dados de terceiros integrar os seguintes objetos de mineração de dados no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
     Você pode criar estruturas de mineração e modelos de mineração usando AMO. Consulte os seguintes exemplos em CodePlex:  
  
    -   Navegador AMO  
  
         Conecta-se à instância do SSAS especificada e lista todos os objetos de servidor e suas propriedades, incluindo estrutura de mineração e modelos de mineração.  
  
    -   Exemplo Simples de AMO  
  
         O Exemplo Simples do AS aborda o acesso programático à maioria dos objetos principais, e demonstra a navegação de metadados e o acesso aos valores em objetos.  
  
         O exemplo também demonstra como criar e processar uma estrutura e um modelo de mineração de dados, bem como navegar em um modelo de mineração de dados existente.  
  
-   **DMX**  
  
     Você pode usar DMX para encapsular instruções de comando, consultas de previsão e resultados da consulta e metadados de retorno em um formato de tabela, supondo que você tenha criado uma conexão com um servidor do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
## <a name="in-this-section"></a>Nesta seção  
 [OLE DB para mineração de dados](../../../2014/analysis-services/dev-guide/ole-db-for-data-mining.md)  
 Descreve adições à especificação para dar suporte à mineração de dados e a dados multidimensionais: novos conjuntos de linhas e colunas de esquemas, linguagem DMX para criação e gerenciamento de estruturas de mineração.  
  
## <a name="related-reference"></a>Referência relacionada  
 [Desenvolvendo com ADOMD.NET](../multidimensional-models/adomd-net/developing-with-adomd-net.md)  
 Apresenta objetos de programação do servidor e do cliente ADOMD.NET.  
  
 [Desenvolvendo com objetos de gerenciamento de análise &#40;AMO&#41;](../multidimensional-models/analysis-management-objects/developing-with-analysis-management-objects-amo.md)  
 Apresenta a biblioteca de programação AMO.  
  
 [Desenvolvimento com o Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
 Apresenta o XML for Analysis (XMLA) e suas extensões.  
  
## <a name="see-also"></a>Consulte também  
 [Guia do desenvolvedor do &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md)   
 [Extensões de mineração de dados &#40;DMX&#41; referência](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
