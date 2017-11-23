---
title: sp_fulltext_semantic_unregister_language_statistics_db (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
- sp_fulltext_semantic_unregister_language_statistics_db_TSQL
- sp_fulltext_semantic_unregister_language_statistics_db
dev_langs: TSQL
helpviewer_keywords: sp_fulltext_semantic_unregister_language_statistics_db
ms.assetid: 1426ca4a-9a76-489e-98da-8f6d13ff9732
caps.latest.revision: "11"
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: ecc4cda0f7541a927dbf49294d03562bbbc7475c
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="spfulltextsemanticunregisterlanguagestatisticsdb-transact-sql"></a>sp_fulltext_semantic_unregister_language_statistics_db (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Cancela o registro de um banco de dados de Estatísticas de Idioma Semântico existente da instância atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e exclui todos os metadados associados.  
  
 Essa instrução não desanexa o banco de dados ou remove o arquivo de banco de dados físico do sistema de arquivos. Depois de cancelar o registro do banco de dados, você pode desanexá-lo e excluir o arquivo de banco de dados físico.  
  
||  
|-|  
|**Aplica-se a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] até a [versão atual](http://go.microsoft.com/fwlink/p/?LinkId=299658)).|  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```tsql  
EXEC sp_fulltext_semantic_unregister_language_statistics_db;  
GO  
```  
  
##  <a name="Arguments"></a> Argumentos  
 Esse procedimento não requer nenhum argumento. Como uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tem apenas um banco de dados de estatísticas de idioma semântico, não é necessário identificar o banco de dados.  
  
## <a name="return-code-value"></a>Valor do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="result-set"></a>Conjunto de resultados  
 Nenhum.  
  
## <a name="general-remarks"></a>Comentários gerais  
 Quando o registro de um banco de dados de estatísticas de idioma semântico é cancelado, todos os metadados associados a ele também são removidos.  
  
 **sp_fulltext_semantic_unregister_language_statistics_db** executa as seguintes etapas:  
  
1.  Verifica se não há nenhuma população semântica em progresso para a instância atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
2.  Remove todos os metadados associados ao banco de dados de estatísticas de idioma semântico especificado.  
  
 Para obter mais informações, veja [Instalar e configurar a pesquisa semântica](../../relational-databases/search/install-and-configure-semantic-search.md).  
  
## <a name="metadata"></a>Metadados  
 Para obter informações sobre o banco de dados de estatísticas semânticas de idioma instalado em uma instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte a exibição de catálogo [sys. fulltext_semantic_language_statistics_database &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql.md).  
  
## <a name="security"></a>Segurança  
  
### <a name="permissions"></a>Permissões  
 Requer as permissões CONTROL SERVER.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir mostra como cancelar o registro do banco de dados de estatísticas semânticas de idioma chamando **sp_fulltext_semantic_unregister_language_statistics_db**.  
  
```tsql  
EXEC sp_fulltext_semantic_unregister_language_statistics_db;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Instalar e configurar a pesquisa semântica](../../relational-databases/search/install-and-configure-semantic-search.md)  
  
  