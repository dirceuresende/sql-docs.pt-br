---
title: Backup e carregando hardware - Parallel Data Warehouse
description: Para implantar seu ponta a ponta solução do data warehouse em Analytics Platform System (APS) com o Parallel Data Warehouse (PDW), você precisa criar um plano de backup do data warehouse e o carregamento de dados. Use este guia para adquirir e configurar servidores de backup e carregar que atenda às suas necessidades de negócios.
author: mzaman1
manager: craigg
ms.prod: sql
ms.technology: data-warehouse
ms.topic: conceptual
ms.date: 04/17/2018
ms.author: murshedz
ms.reviewer: martinle
ms.openlocfilehash: 4d7f7b6b4edea9dacab7287a7936b7fd87fd7973
ms.sourcegitcommit: 056ce753c2d6b85cd78be4fc6a29c2b4daaaf26c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31544728"
---
# <a name="backup-and-loading-hardware-overview---parallel-data-warehouse"></a>Backup e carregamento de visão geral de hardware – Parallel Data Warehouse
Para implantar seu ponta a ponta solução do data warehouse em Analytics Platform System (APS) com o Parallel Data Warehouse (PDW), você precisa criar um plano de backup do data warehouse e o carregamento de dados. Use este guia para adquirir e configurar servidores de backup e carregar que atenda às suas necessidades de negócios.  
  
## <a name="acquire-and-configure-backup-servers"></a>Adquirir e configurar servidores de backup  
![Processo de backup](media/backup-process.png "processo de Backup")  
  
Para fazer backup de um banco de dados PDW, você precisa de um ou mais servidores de backup. Você pode usar seu próprio hardware existente ou adquirir novo hardware. Para obter mais informações, consulte [adquirir e configurar um servidor de Backup](acquire-and-configure-backup-server.md). Essas instruções incluem um [planilha de planejamento de capacidade do servidor de Backup](backup-capacity-planning-worksheet.md) para ajudá-lo a planejar a solução certa para backup.  
  
## <a name="acquire-and-configure-loading-servers"></a>Adquirir e configurar servidores de carregamento  
![Processo de carregamento](media/loading-process.png "processo de carregamento")  
  
Para carregar dados, você precisa de um ou mais servidores de carregamento. Você pode usar seu próprio ETL existente ou outros servidores, ou você pode adquirir novos servidores. Para obter mais informações, consulte [adquirir e configurar um servidor de carregamento](acquire-and-configure-loading-server.md). Essas instruções incluem um [carregar planilha de planejamento de capacidade do servidor](loading-server-capacity-planning-worksheet.md) para ajudá-lo a planejar a solução certa para carregamento.  
  
## <a name="see-also"></a>Consulte também  
[Visão geral de backup e restauração](backup-and-restore-overview.md)  
[Visão geral de carga](load-overview.md)  
  
