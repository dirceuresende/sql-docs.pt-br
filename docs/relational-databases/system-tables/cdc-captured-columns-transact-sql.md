---
title: captured_columns (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- cdc.captured_columns
- cdc.captured_columns_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- cdc.captured_columns
ms.assetid: 7bb4d408-d764-4ef6-802c-f271c8d39c2a
caps.latest.revision: 14
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 144bf49651013b55ec1b515da1ecec156dd375c6
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39103274"
---
# <a name="cdccapturedcolumns-transact-sql"></a>cdc.captured_columns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna uma linha para cada coluna rastreada em uma instância de captura. Por padrão, todas as colunas na tabela de origem são capturadas. Porém, colunas podem ser incluídas ou excluídas quando a tabela de origem é habilitada para Change Data Capture especificando uma lista de colunas. Para obter mais informações, consulte [sp_cdc_enable_table &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-enable-table-transact-sql.md).  
  
 É recomendável que você **não consultar diretamente as tabelas do sistema**. Em vez disso, execute as [sp_cdc_get_source_columns](../../relational-databases/system-stored-procedures/sys-sp-cdc-get-captured-columns-transact-sql.md) procedimento armazenado.  
   
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|A identificação da tabela de origem à qual a coluna capturada pertence.|  
|**column_name**|**sysname**|Nome da coluna capturada.|  
|**column_id**|**int**|A identificação da coluna capturada dentro da tabela de origem.|  
|**column_type**|**sysname**|O tipo de coluna capturada.|  
|**column_ordinal**|**int**|O ordinal da coluna (com base em 1) na tabela de alteração. As colunas de metadados na tabela de alteração são excluídas. O ordinal 1 é atribuído à primeira coluna capturada.|  
|**is_computed**|**bit**|Indica que a coluna capturada é uma coluna computada na tabela de origem.|  
  
## <a name="see-also"></a>Consulte também  
 [change_tables &#40;Transact-SQL&#41;](../../relational-databases/system-tables/cdc-change-tables-transact-sql.md)  
  
  
