---
title: MSSQLSERVER_21889 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 21889 (Database Engine error)
ms.assetid: ae199540-7986-4cc2-b782-cd22793236d3
caps.latest.revision: 6
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 3a42d6959fcf743ea17f582a7aa1c9bf752bd423
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37332206"
---
# <a name="mssqlserver21889"></a>MSSQLSERVER_21889
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|21889|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|SQLErrorNum21889|  
|Texto da mensagem|A instância do SQL Server '% s' não é um publicador de replicação. Execute **sp_adddistributor** na instância '%s' do SQL Server com o distribuidor '%s' para permitir que a instância hospede o banco de dados de publicação '%s'. Certifique-se de especificar as mesmas informações de logon e senha que foram usadas para o publicador original.|  
  
## <a name="explanation"></a>Explicação  
Para hospedar o banco de dados publicador, a instância do SQL Server deve ser um publicador de replicação. **sp_validate_redirected_publisher** chama **sp_helpdistributor** no servidor remoto para determinar se o servidor é um publicador de replicação. Esse erro indica que a instância de destino do SQL Server não é um publicador de replicação.  
  
## <a name="user-action"></a>Ação do usuário  
Execute **sp_adddistributor** na instância do SQL Server que hospeda o banco de dados publicador. Ao executar **sp_adddistributor**, especifique o distribuidor correto. Use o mesmo valor para o parâmetro *@password* que foi usado quando **sp_adddistributor** foi executado inicialmente no distribuidor.  
  
