---
title: Excluir uma tabela (SSAS Tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
caps.latest.revision: 8
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: e57cdddbbd7cc4ee75c0758b84d6a68b7fadfd6b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37308478"
---
# <a name="delete-a-table-ssas-tabular"></a>Excluir uma tabela (SSAS tabular)
  No designer de modelo, você pode excluir tabelas em seu banco de dados de espaço de trabalho modelo que você não precisa mais. A exclusão de uma tabela não afeta os dados de origem originais, somente os dados que você importou e com os quais estava trabalhando. Não é possível desfazer a exclusão de uma tabela.  
  
### <a name="to-delete-a-table"></a>Para excluir uma tabela  
  
-   Clique com o botão direito do mouse na guia, na parte inferior do designer de modelo para a tabela que você deseja excluir, e clique em **Excluir**.  
  
## <a name="considerations-when-deleting-tables"></a>Considerações ao excluir tabelas  
  
-   Quando você excluir uma tabela, a guia inteira na qual a tabela se encontra será excluída.  
  
-   Se houver uma medida associada a essa tabela, a definição da medida também será excluída.  
  
-   Se você criou qualquer coluna calculada usando essa tabela, as colunas dessa tabela também serão excluídas; as colunas calculadas de outras tabelas que usam colunas da tabela excluída exibirão um erro.  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas e colunas &#40;Tabular do SSAS&#41;](tables-and-columns-ssas-tabular.md)  
  
  
