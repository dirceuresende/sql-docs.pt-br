---
title: Fontes de dados | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- data sources [ODBC]
- data sources [ODBC], about data sources
ms.assetid: 4ae44fa2-0b9b-4e19-ab45-c1dc93b68406
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c3a57a40e301b565998a5eff86b7d631f1bc8e7a
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32911821"
---
# <a name="data-sources"></a>Fontes de Dados
Um *fonte de dados* é simplesmente a fonte de dados. Ele pode ser um arquivo, um banco de dados específico em um DBMS ou até mesmo um feed de dados ao vivo. Os dados podem ser localizados no mesmo computador que o programa, ou em outro computador em algum lugar em uma rede. Por exemplo, uma fonte de dados pode ser um DBMS do Oracle em execução em um sistema de operacional OS/2®, acessado por Novell® Netware; um DBMS de DB2 da IBM acessados por meio de um gateway. uma coleção de arquivos Xbase em um diretório de servidor. ou um arquivo de banco de dados local do Microsoft® Access.  
  
 A finalidade de uma fonte de dados é reunir todas as informações técnicas necessárias para acessar os dados — o nome do driver, endereço de rede, software de rede e assim por diante — em uma única colocar e ocultá-lo do usuário. O usuário deve ser capaz de ver uma lista que inclui a folha de pagamento, inventário e pessoal, escolha da folha de pagamento da lista e têm o aplicativo se conectar aos dados da folha de pagamento, tudo sem saber onde residem os dados de folha de pagamento ou como o aplicativo obteve a ele.  
  
 O termo *fonte de dados* não deve ser confundido com termos semelhantes. Esse manual *DBMS* ou *banco de dados* refere-se a um programa de banco de dados ou o mecanismo. Outra distinção é feita entre *bancos de dados de área de trabalho,* projetado para ser executado em computadores pessoais e geralmente está faltando no SQL completo e o suporte a transações, e *bancos de dados do servidor,* projetado para ser executado em um cliente / situação de servidor e caracterizados por um mecanismo de banco de dados independente e SQL avançada e suporte a transações. *Banco de dados* também se refere a uma coleção específica de dados, como uma coleção de arquivos Xbase em um diretório ou um banco de dados no SQL Server. É geralmente equivalente para o termo *catálogo,* usado em outro local neste manual ou o termo *qualificador* em versões anteriores do ODBC.  
  
 Esta seção contém os tópicos a seguir.  
  
-   [Tipos de fontes de dados](../../odbc/reference/types-of-data-sources.md)  
  
-   [Usando fontes de dados](../../odbc/reference/using-data-sources.md)  
  
-   [Exemplo de fonte de dados](../../odbc/reference/data-source-example.md)
