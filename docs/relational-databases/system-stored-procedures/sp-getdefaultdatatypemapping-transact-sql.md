---
title: sp_getdefaultdatatypemapping (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_getdefaultdatatypemapping_TSQL
- sp_getdefaultdatatypemapping
helpviewer_keywords:
- sp_getdefaultdatatypemapping
ms.assetid: b8401de1-f135-41d0-ba79-ce8fe1f48c00
caps.latest.revision: 18
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ff9df7e27545aa130398e0a81ffcf24855503aba
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43025705"
---
# <a name="spgetdefaultdatatypemapping-transact-sql"></a>sp_getdefaultdatatypemapping (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna informações sobre o mapeamento padrão para o tipo de dados especificado entre [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e um não -[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (DBMS) do sistema de gerenciamento de banco de dados. Esse procedimento armazenado é executado no Distribuidor em qualquer banco de dados.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_getdefaultdatatypemapping [ @source_dbms = ] 'source_dbms'   
    [ , [ @source_version = ] 'source_version' ]  
        , [ @source_type = ] 'source_type'    
    [ , [ @source_length = ] source_length ]  
    [ , [ @source_precision = ] source_precision ]  
    [ , [ @source_scale = ] source_scale ]  
    [ , [ @source_nullable = ] source_nullable ]  
        , [ @destination_dbms = ] 'destination_dbms'   
    [ , [ @destination_version = ] 'destination_version' ]  
    [ , [ @destination_type = ] 'destination_type' OUTPUT ]  
    [ , [ @destination_length = ] destination_length OUTPUT ]  
    [ , [ @destination_precision = ] destination_precision OUTPUT ]  
    [ , [ @destination_scale = ] destination_scale OUTPUT ]  
    [ , [ @destination_nullable = ] source_nullable OUTPUT ]  
    [ , [ @dataloss = ] dataloss OUTPUT ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [ **@source_dbms**=] **'***source_dbms***'**  
 É o nome do DBMS no qual os tipos de dados são mapeados. *source_dbms* está **sysname**, e pode ser um dos seguintes valores:  
  
|Valor|Description|  
|-----------|-----------------|  
|**MSSQLSERVER**|A origem é um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|**ORACLE**|A origem é um banco de dados Oracle.|  
  
 Você deve especificar esse parâmetro.  
  
 [  **@source_version=** ] **'***source_version***'**  
 É o número da versão do DBMS de origem. *source_version* está **varchar(10)**, com um valor padrão de NULL.  
  
 [ **@source_type**=] **'***source_type***'**  
 É o tipo de dados no DBMS de origem. *source_type* está **sysname**, sem padrão.  
  
 [  **@source_length=** ] *source_length*  
 É o comprimento do tipo de dados no DBMS de origem. *source_length* está **bigint**, com um valor padrão de NULL.  
  
 [  **@source_precision=** ] *source_precision*  
 É a precisão do tipo de dados no DBMS de origem. *source_precision* está **bigint**, com um valor padrão de NULL.  
  
 [  **@source_scale=** ] *source_scale*  
 É a escala do tipo de dados no DBMS de origem. *source_scale* está **int**, com um valor padrão de NULL.  
  
 [  **@source_nullable=** ] *source_nullable*  
 Especifica se o tipo de dados no DBMS de origem dá suporte a um valor de NULL. *source_nullable* está **bit**, com um valor padrão de **1**, que significa que valores NULL têm suporte.  
  
 [ **@destination_dbms** =] **'***destination_dbms***'**  
 O nome do DBMS de destino. *destination_dbms* está **sysname**, e pode ser um dos seguintes valores:  
  
|Valor|Description|  
|-----------|-----------------|  
|**MSSQLSERVER**|O destino é um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|**ORACLE**|O destino é um banco de dados Oracle.|  
|**DB2**|O destino é um banco de dados IBM DB2.|  
|**SYBASE**|O destino é um banco de dados Sybase.|  
  
 Você deve especificar esse parâmetro.  
  
 [ **@destination_version**=] **'***destination_version***'**  
 É a versão de produto do DBMS de destino. *destination_version* está **varchar(10)**, com um valor padrão de NULL.  
  
 [ **@destination_type**=] **'***destination_type***'** saída  
 É o tipo de dados listado no DBMS de destino. *destination_type* está **sysname**, com um valor padrão de NULL.  
  
 [  **@destination_length=** ] *destination_length* saída  
 É o comprimento do tipo de dados no DBMS de destino. *destination_length* está **bigint**, com um valor padrão de NULL.  
  
 [  **@destination_precision=** ] *destination_precision* saída  
 É a precisão do tipo de dados no DBMS de destino. *destination_precision* está **bigint**, com um valor padrão de NULL.  
  
 [  **@destination_scale=** ] *destination_scale * * * saída**  
 É a escala do tipo de dados no DBMS de destino. *destination_scale* está **int**, com um valor padrão de NULL.  
  
 [  **@destination_nullable=** ] *destination_nullable * * * saída**  
 Especifica se o tipo de dados no DBMS de destino dá suporte a um valor de NULL. *destination_nullable* está **bit**, com um valor padrão de NULL. **1** significa que valores NULL têm suporte.  
  
 [  **@dataloss=** ] *perda de dados * * * saída**  
 Especifica se o mapeamento tem o potencial de perda de dados. *perda de dados* está **bit**, com um valor padrão de NULL. **1** significa que há um potencial perda de dados.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_getdefaultdatatypemapping** é usado em todos os tipos de replicação entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e um não -[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DBMS.  
  
 **sp_getdefaultdatatypemapping** retorna o tipo de dados de destino padrão que é a correspondência mais próxima para o tipo de dados de origem especificado.  
  
## <a name="permissions"></a>Permissões  
 Somente os membros dos **sysadmin** pode executar a função de servidor fixa **sp_getdefaultdatatypemapping**.  
  
## <a name="see-also"></a>Consulte também  
 [sp_helpdatatypemap &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpdatatypemap-transact-sql.md)   
 [sp_setdefaultdatatypemapping &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-setdefaultdatatypemapping-transact-sql.md)   
 [Data Type Mapping for Oracle Publishers](../../relational-databases/replication/non-sql/data-type-mapping-for-oracle-publishers.md)   
 [IBM DB2 Subscribers](../../relational-databases/replication/non-sql/ibm-db2-subscribers.md)   
 [Assinantes Oracle](../../relational-databases/replication/non-sql/oracle-subscribers.md)  
  
  
