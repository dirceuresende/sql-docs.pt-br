---
title: Especifique as informações de origem (Assistente para partições) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifydsvandfacttables.f1
ms.assetid: b6c13587-c690-45d9-af90-b3d652afc55b
caps.latest.revision: 20
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: c6f60f8470c45e8dbc97de12d7a13b19bea9becb
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37310446"
---
# <a name="specify-source-information-partition-wizard"></a>Especificar Informações sobre a Origem (Assistente para Partições)
  Use a página **Especificar Informações sobre a Origem** para selecionar o grupo de medidas no qual criar a partição e também a exibição da fonte de dados e as tabelas de filtro da partição.  
  
> [!CAUTION]  
>  Se você especificar uma tabela em **Tabelas Disponíveis** que seja usada por outra partição, deverá fornecer uma consulta na página **Restringir Linhas** ou arriscar duplicação de dados no cubo.  
  
## <a name="options"></a>Opções  
 **Grupo de medidas**  
 Selecione um grupo de medidas para esta partição.  
  
 **Look in**  
 Selecione a fonte de dados ou exibição da fonte de dados que contém as tabelas de origem desta partição. A exibição da fonte de dados usada pelo grupo de medidas é selecionada por padrão.  
  
 **Filtrar tabelas**  
 Digite a cadeia de caracteres usada para restringir, por nome de tabela, as tabelas exibidas em **Tabelas disponíveis**.  
  
 **Localizar tabelas**  
 Selecione para atualizar a lista de tabelas em **Tabelas disponíveis**, restringindo ainda mais a lista, se uma cadeia de caracteres tiver sido especificada em **Filtrar tabelas**.  
  
 **Tabelas disponíveis**  
 Selecione as tabelas a serem usadas como tabelas de origem para partições. O **Assistente para Partições** cria uma partição para cada tabela selecionada em **Tabelas Disponíveis**.  
  
 Se nenhum filtro for especificado em **Filtrar tabelas**, essa opção listará todas as tabelas da fonte de dados ou exibição da fonte de dados que são especificadas em **Examinar** e que são semelhantes em estrutura à tabela de fatos usada pelo grupo de medidas especificado em **Grupo de medidas**.  
  
 Se um filtro for especificado em **Filtrar tabelas**, a lista será restringida ainda mais comparando o filtro com os nomes das tabelas que atendem aos critérios anteriores. Apenas as tabelas que contêm a cadeia de caracteres especificada em **Filtrar tabelas** são exibidas.  
  
> [!NOTE]  
>  Se mais de uma tabela for selecionada, a página **Restringir Linhas** não poderá ser exibida e as linhas não poderão ser restringidas para as partições criadas a partir das tabelas selecionadas. Para restringir linhas para cada partição, execute o Assistente para Partições uma vez para cada tabela da qual uma partição deve ser criada.  
  
## <a name="see-also"></a>Consulte também  
 [Partições &#40;Analysis Services - dados multidimensionais&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
