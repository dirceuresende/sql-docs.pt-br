---
title: sysarticlecolumns (exibição do sistema) (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sysarticlecolumns
- sysarticlecolumns_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysarticlecolumns view
ms.assetid: a8dd8d13-c827-45c4-87ba-802725301382
caps.latest.revision: 10
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 85ed85bcff82f44fa4522dbcd65e4d1d2d4a8fcc
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "33010493"
---
# <a name="sysarticlecolumns-system-view-transact-sql"></a>sysarticlecolumns (exibição de sistema) (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O **sysarticlecolumns** exibição expõe informações adicionais sobre colunas em artigos publicados. Essa exibição é armazenada no banco de dados de distribuição.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**artid**|**Int**|Identifica um artigo.|  
|**colid**|**Int**|Identifica uma coluna em um artigo.|  
|**is_udt**|**Int**|Indica se a coluna é uma coluna UDT (User-Defined Data Type). Um valor de **1** indica uma coluna UDT.|  
|**is_xml**|**Int**|Se a coluna for uma **xml** coluna. Um valor de **1** indica uma **xml** coluna.|  
|**is_max**|**Int**|Se a coluna é uma coluna de tipo de dados de valor grande (**varchar (max)**, **nvarchar (max)** ou **varbinary (max)**). Um valor de **1** indica uma coluna de valor grande.|  
  
## <a name="see-also"></a>Consulte também  
 [sp_articlecolumn &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-articlecolumn-transact-sql.md)   
 [sysarticlecolumns &#40;Transact-SQL&#41;](../../relational-databases/system-tables/sysarticlecolumns-transact-sql.md)  
  
  
