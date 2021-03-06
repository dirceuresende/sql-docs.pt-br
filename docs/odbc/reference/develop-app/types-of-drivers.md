---
title: Tipos de Drivers | Microsoft Docs
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
- driver compatibility issues [ODBC]
- ODBC drivers [ODBC], backward compatibility
- backward compatibility [ODBC], application and driver compatibility
- compatibility [ODBC], application and driver compatibility
ms.assetid: 864c53c1-b68a-48b6-b6bc-5ecb520bb9dc
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e75e5827becd5457d0e310ca5ec0cc2a13259be5
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32914681"
---
# <a name="types-of-drivers"></a>Tipos de Drivers
Drivers ODBC podem ser classificados da seguinte maneira:  
  
-   **2 de ODBC de 32 bits.**  
     ***x* Driver** driver A 32 bits que:  
  
    -   Exporta somente ODBC 2 *. x* funções.  
  
    -   Exibe o ODBC 2. *x* comportamento para alterações de comportamento.  
  
-   **ISO e abrir um Driver compatível com o grupo** driver A 32 bits que:  
  
    -   Exporta todas as funções que estão documentadas nos documentos Open Group ou a CLI do ISO. Isso inclui algumas das funções que são substituídas no ODBC.  
  
    -   Exibe o comportamento de ODBC 3.0 para alterações de comportamento.  
  
    -   Não necessariamente passa por meio do Gerenciador de Driver ODBC 3.0.  
  
-   **Driver ODBC 3.0** driver A 32 bits que:  
  
    -   Exporta somente funções de ODBC 3.0 menos funções preteridas.  
  
    -   É capaz de apresentando ODBC 2. *x* comportamento ou comportamento de ODBC 3.0 em relação a alterações de comportamento com base no atributo SQL_ATTR_APP_ODBC_VERSION ambiente.  
  
-   **Driver ODBC 3.5 (ou posterior) ANSI** driver A 32 bits que:  
  
    -   Exporta somente funções de ODBC 3.5 menos funções preteridas.  
  
    -   É capaz de apresentando ODBC 2. *x* comportamento ou o comportamento de ODBC 3.0 ou o comportamento de ODBC 3.5 em relação a alterações de comportamento com base no atributo SQL_ATTR_APP_ODBC_VERSION ambiente.  
  
-   **Driver ODBC 3.5 (ou posterior) Unicode** driver A 32 bits que:  
  
    -   Oferece suporte a todos os recursos de um driver de ODBC 3.5 ANSI.  
  
    -   Exporta as versões Unicode da cadeia ODBC todas as APIs.  
  
    -   Pode armazenar e processar dados Unicode na fonte de dados.  
  
> [!NOTE]  
>  drivers ODBC de 16 bits não funcionarão diretamente com o ODBC 3. *x* Gerenciador de Driver. No entanto, é possível para os drivers de 16 bits trabalhar com o Gerenciador de Driver ODBC 2.0, que é subsequentemente conversões até a 3. *x* Gerenciador de Driver.
