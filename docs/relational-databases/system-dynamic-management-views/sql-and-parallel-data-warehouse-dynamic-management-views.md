---
title: "SQL Parallel Data Warehouse e exibições de gerenciamento dinâmico | Microsoft Docs"
ms.custom: 
ms.date: 03/15/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.service: sql-data-warehouse
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: e713365e-d44c-4b66-84c9-81a1bcc32414
caps.latest.revision: "9"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c708a2bcf2074b71751520bee20ff636215193c2
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sql-and-parallel-data-warehouse-dynamic-management-views"></a>Exibições de gerenciamento dinâmico do SQL e o Parallel Data Warehouse
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Este tópico lista os [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] e [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] exibições de gerenciamento dinâmico (DMVs).  
  
 Todos os [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] e [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] DMVs começam com **sys.dm_pdw**.  
  
## <a name="includesssdwincludessssdw-mdmd-and-includesspdwincludessspdw-mdmd-dynamic-management-views"></a>[!INCLUDE[ssSDW](../../includes/sssdw-md.md)]e [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] exibições de gerenciamento dinâmico  
 As exibições de gerenciamento dinâmico a seguir se aplicam a ambos [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] e [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]:  
  
 [sys.dm_pdw_dms_cores &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-dms-cores-transact-sql.md)  
  
 [sys.dm_pdw_dms_external_work &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-dms-external-work-transact-sql.md)  
  
 [sys.dm_pdw_dms_workers &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-dms-workers-transact-sql.md)  
  
 [sys.dm_pdw_errors &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-errors-transact-sql.md)  
  
 [sys.dm_pdw_exec_connections &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-connections-transact-sql.md)  
  
 [sys.dm_pdw_exec_requests &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)  
  
 [sys.dm_pdw_exec_sessions &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-sessions-transact-sql.md)  
  
 [sys.dm_pdw_hadoop_operations &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-hadoop-operations-transact-sql.md)  
  
 [sys.dm_pdw_lock_waits &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-lock-waits-transact-sql.md)  
  
 [sys.dm_pdw_nodes &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md)  
  
 [sys.dm_pdw_nodes_database_encryption_keys &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-database-encryption-keys-transact-sql.md)  
  
 [sys.dm_pdw_os_threads &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-os-threads-transact-sql.md)  
  
 [sys.dm_pdw_request_steps &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-request-steps-transact-sql.md)  
  
 [sys.dm_pdw_resource_waits &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-resource-waits-transact-sql.md)  
  
 [sys.dm_pdw_sql_requests &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-sql-requests-transact-sql.md)  
  
 [sys.dm_pdw_sys_info &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-sys-info-transact-sql.md)  
  
 [sys.dm_pdw_wait_stats &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-wait-stats-transact-sql.md)  
  
 [sys.dm_pdw_waits &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-waits-transact-sql.md)  
  
## <a name="includesspdwincludessspdw-mdmd-dynamic-management-views"></a>[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]Exibições de gerenciamento dinâmico  
 As exibições de gerenciamento dinâmico a seguir se aplicam a [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] somente:  
  
 [sys.dm_pdw_component_health_active_alerts &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-component-health-active-alerts-transact-sql.md)  
  
 [sys.dm_pdw_component_health_alerts &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-component-health-alerts-transact-sql.md)  
  
 [sys.dm_pdw_component_health_status &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-component-health-status-transact-sql.md)  
  
 [sys.dm_pdw_diag_processing_stats &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-diag-processing-stats-transact-sql.md)  
  
 [sys.dm_pdw_network_credentials &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-network-credentials-transact-sql.md)  
  
 [sys.dm_pdw_node_status &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-node-status-transact-sql.md)  
  
 [sys.dm_pdw_os_event_logs &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-os-event-logs-transact-sql.md)  
  
 [sys.dm_pdw_os_performance_counters &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-os-performance-counters-transact-sql.md)  
  
 [sys.dm_pdw_query_stats_xe &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-query-stats-xe-transact-sql.md)  
  
 [sys.dm_pdw_query_stats_xe_file &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-query-stats-xe-file-transact-sql.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  