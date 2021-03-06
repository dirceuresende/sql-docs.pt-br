---
title: Conectando-se a fontes de dados | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [ADO]
ms.assetid: 82770486-37bd-4c90-885f-6817a7c77ad7
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 4262088b9f7bdf629f5ced8b7916359e3062227d
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35270835"
---
# <a name="connecting-to-data-sources"></a>Conectando-se a fontes de dados
ADO **Conexão** objeto representa uma sessão exclusiva com uma fonte de dados, incluindo um DBMS, um repositório de arquivo ou um arquivo de texto delimitado por vírgula. No caso de um sistema de banco de dados cliente/servidor, a conexão ADO pode ser uma conexão de rede reais para o servidor.  
  
 O **Conexão** objeto oferece suporte a vários [propriedades e métodos](../../../ado/reference/ado-api/connection-object-properties-methods-and-events.md) para especificar configurações de conexão, abertura e fechamento de conexões, criar e executar comandos em relação à fonte de dados e fornecer informações sobre o design de fonte de dados na forma de conjuntos de linhas de esquema, etc. Dependendo da funcionalidade com suporte do provedor, algumas coleções, métodos ou propriedades de um **Conexão** objeto pode não estar disponível.  
  
 Você pode se conectar a uma fonte de dados usando um **Conexão** do objeto ou usando um **registros** objeto.  
  
 Esta seção contém os tópicos a seguir.  
  
-   [Usando um objeto Connection](../../../ado/guide/data/using-a-connection-object.md)  
  
-   [Usando um objeto Recordset](../../../ado/guide/data/using-a-recordset-object.md)  
  
-   [Criando uma cadeia de conexão](../../../ado/guide/data/creating-a-connection-string.md)  
  
-   [Especificando propriedades de conexão](../../../ado/guide/data/specifying-connection-properties.md)  
  
-   [Controle de transações](../../../ado/guide/data/controlling-transactions-ado.md)
