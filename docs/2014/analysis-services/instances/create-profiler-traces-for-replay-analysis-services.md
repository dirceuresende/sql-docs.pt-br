---
title: Criar rastreamentos do Profiler para reprodução (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Profiler, Analysis Services
- monitoring Analysis Services [SQL Server]
- replaying queries
- replaying discovers
- events [Analysis Services]
- replaying commands
- Profiler [SQL Server Profiler], Analysis Services
- performance [Analysis Services], replays
- traces [Analysis Services]
ms.assetid: 93b2fc46-7cfb-4ab5-abeb-1475a7d6f0f2
caps.latest.revision: 32
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 03745df066851279d45d5d6dbd8a536e32025cf4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37169707"
---
# <a name="create-profiler-traces-for-replay-analysis-services"></a>Criar rastreamentos do Profiler para reprodução (Analysis Services)
  Para repetir consultas, identificações e comandos enviados pelos usuários ao [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] deve reunir os eventos necessários. Para iniciar a coleta desses eventos, as classes de evento adequadas devem ser selecionadas na guia **Seleção de Eventos** da caixa de diálogo **Propriedades do Rastreamento** . Por exemplo, se a classe de evento Query Begin for selecionada, os eventos que contêm consultas serão coletados e usados para repetição. Além disso, o arquivo de rastreamento contém informações suficientes para oferecer suporte à repetição das transações de servidor em um ambiente distribuído na sequência original das transações.  
  
## <a name="replay-for-queries"></a>Repetição de consultas  
 Para repetir consultas, o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] deve capturar os seguintes eventos:  
  
-   Classe de evento Audit Login com todas as suas colunas de dados. Essa classe de evento fornece informações sobre qual usuário está conectado e sobre as configurações de sessão. A identificação do processo do servidor (SPID) fornece a referência para a sessão de usuário. Para obter mais informações, consulte [Colunas de dados de auditoria de segurança](../trace-events/security-audit-data-columns.md).  
  
-   Classe de evento Query Begin com todas as suas colunas de dados. Essa classe de evento fornece informações sobre a consulta que foi enviada para o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. A coluna Event Subclass fornece informações sobre o tipo de consulta. A coluna TextData fornece o texto real da consulta. A coluna RequestParameters fornece os parâmetros para consultas parametrizadas, e a coluna RequestProperties fornece as propriedades de uma solicitação XMLA (XML para análise). Para obter mais informações, consulte [Colunas de dados de eventos de consultas](../trace-events/queries-events-data-columns.md).  
  
-   Classe de evento Query End com todas as suas colunas de dados. Essa classe de evento verifica o status da execução de consulta. Para obter mais informações, consulte [Colunas de dados de eventos de consultas](../trace-events/queries-events-data-columns.md).  
  
## <a name="replay-for-discovers"></a>Repetição de identificações  
 Para repetir descobertas, o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] deve capturar os seguintes eventos:  
  
-   Classe de evento Audit Login com todas as suas colunas de dados. Essa classe de evento fornece informações sobre qual usuário está conectado e sobre as configurações de sessão. A SPID fornece a referência para a sessão de usuário. Para obter mais informações, consulte [Colunas de dados de auditoria de segurança](../trace-events/security-audit-data-columns.md).  
  
-   Classe de evento Discover Begin com todas as suas colunas de dados. A coluna TextData fornece o \<RequestType > parte da solicitação de descoberta e a coluna RequestProperties fornece a \<Propriedades > parte da solicitação discover. A coluna EventSubclass fornece o tipo de descoberta. Para obter mais informações, consulte [Colunas de dados de eventos de descoberta](../trace-events/discover-events-data-columns.md).  
  
-   Descobrir a classe de evento de Término com todas as suas colunas de dados. Essa classe de evento verifica o status da solicitação de identificação. Para obter mais informações, consulte [Colunas de dados de eventos de descoberta](../trace-events/discover-events-data-columns.md).  
  
## <a name="replay-for-commands"></a>Repetição de comandos  
 Para repetir comandos, o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] deve capturar os seguintes eventos:  
  
-   Classe de evento Command Begin com todas as suas colunas de dados. A coluna TextData fornece os detalhes do comando, como o tipo de processo, a ID do banco de dados e a ID do cubo. A coluna RequestParameters fornece os parâmetros para comando parametrizado, e a coluna RequestProperties fornece as propriedades de uma solicitação XMLA. Para obter mais informações, consulte [Colunas de dados de eventos de comando](../trace-events/command-events-data-columns.md).  
  
-   Classe de evento Command End com todas as suas colunas de dados. Essa classe de evento verifica o status do comando. Para obter mais informações, consulte [Colunas de dados de eventos de comando](../trace-events/command-events-data-columns.md).  
  
## <a name="see-also"></a>Consulte também  
 [Eventos de rastreamento do Analysis Services](../trace-events/analysis-services-trace-events.md)   
 [Introdução ao monitoramento do Analysis Services com o SQL Server Profiler](introduction-to-monitoring-analysis-services-with-sql-server-profiler.md)  
  
  
