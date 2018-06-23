---
title: SQL Server, objeto Gerenciador de Memória | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLServer:Memory Manager
- Memory Manager object
ms.assetid: dbf49000-eeb0-4e9c-a361-5092363920dc
caps.latest.revision: 27
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: ed20cc054b20ae22296576c6558fc21f0a23ef93
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36122602"
---
# <a name="sql-server-memory-manager-object"></a>SQL Server, objeto Memory Manager
  O objeto **Gerenciador de Memória** do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece contadores para monitorar o uso de memória de servidor global. Monitorar o uso de memória de servidor global para medir a atividade de usuário e uso de recursos pode ajudá-lo a identificar gargalos de desempenho. Monitorar a memória usada por uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode ajudar a determinar:  
  
-   Se existem gargalos a partir de memória física inadequada para o armazenamento de dados frequentemente acessados em cache. Se a memória estiver inadequada, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] terá que recuperar os dados do disco.  
  
-   Se o desempenho das consultas pode ser melhorado pela adição de memória ou pela disponibilização de mais memória para o cache de dados ou para as estruturas internas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="memory-manager-counters"></a>Contadores do Gerenciador de Memória  
 Essa tabela descreve os contadores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Gerenciador de Memória** .  
  
|Contadores do Gerenciador de Memória do SQL Server|Description|  
|----------------------------------------|-----------------|  
|**Memória de Conexão (KB)**|Especifica a quantidade total de memória dinâmica que o servidor está usando para manter conexões.|  
|**Memória Cache de Banco de Dados (KB)**|Especifica a quantidade de memória que o servidor está usando atualmente para o cache de páginas de banco de dados.|  
|**Memória Livre (KB)**|Especifica a quantidade de memória comprometida que não está atualmente em uso pelo servidor.|  
|**Memória de Espaço de Trabalho Concedida (KB)**|Especifica a quantidade total de memória concedida atualmente para a execução de processos, como hash, classificação, cópia em massa e operações de criação de índice.|  
|**Blocos de Bloqueio**|Especifica o número atual de blocos de bloqueio em uso no servidor (atualizado periodicamente). Um bloco de bloqueio representa um recurso individual bloqueado, como uma tabela, página ou linha.|  
|**Blocos de Bloqueio Alocados**|Especifica o número atual de blocos de bloqueio alocados. Na inicialização do servidor, o número de blocos de bloqueio alocados mais o número de blocos de proprietário de bloqueio alocados dependem da opção de configuração [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **do** . Se forem necessários mais blocos de bloqueio, o valor aumentará.|  
|**Memória de Bloqueio (KB)**|Especifica a quantidade total de memória dinâmica que o servidor está usando para os bloqueios.|  
|**Blocos de Proprietário de Bloqueio**|Especifica o número de blocos de proprietário de bloqueio atualmente em uso no servidor (atualizado periodicamente). Um bloco de proprietário de bloqueio representa a propriedade de um bloqueio em um objeto por um thread individual. Portanto, se três threads tiverem, cada um, um bloqueio compartilhado (S) em uma página, haverá três blocos de proprietário de bloqueio.|  
|**Blocos de Proprietário de Bloqueio Alocados**|Especifica o número atual de blocos de proprietário de bloqueio alocados. Na inicialização do servidor, o número de blocos de proprietário de bloqueio alocados e o número de blocos de bloqueio alocados dependem da opção de configuração [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **do** . Se forem necessários mais blocos de proprietário de bloqueio, o valor aumentará dinamicamente.|  
|**Memória de Espaço de Trabalho Máxima (KB)**|Indica a quantidade máxima de memória disponível para a execução de processos, como hash, classificação, cópia em massa e operações de criação de índice.|  
|**Concessões de Memória Emitidas**|Especifica o número total de processos que adquiriram com êxito uma concessão de memória de espaço de trabalho.|  
|**Concessões de Memória Pendentes**|Especifica o número total de processos que estão aguardando por uma concessão de memória de espaço de trabalho.|  
|**Memória de Otimizador (KB)**|Especifica a quantidade total de memória dinâmica que o servidor está usando para a otimização de consultas.|  
|**Memória de Servidor Reservado (KB)**|Indica a quantidade de memória que o servidor reservou para uso futuro. Esse contador exibe a quantidade atual de memória não usada inicialmente concedida que é mostrada em **Memória de Espaço de Trabalho Concedida (KB)**.|  
|**Memória Cache de SQL (KB)**|Especifica a quantidade total de memória dinâmica que o servidor está usando para o cache de SQL dinâmico.|  
|**Memória de Servidor Roubada (KB)**|Especifica a quantidade de memória que o servidor está usando para outras finalidades que não sejam páginas de banco de dados.|  
|**Memória do Servidor de Destino (KB)**|Indica a quantidade ideal de memória que o servidor pode consumir.|  
|**Memória Total do Servidor (KB)**|Especifica a quantidade de memória que o servidor comprometeu usando o gerenciador de memória.|  
  
## <a name="see-also"></a>Consulte também  
 [Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](monitor-resource-usage-system-monitor.md)   
 [SQL Server, objeto Buffer Manager](sql-server-buffer-manager-object.md)   
 [sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql)  
  
  