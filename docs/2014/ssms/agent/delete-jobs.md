---
title: Excluir trabalhos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 62b61345e68a6f47ffe8e3a51b1e59343b7d597c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37153467"
---
# <a name="delete-jobs"></a>Excluir trabalhos
  Um trabalho é uma série especificada de operações executadas sequencialmente pelo SQL Server Agent. Por padrão, os trabalhos não são excluídos quando a execução termina. Você pode excluir um ou mais trabalhos do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent independentemente do êxito ou da falha do trabalho. Também é possível configurar o [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para excluir trabalhos automaticamente quando eles obtiverem êxito, falharem ou forem concluídos.  
  
 Por padrão, os membros a **sysadmin** pode executar a função de servidor fixa a [sp_delete_job &#40;Transact-SQL&#41; ](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) procedimento para excluir um trabalho armazenado do sistema. Deve ser concedida a outros usuários uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados **msdb** :  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 Para obter detalhes sobre as permissões dessas funções, consulte [Funções de banco de dados fixas do SQL Server Agent](sql-server-agent-fixed-database-roles.md).  
  
 Membros da função de servidor fixa **sysadmin** podem executar **sp_delete_job** para excluir qualquer trabalho. Um usuário que não for membro da função de servidor fixa **sysadmin** poderá excluir somente os trabalhos que forem de sua propriedade.  
  
## <a name="related-tasks"></a>Related Tasks  
  
|||  
|-|-|  
|**Descrição**|**Tópico**|  
|Descreve como excluir um ou mais trabalhos do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.|[Excluir um ou mais trabalhos](delete-one-or-more-jobs.md)|  
|Descreve como configurar o [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para excluir trabalhos automaticamente quando eles obtiverem êxito, falharem ou forem concluídos.|[Automatically Delete a Job](automatically-delete-a-job.md)|  
  
  
