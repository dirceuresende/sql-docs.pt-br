---
title: Posicionamento do conjunto de registros | Microsoft Docs
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- record positioning [ADO]
- Recordset object [ADO]
- repositioning record [ADO]
- AbsolutePosition property [ADO]
ms.assetid: c8f6fbcb-6675-4133-b37e-430de43949c1
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0bb579a63f25207d44f5211afca78831d5cabaad
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="recordset-positioning"></a>Posicionamento do conjunto de registros
Use o **AbsolutePosition** propriedade mover para um registro, com base em sua posição ordinal no **registros** objeto, ou para determinar a posição ordinal do registro atual. O provedor deve oferecer suporte a funcionalidade apropriada para essa propriedade disponível.  
  
 **AbsolutePosition** é baseado em 1 e é igual a 1 quando o registro atual é o primeiro registro no **registros**. Conforme mencionado anteriormente, você pode obter o número total de registros a **Recordset** de objeto o **RecordCount** propriedade.  
  
 Quando você define o **AbsolutePosition** propriedade, mesmo se ele é um registro no cache atual, ADO recarrega o cache com um novo grupo de registros que começam com o registro especificado. O **CacheSize** propriedade determina o tamanho desse grupo.  
  
> [!NOTE]
>  Você não deve usar o **AbsolutePosition** a propriedade como um número de registro de substitutos. A posição de um determinado registro muda quando você excluir um registro anterior. Também não há nenhuma garantia de que um determinado registro terá o mesmo **AbsolutePosition** se o **registros** objeto é novamente consultado ou reaberto. Indicadores são a maneira recomendada de reter e retornar para uma determinada posição e são a única maneira de posicionamento de todos os tipos de **registros** objetos.