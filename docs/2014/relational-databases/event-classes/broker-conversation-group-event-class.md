---
title: Classe de evento Broker:Conversation Group | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
topic_type:
- apiref
helpviewer_keywords:
- Broker:Conversation Group event class
ms.assetid: 6595bef6-9d40-42eb-a934-735622dd23fb
caps.latest.revision: 24
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 04e8fd6c939774838b306096c9ee3fa91bc3c229
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36121942"
---
# <a name="brokerconversation-group-event-class"></a>classe de evento Broker:Conversation Group
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gera um evento **Broker:Conversation Group** quando o Service Broker cria um novo grupo de conversa ou descarta um grupo de conversa existente.  
  
## <a name="brokerconversation-group-event-class-data-columns"></a>Colunas de dados da classe de evento Broker:Conversation Group  
  
|Coluna de dados|Tipo|Description|Número da coluna|Filtrável|  
|-----------------|----------|-----------------|-------------------|----------------|  
|**ApplicationName**|`nvarchar`|O nome do aplicativo cliente que criou a conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.|10|Sim|  
|**ClientProcessID**|`int`|A ID atribuída pelo computador host ao processo em que está sendo executado o aplicativo cliente. Essa coluna de dados será populada se a ID do processo do cliente for fornecida pelo cliente.|9|Sim|  
|**DatabaseID**|`int`|A ID do banco de dados especificada pela instrução USE *database* ou a ID do banco de dados padrão se nenhuma instrução USE *database* tiver sido emitida para uma determinada instância. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] exibirá o nome do banco de dados se a coluna de dados **ServerName** for capturada no rastreamento e o servidor estiver disponível. Determine o valor para um banco de dados usando a função DB_ID.|3|Sim|  
|**EventClass**|`int`|O tipo de classe de evento capturado. Sempre **136** para **Broker:Conversation Group**.|27|não|  
|**EventSequence**|`int`|Número de sequência para esse evento.|51|não|  
|**EventSubClass**|`nvarchar`|O tipo de subclasse de evento, fornecendo mais informações sobre cada classe de evento. Essa coluna pode conter os seguintes valores:<br /><br /> **Criar**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criou um novo grupo de conversa.<br /><br /> **Drop**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] excluiu um grupo de conversa.|21|Sim|  
|**GUID**|`uniqueidentifier`|O identificador do grupo de conversa que este evento descreve.|54|não|  
|**HostName**|`nvarchar`|O nome do computador no qual o cliente está sendo executado. Essa coluna de dados será populada se o nome do host for fornecido pelo cliente. Para determinar o nome do host, use a função HOST_NAME.|8|Sim|  
|**IsSystem**|`int`|Indica se o evento ocorreu em um processo do sistema ou do usuário. 1 = sistema, 0 = usuário.|60|não|  
|**LoginSid**|`image`|Número SID (identificação de segurança) do usuário que fez logon. Cada SID é exclusivo para cada logon no servidor.|41|Sim|  
|**NTDomainName**|`nvarchar`|O domínio do Windows ao qual o usuário pertence.|7|Sim|  
|**NTUserName**|`nvarchar`|O nome do usuário proprietário da conexão que gerou este evento.|6|Sim|  
|**ServerName**|`nvarchar`|O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo rastreada.|26|não|  
|**SPID**|`int`|A ID de processo do servidor atribuída pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao processo associado ao cliente.|12|Sim|  
|**StartTime**|`datetime`|O horário no qual o evento foi iniciado, quando disponível.|14|Sim|  
|**TransactionID**|`bigint`|ID da transação atribuída pelo sistema.|4|não|  
  
  