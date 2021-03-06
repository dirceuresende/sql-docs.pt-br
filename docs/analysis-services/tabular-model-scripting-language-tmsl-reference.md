---
title: Referência de linguagem (TMSL) de script de modelo de tabela | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tmsl
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 713fecbb367ac4717604c14b6f23baab905a993f
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34043770"
---
# <a name="tabular-model-scripting-language-tmsl-reference"></a>Referência de linguagem (TMSL) de script de modelo de tabela
[!INCLUDE[ssas-appliesto-sqlas-aas](../includes/ssas-appliesto-sqlas-aas.md)]

  Linguagem de script de modelo tabular (TMSL) é a sintaxe de definição de modelo de comando e o objeto para bancos de dados do Analysis Services modelo de tabela no nível de compatibilidade 1200 ou superior. O TMSL se comunica com o Analysis Services por meio do protocolo XMLA, onde o [XMLA. Executar](../analysis-services/xmla/xml-elements-methods-execute.md) método aceita com base em JSON **instrução** scripts em TMSL, bem como os scripts tradicionais baseado em XML em [Analysis Services Scripting Language &#40;ASSL para XMLA&#41; ](../analysis-services/scripting/analysis-services-scripting-language-assl-for-xmla.md).  
  
 Os principais elementos da TMSL incluem o seguinte:  
  
-   Metadados de tabela com base na semântica do modelo de tabela. Um modelo de tabela é composto de tabelas, colunas e relações. Definições de objeto equivalente em TMSL são agora, não surpreendentemente, tabelas, colunas, relações e assim por diante.  
  
     Um novo mecanismo de metadados dá suporte a essas definições.  
  
-   Definições de objeto são estruturadas como JSON em vez de XML.  
  
 Com exceção de como a carga é formatada (em JSON ou XML), TMSL e ASSL são funcionalmente equivalentes em como eles fornecem comandos e metadados para os métodos XMLA usada para transferência de comunicação e os dados do servidor.  
  
## <a name="how-to-use-tmsl"></a>Como usar TMSL  
 A maneira mais fácil de explorar o script TMSL está usando os comandos CREATE, ALTER, DELETE ou processo no SQL Server Management Studio (SSMS) em um modelo que você já conhece. Se que você estiver usando um modelo existente, lembre-se de atualizar o nível de compatibilidade 1200 ou superior primeiro.  
  
1.  Encontrar o comando que você deseja usar: [comandos na linguagem de script de modelo de tabela &#40;TMSL&#41;](../analysis-services/tabular-models-scripting-language-commands/tmsl-reference-commands.md)  
  
2.  Verificar a referência de definição de objeto para objetos usados no comando: [definições de objeto na linguagem de script de modelo de tabela &#40;TMSL&#41;](../analysis-services/tabular-models-scripting-language-objects/tmsl-reference-tabular-objects.md)  
  
3.  Escolha um método para enviar o script TMSL:  
  
    -   Janela XMLA no Management Studio  
  
    -   **Invoke-ascmd** por meio do PowerShell do AMO ([cmdlet Invoke-ASCmd](../analysis-services/powershell/invoke-ascmd-cmdlet.md))  
  
    -   [Analysis Services tarefa executar DDL](../integration-services/control-flow/analysis-services-execute-ddl-task.md) no SSIS.  
  
## <a name="model-definition-schema"></a>Esquema de definição de modelo  
 Captura de tela a seguir mostra uma versão abreviada do esquema, recolhida para mostrar os objetos principais.  
  
 ![SSAS_TabularMetadata](../analysis-services/media/ssas-tabularmetadata.JPG "SSAS_TabularMetadata")  
  
## <a name="scripting-languages-in-analysis-services"></a>Linguagens de script no Analysis Services  
 Analysis Services oferece suporte a linguagens de script ASSL e TMSL. Somente modelos de tabela criados no nível de compatibilidade 1200 ou superior são descritos na TMS no formato JSON.  
  
 [Linguagem de script do Analysis Services &#40;ASSL para XMLA&#41; ](../analysis-services/scripting/analysis-services-scripting-language-assl-for-xmla.md) foi a primeira linguagem de script, e ainda é a linguagem de script somente para modelos multidimensionais e tabulares em níveis inferiores de compatibilidade (1100 ou 1103). Em ASSL, modelos de tabela em x 110 são descritos em termos multidimensionais, como **cubo** (para um modelo) e **measuregroup** (para uma tabela).  
  
> [!NOTE]  
>  Em [SQL Server Data Tools (SSDT), você pode atualizar um modelo de tabela de versão anterior para usar TMSL alternando o seu **CompatibilityLevel** para 1200 ou superior. Lembre-se de que essa atualização é irreversível. Antes de atualizar, faça o modelo no caso de você precisa da versão original mais tarde.  
  
 A tabela a seguir é a matriz de linguagem de script para modelos de dados do Analysis Services em diferentes versões, nos níveis de compatibilidade específico.  

||||||  
|-|-|-|-|-|  
|**Versão**|**Multidimensional**|**Tabulares 110x**|**Tabela 1200**| **Tabela 1400** |
|Azure Analysis Services|NA|NA|TMSL|TMSL| 
|SQL Server 2017|ASSL|ASSL|TMSL|TMSL| 
|SQL Server 2016|ASSL|ASSL|TMSL|TMSL| 
|SQL Server 2014|ASSL|ASSL|NA|NA|   
|SQL Server 2012|ASSL|ASSL|NA|NA|  

  
## <a name="see-also"></a>Consulte também  
 [Nível de compatibilidade para modelos de tabela no Analysis Services](../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)   
 [Linguagem de script do Analysis Services &#40;ASSL para XMLA&#41;](../analysis-services/scripting/analysis-services-scripting-language-assl-for-xmla.md)   
 [Determina o Modo de Servidor de uma instância do Analysis Services](../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
