---
title: sp_helprotect (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_helprotect
- sp_helprotect_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_helprotect
ms.assetid: faaa3e40-1c95-43c2-9fdc-c61a1d3cc0c3
caps.latest.revision: "24"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 35d41f189e64fc3a4f3420085a371ec4d68ea9cb
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="sphelprotect-transact-sql"></a>sp_helprotect (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna um relatório que tem informações sobre permissões para um objeto ou permissões de instrução, no banco de dados atual.  
  
> [!IMPORTANT]  
>  **sp_helprotect** não retorna informações sobre protegíveis que foram introduzidos no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]. Use [database_permissions](../../relational-databases/system-catalog-views/sys-database-permissions-transact-sql.md) e [fn_builtin_permissions](../../relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql.md) em vez disso.  
  
 Não lista as permissões que sempre são atribuídas às funções de servidor fixas ou funções de banco de dados fixas. Não inclui os logons ou os usuários que recebem permissões com base em sua associação em uma função.  
  
||  
|-|  
|**Aplica-se a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] até a [versão atual](http://go.microsoft.com/fwlink/p/?LinkId=299658)).|  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_helprotect [ [ @name = ] 'object_statement' ]   
     [ , [ @username = ] 'security_account' ]   
     [ , [ @grantorname = ] 'grantor' ]   
     [ , [ @permissionarea = ] 'type' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@name =** ] **'***object_statement***'**  
 É o nome do objeto no banco de dados atual ou uma instrução, que tem as permissões a serem relatadas. *object_statement* é **nvarchar(776)**, com um padrão NULL, que retorna todas as permissões de objeto e a instrução. Se o valor for um objeto (tabela, exibição, procedimento armazenado ou procedimento armazenado estendido), ele deverá ser um objeto válido no banco de dados atual. O nome do objeto pode incluir um qualificador de proprietário no formato *proprietário***.** *objeto*.  
  
 Se *object_statement* é uma instrução, ele pode ser uma instrução CREATE.  
  
 [  **@username =** ] **'***security_account***'**  
 É o nome da entidade de segurança para a qual são retornadas permissões. *security_account* é **sysname**, com um padrão NULL, que retorna todos os objetos de banco de dados atual. *security_account* deve existir no banco de dados atual.  
  
 [  **@grantorname =** ] **'***concessor***'**  
 É o nome da entidade de segurança que concedeu permissões. *o concessor* é **sysname**, com um padrão NULL, que retorna todas as informações de permissões concedidas por qualquer entidade no banco de dados.  
  
 [  **@permissionarea =** ] **'***tipo***'**  
 É uma cadeia de caracteres que indica se deseja exibir permissões de objeto (cadeia de caracteres **o**), permissões de instrução (cadeia de caracteres **s**), ou ambos (**os**). *tipo* é **varchar (10)**, com um padrão de **os**. *tipo* pode ser qualquer combinação de **o** e **s**, com ou sem vírgulas ou espaços entre **o** e **s**.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou 1 (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**Proprietário**|**sysname**|Nome do proprietário do objeto.|  
|**Objeto**|**sysname**|Nome do objeto.|  
|**Usuário autorizado**|**sysname**|Nome do principal para o qual foram concedidas permissões.|  
|**Concessor**|**sysname**|Nome do principal que concedeu permissões ao usuário autorizado especificado.|  
|**ProtectType**|**nvarchar (10)**|Nome do tipo de proteção:<br /><br /> GRANT REVOKE|  
|**Ação**|**nvarchar (60)**|Nome da permissão. As instruções de permissão válidas dependem do tipo de objeto.|  
|**Coluna**|**sysname**|Tipo de permissão:<br /><br /> Todas = Permissão que cobre todas as colunas atuais do objeto.<br /><br /> Nova = Permissão que cobre qualquer coluna nova que possa ser alterada (com a instrução ALTER) no objeto no futuro.<br /><br /> Todas+Nova = combinação de Todas e Nova.<br /><br /> Retornará um ponto se o tipo de permissão não se aplicar às colunas.|  
  
## <a name="remarks"></a>Comentários  
 Todos os parâmetros no procedimento seguinte são opcionais. Se for executado sem parâmetros, o `sp_helprotect` mostra todas as permissões que tenham sido concedidas ou negadas no banco de dados atual.  
  
 Se alguns, mas não todos os parâmetros forem especificados, use parâmetros nomeados para identificar o parâmetro particular ou `NULL` como um espaço reservado.  Por exemplo, para relatar todas as permissões para o proprietário do banco de dados de concessor (`dbo`), execute o seguinte:  
  
```  
EXEC sp_helprotect NULL, NULL, dbo;  
```  
  
 Ou  
  
```  
EXEC sp_helprotect @grantorname = 'dbo';  
```  
  
 O relatório de saída é classificado por categoria de permissão, proprietário, usuário autorizado, concessor, categoria de tipo de proteção, tipo de proteção, ação e ID sequencial de coluna.  
  
## <a name="permissions"></a>Permissões  
 Requer associação à função **pública** .  
  
 As informações retornadas estão sujeitas a restrições no acesso para metadados. Entidades em que o principal não tem nenhuma permissão não aparecem. Para obter mais informações, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-listing-the-permissions-for-a-table"></a>A. Listando as permissões de uma tabela  
 O exemplo seguinte lista as permissões para a tabela `titles`.  
  
```  
EXEC sp_helprotect 'titles';  
```  
  
### <a name="b-listing-the-permissions-for-a-user"></a>B. Listando as permissões de um usuário  
 O exemplo seguinte lista todas as permissões que usuário `Judy` tem no banco de dados atual.  
  
```  
EXEC sp_helprotect NULL, 'Judy';  
```  
  
### <a name="c-listing-the-permissions-granted-by-a-specific-user"></a>C. Listando as permissões concedidas por um usuário específico  
 O exemplo a seguir lista todas as permissões que foram concedidas pelo usuário `Judy` no banco de dados atual, e usa o `NULL` como um espaço reservado para os parâmetros faltantes.  
  
```  
EXEC sp_helprotect NULL, NULL, 'Judy';  
```  
  
### <a name="d-listing-the-statement-permissions-only"></a>D. Listando apenas as permissões de instruções  
 O exemplo a seguir lista todas as permissões de instrução no banco de dados atual e usa o `NULL` como um espaço reservado para os parâmetros ausentes.  
  
```  
EXEC sp_helprotect NULL, NULL, NULL, 's';   
```  
  
### <a name="e-listing-the-permissions-for-a-create-statement"></a>e. Listando as permissões de uma instrução CREATE  
 O exemplo a seguir lista todos os usuários que receberam a permissão CREATE TABLE.  
  
```  
EXEC sp_helprotect @name = 'CREATE TABLE';  
```  
  
## <a name="see-also"></a>Consulte também  
 [Segurança armazenados procedimentos &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [DENY &#40;Transact-SQL&#41;](../../t-sql/statements/deny-transact-sql.md)   
 [GRANT &#40;Transact-SQL&#41;](../../t-sql/statements/grant-transact-sql.md)   
 [REVOKE &#40;Transact-SQL&#41;](../../t-sql/statements/revoke-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  