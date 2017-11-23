---
title: syspolicy_system_health_state (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- syspolicy_system_health_state_TSQL
- syspolicy_system_health_state
dev_langs: TSQL
helpviewer_keywords: syspolicy_system_health_state view
ms.assetid: 00815106-9fe4-481d-a9e1-a256101887f4
caps.latest.revision: "22"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e3aa7ef860f35917adc330b6c8c49b3692b5e6f4
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="syspolicysystemhealthstate-transact-sql"></a>syspolicy_system_health_state (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Exibe uma linha para cada combinação de expressão de consulta de destino e política do Gerenciamento Baseado em Política. Use a exibição syspolicy_system_health_state para verificar de forma programática a saúde da política do servidor. A tabela a seguir descreve as colunas na exibição  syspolicy_system_health_state.  
  
||  
|-|  
|**Aplica-se a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] até a [versão atual](http://go.microsoft.com/fwlink/p/?LinkId=299658)).|  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|health_state_id|**bigint**|Identificador do registro do estado da saúde da política.|  
|policy_id|**int**|Identificador da política.|  
|last_run_date|**datetime**|Data e hora em que a política foi executada pela última vez.|  
|target_query_expression_with_id|**nvarchar (400)**|A expressão de destino com valores atribuídos a variáveis de identidade que define o destino contra o qual a política é avaliada.|  
|target_query_expression|**nvarchar(max)**|A expressão que define o destino no qual a política é avaliada.|  
|result|**bit**|O estado de saúde desse destino em relação à política:<br /><br /> 0 = Falha<br /><br /> 1 = Êxito|  
  
## <a name="remarks"></a>Comentários  
 O exibição syspolicy_system_health_state mostra o estado mais recente da saúde da expressão de consulta de destino para cada política ativa (ativada). As página Pesquisador de Objetos e Detalhes do Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] agrega a saúde da política desta exibição para mostrar o estado de saúde crítico.  
  
## <a name="permissions"></a>Permissões  
 Requer a associação à função PolicyAdministratorRole no banco de dados msdb.  
  
## <a name="see-also"></a>Consulte também  
 [Administrar servidores com Gerenciamento Baseado em Políticas](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)   
 [Exibições de Gerenciamento Baseado em Políticas &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/policy-based-management-views-transact-sql.md)  
  
  