---
title: Exportar Editor de transformação de coluna (página colunas) | Microsoft Docs
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
- sql12.dts.designer.fileextractortransformation.columns.f1
helpviewer_keywords:
- Export Column Transformation Editor
ms.assetid: b659a5c2-5509-4b5b-9c82-136c971d5c7f
caps.latest.revision: 28
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: b427d8a727f0db31b63d43efbe00378c7ef0f18b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37207446"
---
# <a name="export-column-transformation-editor-columns-page"></a>Editor de Transformação Exportar Colunas (página Colunas)
  Use a página **Colunas** da caixa de diálogo **Exportar Editor de Transformação Colunas** para especificar as colunas no fluxo de dados a serem extraídas para arquivos. Você pode especificar se a transformação Exportar Coluna acrescenta dados a um arquivo ou substitui um arquivo existente.  
  
 Para saber mais sobre a transformação Exportar Coluna, consulte [Export Column Transformation](data-flow/transformations/export-column-transformation.md).  
  
## <a name="options"></a>Opções  
 **Extrair Coluna**  
 Selecione na lista de colunas de entrada que contêm dados de texto ou de imagem. Todas as linhas devem ter definições para **Extrair Coluna** e **Coluna de Caminho de Arquivos**.  
  
 **Coluna de Caminho de Arquivos**  
 Selecione na lista de colunas de entrada que contêm caminhos e nomes de arquivo. Todas as linhas devem ter definições para **Extrair Coluna** e **Coluna de Caminho de Arquivos**.  
  
 **Permitir Acréscimo**  
 Especifique se a transformação acrescenta dados a arquivos existentes. O padrão é `false`.  
  
 **Forçar Truncamento**  
 Especifique se a transformação exclui o conteúdo dos arquivos existentes antes de gravar dados. O padrão é `false`.  
  
 **Gravar BOM**  
 Especifique se deve ser gravada uma BOM (marca de ordem de byte) no arquivo. Uma BOM só é gravada se os dados têm o `DT_NTEXT` ou tipo de dados DT_WSTR e não são acrescentados a um arquivo de dados existente.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Exportar Editor de transformação de coluna &#40;página de saída de erro&#41;](../../2014/integration-services/export-column-transformation-editor-error-output-page.md)  
  
  
