---
title: "Níveis de isolamento da transação | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- locking [SQL Server], hints
- isolation levels [SQL Server], metadata access
- hints [SQL Server], locking
ms.assetid: 02bb71fa-1e92-4782-a9cf-6e256cc1f3ea
caps.latest.revision: 23
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 0acd70fad20d0ad1c2727f93da52b2e938ee21fd
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="transaction-isolation-levels"></a>Níveis de isolamento da transação
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não garante que as dicas de bloqueio serão cumpridas em consultas que acessam metadados por exibições do catálogo, exibições de compatibilidade, exibições de esquema de informações, funções internas que emitem metadados.  
  
 Internamente, o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cumpre apenas o nível de isolamento READ COMMITTED para acesso a metadados. Se uma transação tiver um nível de isolamento que seja, por exemplo, SERIALIZABLE e, dentro da transação, for feita uma tentativa de acessar os metadados usando exibições do catálogo ou funções internas que emitem metadados, essas consultas serão executadas até serem concluídas como READ COMMITTED. Porém, no isolamento de instantâneo, o acesso aos metadados pode falhar por causa de operações de DDL simultâneas. Isso porque os metadados não são controlados por versão. Portanto, pode haver falha ao acessar o seguinte no isolamento de instantâneo:  
  
-   Exibições do catálogo  
  
-   Exibições de compatibilidade  
  
-   Exibições do esquema de informações  
  
-   Funções internas que emitem metadados  
  
-   **sp_help** grupo de procedimentos armazenados  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Procedimentos de catálogo de cliente nativo  
  
-   Exibições e funções de gerenciamento dinâmico  
  
 Para obter mais informações sobre níveis de isolamento, consulte [SET TRANSACTION ISOLATION LEVEL &#40; Transact-SQL &#41; ](../../t-sql/statements/set-transaction-isolation-level-transact-sql.md).  
  
 A tabela a seguir fornece um resumo do acesso aos metadados em vários níveis de isolamento.  
  
|Nível de isolamento|Tem suporte|Cumprido|  
|---------------------|---------------|-------------|  
|READ UNCOMMITTED|Não|Não garantido|  
|READ COMMITTED|Sim|Sim|  
|REPEATABLE READ|Não|Não|  
|SNAPSHOT ISOLATION|Não|Não|  
|SERIALIZABLE|Não|Não|  
  
  