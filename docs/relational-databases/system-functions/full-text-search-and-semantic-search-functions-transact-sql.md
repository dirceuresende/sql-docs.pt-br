---
title: "Pesquisa de texto completo e funções de pesquisa semântica (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-functions
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
helpviewer_keywords: semantic search [SQL Server], system functions
ms.assetid: a61a3694-7604-4583-962e-fc30f771c6fa
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: cbfbf849815adb7b1da82dec494468590f3d1a4d
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="full-text-search-and-semantic-search-functions-transact-sql"></a>Funções Pesquisa de Texto Completo e Pesquisa Semântica (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Esta seção descreve as funções do sistema relacionadas à pesquisa semântica e de texto completo.  
  
## <a name="full-text-search-functions"></a>Funções de pesquisa de texto completo  
 [CONTAINSTABLE &#40;Transact-SQL&#41;](../../relational-databases/system-functions/containstable-transact-sql.md)  
 Retorna uma tabela com zero, uma ou mais linhas para as colunas que contêm correspondências precisas ou difusas (menos precisas) com palavras individuais e frases, a proximidade entre as palavras em uma determinada distância ou correspondências ponderadas.  
  
 [FREETEXTTABLE &#40;Transact-SQL&#41;](../../relational-databases/system-functions/freetexttable-transact-sql.md)  
 Retorna uma tabela de zero, uma ou mais linhas para as colunas que contêm valores correspondentes ao significado e não apenas a frase exata do texto especificado na *freetext_string*.  
  
## <a name="semantic-search-functions"></a>Funções de pesquisa semântica  
 [semantickeyphrasetable &#40;Transact-SQL&#41;](../../relational-databases/system-functions/semantickeyphrasetable-transact-sql.md)  
 Retorna uma tabela com zero, uma ou mais linhas para essas frases-chave associadas às colunas da tabela especificada.  
  
 [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](../../relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql.md)  
 Retorna uma tabela de zero, uma ou mais linhas de frases-chave comuns entre dois documentos (um documento de origem e um documento correspondido) cujo conteúdo é semanticamente similar.  
  
 [semanticsimilaritytable &#40;Transact-SQL&#41;](../../relational-databases/system-functions/semanticsimilaritytable-transact-sql.md)  
 Retorna uma tabela de zero, uma ou mais linhas para as colunas cujo conteúdo é semanticamente similar a um documento especificado.  
  
  