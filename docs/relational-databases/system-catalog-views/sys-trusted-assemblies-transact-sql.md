---
title: sys.trusted_assemblies (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- trusted_assemblies_TSQL
- trusted_assemblies
- sys.trusted_assemblies_TSQL
- sys.trusted_assemblies
dev_langs:
- TSQL
helpviewer_keywords:
- sys.trusted_assemblies
ms.assetid: ''
author: VanMSFT
ms.author: vanto
manager: craigg
monikerRange: '>=sql-server-2017||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 989233e4e13a26b316a554a908a1282d384565f6
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43081079"
---
# <a name="systrustedassemblies-transact-sql"></a>sys.trusted_assemblies (Transact-SQL)  
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]

Contém uma linha para cada assembly confiável para o servidor.

 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  


|Nome da coluna |Tipo de dados |Description |
|--- |--- |--- |
|hash |varbinary(8000) |SHA2_512 o hash do conteúdo do assembly. |
|descrição |nvarchar(4000) |Descrição opcional definida pelo usuário do assembly. A Microsoft recomenda usar o nome canônico que codifica o nome simples, número de versão, cultura, chave pública e arquitetura do assembly para confiar. Esse valor identifica o assembly do lado common language runtime (CLR) exclusivamente e é o mesmo que o valor de clr_name em sys. assemblies. |
|create_date |datetime2 |Data em que o assembly foi adicionado à lista de assemblies confiáveis. |
|created_by |nvarchar(128) |Nome de logon da entidade de segurança que adicionou o assembly à lista. |
| | | |


## <a name="remarks"></a>Remarks  

Use **precisa adicionar sp_add_trusted_assembly** e **precisará adicionar o sys.trusted_assemblies** adicionar ou remover assemblies de `sys.trusted_assemblies`.

## <a name="see-also"></a>Consulte também  
  [sys.sp_add_trusted_assembly](../../relational-databases/system-stored-procedures/sys-sp-add-trusted-assembly-transact-sql.md) [sys.sp_drop_trusted_assembly](../../relational-databases/system-stored-procedures/sys-sp-drop-trusted-assembly-transact-sql.md) [DROP ASSEMBLY &#40;Transact-SQL&#41;](../../t-sql/statements/drop-assembly-transact-sql.md)  
  [sys.assemblies](../../relational-databases/system-catalog-views/sys-assemblies-transact-sql.md)  
  [sys.dm_clr_loaded_assemblies](../../relational-databases/system-dynamic-management-views/sys-dm-clr-loaded-assemblies-transact-sql.md)  

