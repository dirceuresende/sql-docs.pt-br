---
title: Editor de transformação de pesquisa (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.columns.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: 690ffef5-fd59-4e95-a27d-4fcf0d6b1c0b
caps.latest.revision: 38
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 118d3a51afe868f1fa6449290a820e9b1b479867
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37199626"
---
# <a name="lookup-transformation-editor-columns-page"></a>Editor da Transformação Pesquisa (página Colunas)
  Use a página **Colunas** da caixa de diálogo **Editor da Transformação Pesquisa** para especificar a junção entre a tabela de origem e a tabela de referência, e para selecionar as colunas de pesquisa a partir da tabela de referência.  
  
 Para saber mais sobre a transformação Pesquisa, consulte [Lookup Transformation](data-flow/transformations/lookup-transformation.md).  
  
## <a name="options"></a>Opções  
 **Colunas de Entrada Disponíveis**  
 Exiba a lista das colunas de entrada disponíveis. As colunas de entrada são as colunas no fluxo de dados de uma origem conectada. As colunas de entrada e de pesquisa devem ter tipos de dados correspondentes.  
  
 Use uma operação arrastar e soltar para mapear as colunas de entrada disponíveis para as colunas de pesquisa.  
  
 Você também pode mapear as colunas de entrada para as colunas de pesquisa usando o teclado, destacando a coluna na tabela **Colunas de Entrada Disponíveis** , pressionando a tecla Aplicativo e clicando em **Editar Mapeamentos**.  
  
 **Colunas de Pesquisa Disponíveis**  
 Exiba a lista de colunas de pesquisa. As colunas de pesquisa são as colunas na tabela de referência que permitem pesquisar os valores que correspondem às colunas de entrada.  
  
 Use uma operação arrastar e soltar para mapear as colunas de pesquisa disponíveis para as colunas de entrada.  
  
 Use as caixas de seleção para selecionar as colunas de pesquisa na tabela de referência nas quais serão executadas as operações de pesquisa.  
  
 Você também pode mapear as colunas de pesquisa para as colunas de entrada usando o teclado, destacando a coluna na tabela **Colunas de Pesquisa Disponíveis** , pressionando a tecla Aplicativo e clicando em **Editar Mapeamentos**.  
  
 **coluna de pesquisa**  
 Exiba as colunas de pesquisa selecionadas. As escolhas são refletidas nas caixas de seleção da tabela **Colunas de Pesquisa Disponíveis** .  
  
 **Operação de Pesquisa**  
 Selecione uma operação de pesquisa da lista a ser executada na coluna de pesquisa.  
  
 **Alias de Saída**  
 Digite um alias para a saída de cada coluna de pesquisa. O padrão é o nome da coluna de pesquisa; entretanto, é possível selecionar qualquer nome descritivo exclusivo.  
  
## <a name="see-also"></a>Consulte também  
 [Editor de transformação de pesquisa &#40;página geral&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor de transformação de pesquisa &#40;página de Conexão&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md)   
 [Editor de transformação de pesquisa &#40;página Avançado&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md)   
 [Editor de transformação de pesquisa &#40;página de saída de erro&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md)   
 [Transformação Pesquisa Difusa](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
