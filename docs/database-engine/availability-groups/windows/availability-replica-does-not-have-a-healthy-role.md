---
title: A réplica de disponibilidade não tem uma função íntegra | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.swb.agdashboard.arp1rolehealthy.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: ebb2c9f4-2097-4688-b4fb-8f0571047317
caps.latest.revision: 13
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: efe3fa11a9f009e8251f9c559df5855717754c23
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34771562"
---
# <a name="availability-replica-does-not-have-a-healthy-role"></a>A réplica de disponibilidade não têm uma função íntegra
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="introduction"></a>Introdução  
  
|||  
|-|-|  
|**Nome da Política**|Estado da função da réplica de disponibilidade|  
|**Problema**|A réplica de disponibilidade não tem uma função íntegra.|  
|**Categoria**|**Crítico**|  
|**Faceta**|Réplica de disponibilidade|  
  
## <a name="description"></a>Descrição  
 Esta política verifica o estado da função da réplica de disponibilidade. O estado da política é não íntegro quando a função da réplica de disponibilidade não é primária nem secundária. Caso contrário, a política estará em um estado íntegro.  
  
> [!NOTE]  
>  Para esta versão do [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], as informações sobre as possíveis causas e soluções estão localizadas em [A réplica de disponibilidade não tem uma função íntegra](http://go.microsoft.com/fwlink/p/?LinkId=220856) no Wiki do TechNet.  
  
## <a name="possible-causes"></a>Causas possíveis  
 A função desta réplica de disponibilidade é não íntegra. A réplica não tem a função primária ou secundária.  
  
## <a name="possible-solution-informationstilltocome"></a>Solução possível: Information_still_to_come  
  
## <a name="see-also"></a>Consulte Também  
 [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)   
 [Usar o Painel AlwaysOn &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
