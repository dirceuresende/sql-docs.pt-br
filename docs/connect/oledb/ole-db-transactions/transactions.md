---
title: Transações | Microsoft Docs
description: Sessões no OLE DB Driver for SQL Server
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: oledb|ole-db-transactions
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- transactions [OLE DB]
- OLE DB Driver for SQL Server, transactions
author: pmasl
ms.author: pelopes
manager: craigg
ms.openlocfilehash: 3cf4aa84b59e41976383b6d5d567579ba2b457bf
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43022325"
---
# <a name="transactions"></a>Transactions
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  O Driver do OLE DB para SQL Server implementa o suporte de transação local. O consumidor pode usar transações distribuídas ou coordenadas pelo Coordenador de Transações Distribuídas da Microsoft (MS DTC). Para os consumidores que necessitam de um controle de transações que englobe várias sessões, o OLE DB Driver for SQL Server pode unir transações iniciadas e mantidas pelo MS DTC.  
  
 Por padrão, o OLE DB Driver for SQL Server usa um modo de transação de confirmação automática, no qual cada ação discreta na sessão de um consumidor compreende uma transação completa em uma instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. O modo de confirmação automática do OLE DB Driver for SQL Server é local e as transações de confirmação automática nunca englobam mais de uma única sessão.  
  
 O OLE DB Driver for SQL Server expõe a interface **ITransactionLocal**, permitindo que o consumidor use transações de início de forma explícita e implícita em uma única conexão a uma instância de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. O Driver do OLE DB para SQL Server não oferece suporte a transações locais aninhadas.  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Dando suporte a transações locais](../../oledb/ole-db-transactions/supporting-local-transactions.md)  
  
-   [Dando suporte a transações distribuídas](../../oledb/ole-db-transactions/supporting-distributed-transactions.md)  
  
-   [Níveis de isolamento &#40;OLE DB&#41;](../../oledb/ole-db-transactions/isolation-levels-ole-db.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Programação no Driver do OLE DB para SQL Server](../../oledb/ole-db/oledb-driver-for-sql-server-programming.md)  
  
  
