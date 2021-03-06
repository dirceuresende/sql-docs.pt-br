---
title: Migrar logons do SQL Server com o Assistente de migração de dados | Microsoft Docs
description: Saiba como migrar logons do SQL Server com o Assistente de migração de dados
ms.custom: ''
ms.date: 08/29/2018
ms.prod: sql
ms.prod_service: dma
ms.reviewer: ''
ms.suite: sql
ms.technology: dma
ms.tgt_pltfrm: ''
ms.topic: conceptual
keywords: ''
helpviewer_keywords:
- Data Migration Assistant, login migration
ms.assetid: ''
caps.latest.revision: ''
author: HJToland3
ms.author: rajpo
manager: craigg
ms.openlocfilehash: 271cb804b63b7adc400f21e6ccbe8e95eb0de307
ms.sourcegitcommit: fb269accc3786715c78f8b6e2ec38783a6eb63e9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43152707"
---
# <a name="migrate-sql-server-logins-with-data-migration-assistant"></a>Migrar logons do SQL Server com o Assistente de migração de dados

Este artigo fornece uma visão geral da migração logons do SQL Server usando o Assistente de migração de dados. 

## <a name="which-logins-are-migrated"></a>Quais logons são migradas

- Você pode migrar os logons com base em uma entidade de segurança do Windows (como um usuário de domínio ou um grupo de domínio do Windows). Também é possível migrar logons criados com base na autenticação do SQL, também chamada de logons do SQL Server.

- Assistente de migração de dados atualmente não dá suporte os logons associados com um certificado de segurança autônomo (logons mapeados para certificado), uma chave assimétrica autônoma (logons mapeados para chave assimétrica) e logons mapeados para as credenciais.

- Assistente de migração de dados não move os **sa** princípios de logon e o servidor com nomes entre duas marcas hash (\#\#), que são somente para uso interno.

- Por padrão, o Assistente de migração de dados seleciona todos os logons qualificados para migrar. Opcionalmente, você pode selecionar logons específicos para migrar. Quando o Assistente de migração de dados migra todos os logons qualificados, o mapeamento de logon do usuário permanece intacto nos bancos de dados que são migrados. 

  Se você planeja migrar logons específicos, certifique-se de selecionar os logons que são mapeados para um ou mais usuários em bancos de dados selecionados para migração.

- Como parte da migração de logon, Assistente de migração de dados também move as funções definidas pelo usuário e adiciona permissões em nível de servidor às funções de servidor definidas pelo usuário. O proprietário da função será definido como **sa** principal.

## <a name="during-and-after-migration"></a>Durante e após a migração

- Como parte da migração de logon, Assistente de migração de dados atribui as permissões para protegíveis no SQL Server de destino como eles existem no SQL Server de origem. 

  Se o logon já existe no destino do SQL Server, Assistente de migração de dados migra apenas as permissões atribuídas a protegíveis e não criará o logon inteiro novamente.

- Assistente de migração de dados torna o melhor esforço para mapear o logon para usuários de banco de dados se o logon já existe no servidor de destino.

- É recomendável que você examine os resultados da migração para entender o status geral de migração de logon e todas as ações recomendadas após a migração.

## <a name="resources"></a>Recursos

[Assistente de migração de dados (DMA)](../dma/dma-overview.md)

[Assistente de migração de dados: Definições de configuração](../dma/dma-configurationsettings.md)
