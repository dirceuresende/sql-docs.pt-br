---
title: Segurança do Queue Reader Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.QRA.f1
helpviewer_keywords:
- Queue Reader Agent Security dialog box
ms.assetid: 77938da0-2afd-4455-8826-f4a6a9440cb3
caps.latest.revision: 20
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: cae324f810da7a1cea684ae1ea0d720ddd788329
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37206736"
---
# <a name="queue-reader-agent-security"></a>Segurança do Agente de Leitor de Fila
  A caixa de diálogo **Segurança do Agente de Leitor de Fila** permite que você especifique a conta [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows na qual o Agente de Leitor de Fila executa e faz conexões locais com o Distribuidor. O agente se conecta ao Publicador usando a conta especificada na caixa de diálogo **Propriedades do Publicador** (disponível na caixa de diálogo **Propriedades do Distribuidor** ); o agente se conecta ao Assinante usando o mesmo contexto do Agente de Distribuição para a assinatura. Para obter mais informações, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).  
  
 A conta deve ser válida, com a senha correta especificada. Contas e senhas não são validadas até que um agente seja executado.  
  
## <a name="options"></a>Opções  
 **Conta do processo**  
 Insira uma conta do Windows na qual o Agente de Leitor de Fila seja executado no Distribuidor. A conta do Windows especificada deve ser, no mínimo, um membro da função de banco de dados fixa **db_owner** no banco de dados de distribuição.  
  
 **Senha** e **Confirmar Senha**  
 Insira a senha para a conta do Windows.  
  
## <a name="see-also"></a>Consulte também  
 [Gerenciar logons e senhas na replicação](security/manage-logins-and-passwords-in-replication.md)   
 [Modelo de segurança do agente de replicação](security/replication-agent-security-model.md)   
 [Visão geral dos agentes de replicação](agents/replication-agents-overview.md)   
 [Replication Security Best Practices](security/replication-security-best-practices.md)  
  
  
