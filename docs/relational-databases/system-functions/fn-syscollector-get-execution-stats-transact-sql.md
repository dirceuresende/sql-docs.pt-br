---
title: fn_syscollector_get_execution_stats (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-functions
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- fn_syscollector_get_execution_stats
- fn_syscollector_get_execution_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- fn_syscollector_get_execution_stats function
ms.assetid: 793ad72c-a992-4a8d-8584-bcb6b3b476f1
caps.latest.revision: 18
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 1a80d59325234108f16a75c081f94d4102c44154
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230306"
---
# <a name="fnsyscollectorgetexecutionstats-transact-sql"></a>fn_syscollector_get_execution_stats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Retorna estatísticas detalhadas sobre o conjunto de coleta ou pacote, inclusive o número das linhas de erro que são registradas por uma tarefa de fluxo de dados do pacote. Uma tarefa de fluxo de dados é um componente do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que processa dados. Esses dados estão em formato relacional, portanto, têm um conjunto de dados de entrada e de saída que consiste em linhas.  
  
 As estatísticas são calculadas a partir de entradas na exibição syscollector_execution_stats.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
fn_syscollector_get_execution_stats ( log_id )  
```  
  
## <a name="arguments"></a>Argumentos  
 *log_id*  
 O identificador exclusivo local do log de execução. *log_id* é **int**.  
  
## <a name="table-returned"></a>Tabela retornada  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|avg_row_count_in|**Int**|Número médio de linhas que entraram nas tarefas de fluxo de dados do pacote.<br /><br /> Observação: Uma tarefa de fluxo de dados é um [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] componente que processa dados. Esses dados estão em formato relacional, portanto, têm um conjunto de dados de entrada que consiste em linhas. É o número de linhas que entraram na tarefa. Depois que os dados são transformados, sua saída ocorre como um resultado que consiste em linhas. A tarefa de fluxo de dados transforma os dados e produz uma saída como um conjunto de resultados que consiste em linhas. Essa saída é o número de linhas que saíram da tarefa.|  
|min_row_count_in|**Int**|Número mínimo de linhas que entraram nas tarefas de fluxo de dados do pacote.|  
|max_row_count_in|**Int**|Número máximo de linhas que entraram nas tarefas de fluxo de dados do pacote.|  
|avg_row_count_out|**Int**|Número médio de linhas que saíram das tarefas de fluxo de dados do pacote.|  
|min_row_count_out|**Int**|Número mínimo de linhas que saíram os dados de fluxo de tarefas do pacote.|  
|max_row_count_out|**Int**|Número máximo de linhas que saíram das tarefas de fluxo de dados do pacote.|  
|avg_duration|**Int**|Tempo médio, em milissegundos, gasto no componente de fluxo de dados do pacote.|  
|min_duration|**Int**|Tempo mínimo, em milissegundos, gasto no componente de fluxo de dados do pacote.|  
|max_duration|**Int**|Tempo máximo, em milissegundos, gasto no componente de fluxo de dados do pacote.|  
  
## <a name="permissions"></a>Permissões  
 Requer SELECT para **dc_operator**.  
  
## <a name="see-also"></a>Consulte também  
 [syscollector_execution_stats &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/syscollector-execution-stats-transact-sql.md)   
 [Coleta de Dados](../../relational-databases/data-collection/data-collection.md)  
  
  
