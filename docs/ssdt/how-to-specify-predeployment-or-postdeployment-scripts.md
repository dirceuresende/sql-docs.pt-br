---
title: Como especificar scripts de pré-implantação ou pós-implantação| Microsoft Docs
ms.custom:
- SSDT
ms.date: 02/09/2017
ms.prod: sql
ms.technology: ssdt
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 7f78f517-f13d-4f4b-84b9-e804cb490b2c
caps.latest.revision: 7
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 1d7b1e6537aa58d06d21eb3df0b4523bfd703252
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39087128"
---
# <a name="how-to-specify-predeployment-or-postdeployment-scripts"></a>Como especificar scripts de pré-implantação ou pós-implantação
Os scripts de pré-implantação e pós-implantação executam instruções do Transact\-SQL antes e após o script de implantação principal, que é gerado do projeto de banco de dados. Um projeto pode ter somente um script de pré-implantação e um de pós-implantação. Esses scripts podem ser usados para várias finalidades. Por exemplo:  
  
-   Um script de pré-implantação pode copiar dados de uma tabela que está sendo alterada em uma tabela temporária antes de reformatar e aplicar os dados na tabela alterada em um script de pós-implantação,  
  
-   Você pode inserir dados de referência que devem existir em uma tabela em um script de pós-implantação. Antes de inserir os dados, você pode conferir se a tabela já contém dados. Se a tabela não estiver vazia, você deverá limpar os dados existentes ou especificar que deseja recriar sempre o banco de dados antes de implantá-lo. Você pode adicionar uma instrução como a seguinte ao script de pós-implantação:  
  
```  
IF (EXISTS(SELECT * FROM [dbo].[MyReferenceTable]))  
BEGIN  
    DELETE FROM [dbo].[MyReferenceTable]  
END  
```  
  
## <a name="to-add-and-modify-a-pre--or-post-deployment-script"></a>Para adicionar e modificar um script de pré ou pós-implantação.  
  
1.  No **Gerenciador de Soluções**, expanda seu projeto de banco de dados para exibir a pasta Scripts.  
  
2.  Clique com o botão direito do mouse na pasta Scripts e selecione Adicionar.  
  
3.  Selecione Scripts no menu de contexto.  
  
4.  Selecione o script de pré-implantação ou pós-implantação. Opcionalmente, especifique um nome não padrão. Clique em Adicionar para concluir.  
  
5.  Clique duas vezes na pasta Scripts.  
  
    O editor Transact\-SQL é aberto, exibindo o conteúdo do arquivo.  
  
Você pode usar a sintaxe e as variáveis SQLCMD em seus scripts e defini-los nas propriedades do projeto de banco de dados. Por exemplo:  
  
-   Você pode usar a sintaxe SQLCMD para incluir o conteúdo de um arquivo em um script de pré ou pós-implantação. Os arquivos são incluídos e executados na ordem que você definir: `:r .\myfile.sql`  
  
-   Você pode usar a sintaxe SQLCMD para referenciar uma variável no script de pós-implantação. Você define a variável SQLCMD nas propriedades do projeto ou em um perfil de publicação:  
  
    ```  
    :setvar TableName MyTable  
    SELECT * FROM [$(TableName)]  
    ```  
  
Para saber mais sobre como usar SQLCMD em scripts, consulte [Configurações de projeto de banco de dado](../ssdt/database-project-settings.md).  
  
## <a name="see-also"></a>Consulte Também  
[Desenvolvimento de banco de dados offline orientado a projetos](../ssdt/project-oriented-offline-database-development.md)  
  
