---
title: Inicializar assinaturas | Microsoft Docs
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
- sql12.rep.newsubwizard.initializesubscriptions.f1
ms.assetid: 7b170e4e-470d-4828-a9ed-7435b0b03514
caps.latest.revision: 23
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 6e80b04a7ba6d62ba57d237a61d5fc8b5bec6ec0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37240556"
---
# <a name="initialize-subscriptions"></a>Inicializar Assinaturas
  Os Assinantes devem ser inicializados antes que possam começar a receber dados replicados. Um conjunto de dados inicial não é requerido, mas o Assinante deve ter pelo menos o esquema para cada objeto replicado e todas as tabelas de metadados e procedimentos requeridos pela replicação.  
  
## <a name="options"></a>Opções  
 **Propriedades da assinatura**  
 Marque a caixa de seleção na coluna **Inicializar** para cada Assinante que requer um conjunto de dados inicial. Se a caixa de seleção for desmarcada, somente os metadados de replicação e procedimentos serão inicializados. Para mais informações sobre a inicialização de uma assinatura sem um instantâneo, consulte [Inicializar uma assinatura transacional sem um instantâneo](initialize-a-transactional-subscription-without-a-snapshot.md).  
  
 Selecione **Imediatamente** na caixa de listagem suspensa na coluna **Inicializar Quando** para que o Agente de Mesclagem ou Agente de Distribuição transfira os arquivos de instantâneo para o Assinante depois que o assistente for concluído. Selecione **Na primeira sincronização** para que o agente transfira os arquivos da próxima vez em que for agendado para executar. A opção **Imediatamente** não está disponível para assinaturas pull no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]. O Agente de Mesclagem e Agente de Distribuição não executam em instâncias do [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]; portanto a assinatura deve ser reiniciada por outro método.  
  
> [!NOTE]  
>  O assistente pode solicitar uma conexão com o Distribuidor para iniciar o trabalho apropriado para o Agente de Distribuição ou Agente de Mesclagem.  
  
## <a name="see-also"></a>Consulte também  
 [Create a Pull Subscription](create-a-pull-subscription.md)   
 [Create a Push Subscription](create-a-push-subscription.md)   
 [Inicializar uma assinatura](initialize-a-subscription.md)   
 [Assinar publicações](subscribe-to-publications.md)  
  
  
