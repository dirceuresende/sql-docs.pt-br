---
title: Modelo de objeto SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: smo
ms.reviewer: ''
ms.suite: sql
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
caps.latest.revision: 30
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 3dc54f13f4cd16f4dc5db9d16e0c9ec1a85544ce
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43068523"
---
# <a name="smo-object-model"></a>Modelo de objeto SMO
[!INCLUDE[appliesto-ss-asdb-asdw-xxx-md](../../includes/appliesto-ss-asdb-asdw-xxx-md.md)]

  O modelo de objeto SMO é composto de uma hierarquia de objetos. O objeto <xref:Microsoft.SqlServer.Management.Smo.Server> é o objeto de nível superior e todos os objetos de classe de instância residem sob o objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.  
  
 A classe <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> é uma classe de nível superior com uma hierarquia de objetos separada. O <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objeto representa [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] serviços e configurações de rede disponíveis por meio do provedor WMI.  
  
 Além dos objetos <xref:Microsoft.SqlServer.Management.Smo.Server> e <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>, há várias classes de utilitário que representam tarefas ou operações, como <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup> ou <xref:Microsoft.SqlServer.Management.Smo.Restore>  
  
 O modelo de objeto SMO é composto de vários namespaces. Para obter mais informações, consulte o [Namespaces do SMO](../../relational-databases/server-management-objects-smo/smo-object-model-namespaces.md).  
  
## <a name="see-also"></a>Consulte também  
 [Diagrama de modelo de objeto do SMO](../../relational-databases/server-management-objects-smo/smo-object-model-diagram.md)   
 [Namespaces do SMO](../../relational-databases/server-management-objects-smo/smo-object-model-namespaces.md)   
 [Provedor WMI para conceitos de gerenciamento de configuração](../../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
