---
title: Exibir comandos replicados e informação no banco de dados de distribuição | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: replication
ms.reviewer: ''
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_browsereplcmds
- transactional replication, monitoring
- distribution databases [SQL Server replication], viewing replicated commands
- viewing replicated commands
ms.assetid: 9c20acec-8fab-4483-b9c1-dfe3768f85dd
caps.latest.revision: 31
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: c5a3c649f60f10ed966bb24d7307947c165d20bf
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37350218"
---
# <a name="view-replicated-commands-and-information-in-distribution-database"></a>Exibir comandos replicados e informação no banco de dados de distribuição
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Ao usar replicação transacional, os comandos de transação são armazenados no banco de dados de distribuição ou até que o Agente de Distribuição os propague a todos os Assinantes ou até um Agente de Distribuição enviar as alterações ao Assinante. Esses comandos pendentes no banco de dados de distribuição podem ser exibidos programaticamente por meio de procedimentos armazenados de replicação. Para obter mais informações, consulte [procedimentos armazenados de replicação &#40;Transact-SQL&#41;](../../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md).  
  
### <a name="to-view-replicated-commands-from-all-transactional-publications-in-the-distribution-database"></a>Para exibir os comandos replicados de todas as publicações transacionais no banco de dados de distribuição  
  
1.  No Distribuidor, no banco de dados de distribuição, execute [sp_browsereplcmds](../../../relational-databases/system-stored-procedures/sp-browsereplcmds-transact-sql.md).  
  
### <a name="to-view-replicated-commands-in-the-distribution-database-from-a-specific-article-or-from-a-specific-database-published-using-transactional-replication"></a>Para exibir comandos replicados no banco de dados de distribuição de um artigo específico ou de um banco de dados publicado específico por meio de replicação transacional  
  
1.  (Opcional) No Publicador, no banco de dados de publicação, execute [sp_helparticle](../../../relational-databases/system-stored-procedures/sp-helparticle-transact-sql.md). Especifique **@publication** e **@article**. Observe o valor de **id de artigo** no conjunto de resultados.  
  
2.  No Distribuidor, no banco de dados de distribuição, execute [sp_browsereplcmds](../../../relational-databases/system-stored-procedures/sp-browsereplcmds-transact-sql.md). (Opcional) Especifique a ID do artigo da etapa 2 como **@article_id**. (Opcional) Especifique a id do banco de dados de publicação como **@publisher_database_id**, que pode ser obtida da coluna **database_id** na exibição de catálogo [sys.databases](../../../relational-databases/system-catalog-views/sys-databases-transact-sql.md) .  
  
## <a name="see-also"></a>Consulte Também  
 [Monitorar programaticamente a replicação](../../../relational-databases/replication/monitor/programmatically-monitor-replication.md)  
  
  
