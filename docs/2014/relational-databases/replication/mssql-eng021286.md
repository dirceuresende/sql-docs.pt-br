---
title: MSSQL_ENG021286 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021286 error
ms.assetid: b63620b7-1c6d-46f7-90ea-3a8e99af8de4
caps.latest.revision: 11
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 0ff5775a87c77ee7b0654ab39f7825f7b7bbe4f1
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37191746"
---
# <a name="mssqleng021286"></a>MSSQL_ENG021286
    
## <a name="message-details"></a>Detalhes da mensagem  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|21286|  
|Origem do evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbólico||  
|Texto da mensagem|A tabela de conflitos '%s' não existe.|  
  
## <a name="explanation"></a>Explicação  
 Esse erro será acionado se a tabela de conflitos de um artigo listado em [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) não existir de fato. O erro pode ocorrer ao tentar adicionar uma coluna ou descartar uma coluna de uma tabela publicada para replicação de mesclagem.  
  
## <a name="user-action"></a>Ação do usuário  
 Execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) no banco de dados com a tabela de conflitos ausente para verificar se não há problemas de consistência de dados.  
  
 Se a tabela de conflitos estiver ausente em um Assinante, descarte a assinatura e recrie-a. Se a tabela de conflitos estiver ausente em um Publicador, descarte todas as assinaturas, descarte a publicação e, depois, recrie a publicação e todas as assinaturas. Para obter mais informações, consulte [Publicar dados e objetos de banco de dados](publish/publish-data-and-database-objects.md) e [Assinar publicações](subscribe-to-publications.md).  
  
## <a name="see-also"></a>Consulte também  
 [Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md)  
  
  
