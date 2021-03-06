---
title: sp_flush_log (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_flush_log_TSQL
- sys.sp_flush_log
- sys.sp_flush_log_TSQL
- sp_flush_log
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_flush_log
ms.assetid: 75cc9f52-3b1f-4754-b1e7-ce0dd3323bc9
author: VanMSFT
ms.author: vanto
manager: craigg
ms.openlocfilehash: 2dad71f88311c8a44a03ab48ae4ad2daab1c3709
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43031528"
---
# <a name="sysspflushlog-transact-sql"></a>sys.sp_flush_log (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Libera para disco o log de transações do banco de dados atual, protegendo, assim todas as transações duráveis atrasadas confirmadas anteriormente.  
  
 Se você escolher usar a durabilidade da transação atrasada devido aos benefícios de desempenho, mas também quiser ter um limite garantido na quantidade de dados que serão perdidos se houver falha do servidor ou failover, execute `sys.sp_flush_log` regularmente. Por exemplo, se você quiser ter certeza de não perder mais do que x segundos de dados, deverá executar `sp_flush_log` a cada x segundos.  
  
 Executar `sys.sp_flush_log` garante que todas as transações duráveis atrasadas confirmadas anteriormente tornem-se duráveis. Consulte o tópico conceitual [controlar a durabilidade da transação](../../relational-databases/logs/control-transaction-durability.md) para obter mais informações.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```sql  
  
sys.sp_flush_log  
  
```  
  
#### <a name="parameters"></a>Parâmetros  
 Nenhum.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 Um código de retorno de 1 indica êxito.  Qualquer outro valor indica falha.  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Nenhum.  
  
## <a name="sample-code"></a>Código de exemplo  
  
```sql  
.  
EXECUTE sys.sp_flush_log  
  
```  
  
  
