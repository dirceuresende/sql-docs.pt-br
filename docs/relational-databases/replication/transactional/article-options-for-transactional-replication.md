---
title: Opções do artigo para replicação transacional | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: replication
ms.reviewer: ''
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], transactional replication options
- transactional replication, article options
ms.assetid: 3469b185-0ea5-4690-a71c-717230d886b6
caps.latest.revision: 30
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: ae80de532c6cddf4e67b4e8161ea6219beb88f10
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37349188"
---
# <a name="article-options-for-transactional-replication"></a>Opções de artigo para replicação transacional
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Há vários um número de opções para artigos em publicações transacionais. Com a replicação transacional, você pode fazer o seguinte:  
  
-   Especificar como as alterações são propagadas do Publicador para os Assinantes. Para obter mais informações, consulte [Especificar como as alterações são propagadas para artigos transacionais](../../../relational-databases/replication/transactional/transactional-articles-specify-how-changes-are-propagated.md).  
  
-   Especificar que a execução de um procedimento armazenado seja replicada. Isso é útil ao replicar os resultados de procedimentos armazenados orientados a manutenção que afetam grandes quantidades de dados. Para saber mais, confira [Publishing Stored Procedure Execution in Transactional Replication](../../../relational-databases/replication/transactional/publishing-stored-procedure-execution-in-transactional-replication.md).  
  
-   Especificar opções de esquema se as restrições e os gatilhos são copiados para o Assinante. Para obter mais informações, veja [Especificar opções de esquema](../../../relational-databases/replication/publish/specify-schema-options.md).  
  
-   Usar filtros de linha e filtros de coluna. Filtrar artigos de tabela lhe permite criar partições de dados a serem publicados. Para obter mais informações, consulte [Filter Published Data](../../../relational-databases/replication/publish/filter-published-data.md) (Filtrar dados publicados).  
  
## <a name="see-also"></a>Consulte Também  
 [Publicar dados e objetos de banco de dados](../../../relational-databases/replication/publish/publish-data-and-database-objects.md)  
  
  
