---
title: Conjunto de linhas LINKEDSERVERS (OLE DB) | Microsoft Docs
description: Conjunto de linhas LINKEDSERVERS (OLE DB)
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: ole-db
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- LINKEDSERVERS rowset
- enumerating data sources [OLE DB]
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b00a600f2690981f152c75c92dc467c1d6d13aed
ms.sourcegitcommit: 9351e8b7b68f599a95fb8e76930ab886db737e5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2018
---
# <a name="schema-rowsets---linkedservers-rowset"></a>Conjuntos de linhas de esquema - conjunto de linhas LINKEDSERVERS
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  O **LINKEDSERVERS** linhas enumera fontes de dados da organização que podem participar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] consultas distribuídas.  
  
 O conjunto de linhas **LINKEDSERVERS** contém as seguintes colunas.  
  
|Nome da coluna|Indicador de tipo|Description|  
|-----------------|--------------------|-----------------|  
|SVR_NAME|DBTYPE_WSTR|Nome de um servidor vinculado.|  
|SVR_PRODUCT|DBTYPE_WSTR|Fabricante ou outro nome que identifique o tipo de repositório de dados representado pelo nome do servidor vinculado.|  
|SVR_PROVIDERNAME|DBTYPE_WSTR|Nome amigável do provedor OLE DB usado para consumir dados do servidor.|  
|SVR_DATASOURCE|DBTYPE_WSTR|Cadeia de caracteres OLE DB DBPROP_INIT_DATASOURCE usada para adquirir uma fonte de dados do provedor.|  
|SVR_PROVIDERSTRING|DBTYPE_WSTR|Valor DBPROP_INIT_PROVIDERSTRING do OLE DB usado para adquirir uma fonte de dados do provedor.|  
|SVR_LOCATION|DBTYPE_WSTR|Cadeia de caracteres de DBPROP_INIT_LOCATION do OLE DB usada para adquirir uma fonte de dados do provedor.|  
  
 O conjunto de linhas é classificado em SRV_NAME, havendo suporte a uma única restrição em SRV_NAME.  
  
## <a name="see-also"></a>Consulte também  
 [Suporte ao conjunto de linhas de esquema &#40;OLE DB&#41;](../../oledb/ole-db/schema-rowset-support-ole-db.md)  
  
  