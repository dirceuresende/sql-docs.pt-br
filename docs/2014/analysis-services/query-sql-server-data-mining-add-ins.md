---
title: Consulta (SQL Server Data Mining Add-ins) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- queries [data mining]
- Data Mining Query Advanced Editor
- query builder [data mining]
- DMX
ms.assetid: 16af4a6f-18d4-496a-a304-7a13aa32ee76
caps.latest.revision: 16
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 7c2ddae6582355e271488389d6e4005a5d235a74
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37289772"
---
# <a name="query-sql-server-data-mining-add-ins"></a>Consulta (Suplementos de Mineração de Dados do SQL Server)
  ![Botão de modelo de consulta, faixa de opções mineração de dados](media/dmc-query.gif "botão de modelo de consulta, faixa de opções mineração de dados")  
  
 O assistente de **Consulta** o ajuda a interagir com os modelos de mineração de dados existentes para fazer previsões com base nos dados em uma tabela ou intervalo do Excel, ou outra fonte de dados. O processo de aplicar novos dados a um modelo existente para prever tendências é denominado *consulta de previsão*.  
  
 O assistente de **Consulta** também fornece um editor avançado para criar ou modificar modelos de mineração de dados, para gerar consultas personalizadas ou trabalhar com estruturas que não têm suporte nas outras ferramentas, como conjuntos de dados aninhados.  
  
-   Use o editor de texto para digitar ou colar em instruções de extensões DMX que você criou em outro lugar.  
  
-   Use o Construtor de Consultas interativo para compor uma instrução DMX personalizada com a ajuda de modelos e caixas de diálogo.  
  
-   Criar instruções DMX para gerenciar ou fazer backup de modelos e estruturas de mineração.  
  
## <a name="using-the-query-wizard"></a>Usando o Assistente de Consulta  
  
1.  Primeiro, você deve especificar uma fonte para os dados a ser usada como entrada. Use os dados em uma tabela ou intervalo existente do Excel ou especifique uma instrução SQL para recuperar os dados.  
  
2.  Em seguida, o assistente apresenta uma lista dos modelos de mineração de dados no servidor ao qual você está conectado. Se você souber qual modelo deseja e estiver familiarizado com mineração de dados, também poderá clicar em **Avançado** para abrir o **Editor de Consulta Avançada de Mineração de Dados**.  
  
3.  Dependendo do tipo de modelo escolhido, você deverá especificar a coluna que contém os dados a serem avaliados e definir mapeamentos entre as colunas dos dados de entrada e as colunas do modelo. De acordo com o algoritmo escolhido, você poderá definir outras propriedades no modelo.  
  
4.  Por fim, o assistente também lhe oferecerá a capacidade de escolher uma ou mais previsões e especificar um destino no qual armazenar os resultados.  
  
 A qualquer momento, você poderá clicar em **Avançado** para alternar para o **Editor de Consulta Avançada de Mineração de Dados**, que lhe proporcionará mais controle sobre cada parte da instrução DMX. Para obter mais informações sobre como usar a ferramentas de edição de consulta avançada, consulte [Editor de consultas de mineração de dados avançados](advanced-data-mining-query-editor.md).  
  
### <a name="requirements"></a>Requisitos  
 Para usar o **consulta** do assistente, você deve estar conectado a uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]. Além disso, o servidor deve conter pelo menos um modelo de mineração de dados de um tipo apropriado. Se não houver nenhum modelo de mineração disponível, você poderá criar um desses modelos usando os assistentes fornecidos no Cliente de Mineração de Dados para Excel. Para obter informações sobre como criar um novo modo de mineração usando um assistente, consulte [criando um modelo de mineração de dados](creating-a-data-mining-model.md).  
  
## <a name="see-also"></a>Consulte também  
 [Implantando e dimensionando modelos de mineração &#40;Data Mining Add-ins para Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)   
 [Cliente de mineração de dados para Excel &#40;suplementos de mineração de dados do SQL Server&#41;](data-mining-client-for-excel-sql-server-data-mining-add-ins.md)  
  
  
