---
title: MSSQLSERVER_32042 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 32042 (Database Engine error)
ms.assetid: 53a51c7a-dcd4-4c15-b4d2-6aaa9dce76da
caps.latest.revision: 15
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: b73bdc058ad71cd3b4c3144221f78f6446aa95da
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37423435"
---
# <a name="mssqlserver32042"></a>MSSQLSERVER_32042
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|32042|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|SQLErrorNum32042|  
|Texto da mensagem|O alerta de 'log não enviado' foi interceptado. O valor atual '%d' ultrapassa o limite '%d'.|  
  
## <a name="explanation"></a>Explicação  
 Esse evento de espelhamento de banco de dados é emitido na instância do servidor principal para indicar que a quantidade de logs não enviados alcançou um valor de limite especificado pelo usuário. Normalmente, esse evento acontece porque o desempenho do sistema foi alterado. A largura da banda entre os dois sistemas diminuiu ou a carga aumentou.  
  
 A quantidade de logs não enviados é uma métrica de desempenho que pode ajudá-lo a avaliar o potencial de perda de dados em termos de número de kilobytes (KB) de logs não enviados. Essa métrica é particularmente relevante para sessões em modo de alto desempenho. No entanto, essa métrica também é relevante para uma sessão em modo de segurança alta, quando o espelhamento é pausado ou suspenso devido à desconexão dos parceiros.  
  
## <a name="user-action"></a>Ação do usuário  
 Verifique a causa nas cargas das instâncias do servidor principal e espelho, bem como nas respectivas conexões de rede.  
  
## <a name="see-also"></a>Consulte também  
 [Espelhamento de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md)   
 [Usar os limites de aviso e alertas em métricas de desempenho de espelhamento &#40;SQL Server&#41;](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
