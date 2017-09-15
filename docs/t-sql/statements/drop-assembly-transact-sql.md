---
title: DROP ASSEMBLY (Transact-SQL) | Microsoft Docs
ms.custom:
- SQL2016_New_Updated
ms.date: 05/10/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROP ASSEMBLY
- DROP_ASSEMBLY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- deleting assemblies
- assemblies [CLR integration], removing
- dropping assemblies
- WITH NO DEPENDENTS option
ms.assetid: 452d181a-a8e6-44a3-975d-29966d01b18d
caps.latest.revision: 32
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: c38654a3ce90b4e1605cfdbe1db7a49ddac8b6b1
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="drop-assembly-transact-sql"></a>DROP ASSEMBLY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Remove um assembly e todos os seus arquivos associados do banco de dados atual. Os assemblies são criados usando [CREATE ASSEMBLY](../../t-sql/statements/create-assembly-transact-sql.md) e modificados usando [ALTER ASSEMBLY](../../t-sql/statements/alter-assembly-transact-sql.md).  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
DROP ASSEMBLY [ IF EXISTS ] assembly_name [ ,...n ]  
[ WITH NO DEPENDENTS ]  
[ ; ]  
```  
  
## <a name="arguments"></a>Argumentos  
 *SE EXISTIR*  
 **Aplica-se a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] até a [versão atual](http://go.microsoft.com/fwlink/p/?LinkId=299658)).  
  
 Condicionalmente descarta o assembly apenas se ele já existe.  
  
 *nome_do_assembly*  
 É o nome do assembly que você deseja descartar.  
  
 WITH NO DEPENDENTS  
 Se especificado, descarta somente *nome_do_assembly* e nenhum dos assemblies dependentes que são referenciados pelo assembly. Se não for especificado, DROP ASSEMBLY descarta *nome_do_assembly* e todos os assemblies dependentes.  
  
## <a name="remarks"></a>Comentários  
 O descarte de um assembly remove o mesmo e todos os seus arquivos associados, tais como código fonte e arquivos de depuração, do banco de dados  
  
 Se WITH NO DEPENDENTS não for especificado, DROP ASSEMBLY descarta *nome_do_assembly* e todos os assemblies dependentes. Se houver falha em uma tentativa de descarte de quaisquer assemblies dependentes, DROP ASSEMBLY retornará um erro.  
  
 DROP ASSEMBLY retornará um erro se o assembly for referenciado por outro assembly que exista no banco de dados ou se for usado por funções CLR (Common Language Runtime), procedimentos armazenados, disparadores, tipos definidos pelo usuário ou agregações no banco de dados atual.  
  
 DROP ASSEMBLY não interfere em nenhum código que faça referência ao assembly que está atualmente em execução. Entretanto, depois que DROP ASSEMBLY for executado, quaisquer tentativas de invocar o código do assembly falharão.  
  
## <a name="permissions"></a>Permissões  
 Requer propriedade do assembly ou permissão CONTROL no mesmo.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir assume que o assembly `HelloWorld` já está criado na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
```  
DROP ASSEMBLY Helloworld ;  
```  
  
## <a name="see-also"></a>Consulte também  
 [Criar ASSEMBLY &#40; Transact-SQL &#41;](../../t-sql/statements/create-assembly-transact-sql.md)   
 [ALTER ASSEMBLY &#40; Transact-SQL &#41;](../../t-sql/statements/alter-assembly-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [Obtendo informações sobre Assemblies](../../relational-databases/clr-integration/assemblies-getting-information.md)  
  
  
