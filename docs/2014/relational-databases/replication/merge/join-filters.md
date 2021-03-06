---
title: Filtros de junção | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server replication], join
- publications [SQL Server replication], join filters
- merge replication join filters [SQL Server replication]
- join filters
ms.assetid: dd78fd8f-56e3-4582-9abd-6bc25c91e075
caps.latest.revision: 37
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 14a87090d28b91744fcfb9328045d8aa00c1022c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37154477"
---
# <a name="join-filters"></a>filtros de junção
  Um filtro de junção permite que uma tabela seja filtrada com base na forma pela qual uma tabela relacionada é filtrada na publicação. Geralmente uma tabela pai é filtrada usando um filtro de linha com parâmetros; depois um ou mais filtros de junção são definidos da mesma forma que se define junções entre tabelas. Os filtros de junção estendem os filtros com parâmetros para que os dados nas tabelas relacionadas sejam replicados somente se corresponderem à cláusula do filtro de junção.  
  
 Os filtros de junção geralmente seguem as relações chave primária/chave estrangeira definidas para as tabelas nas quais são aplicados, mas não estão estritamente limitados a essas relações. O filtro de junção pode ser baseado em qualquer lógica que compare dados relacionados em duas tabelas.  
  
 Considere as seguintes tabelas no banco de dados de exemplo [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] que estão relacionadas por chave primária para relações de chave estrangeira:  
  
-   **HumanResources.Employee**  
  
-   **Sales.SalesOrderHeader**  
  
-   **Sales.SalesOrderDetail**  
  
 Essas tabelas podem ser usadas em um aplicativo para fornecer suporte a uma força de vendas móvel, mas precisam ser filtradas para que cada vendedor na tabela **HumanResources.Employee** receba apenas os dados relevantes aos pedidos de seus clientes.  
  
 A primeira etapa é definir um filtro com parâmetros na tabela pai que, neste exemplo, é a tabela **HumanResources.Employee** . Essa tabela inclui a coluna **LoginID**que contém o logon para cada funcionário no formulário *domain\login*. Para filtrar essa tabela de forma que cada funcionário receba apenas os dados relacionados a ele, especifique uma cláusula de filtro com parâmetros de:  
  
```  
LoginID = SUSER_SNAME()  
```  
  
 Esse filtro garante que a assinatura de cada funcionário só contenha os dados da tabela **HumanResources.Employee** que sejam relevantes para esse funcionário (que, neste caso, é uma linha simples). Para obter mais informações, consulte [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).  
  
 A próxima etapa é estender esse filtro a cada tabela relacionada, usando sintaxe similar à que foi usada para especificar uma junção entre as duas tabelas. A primeira cláusula de filtro de junção é:  
  
```  
Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
```  
  
 Isso assegura que a assinatura contenha só os dados de pedido pertinentes a cada vendedor. A segunda cláusula de filtro de junção é:  
  
```  
SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
```  
  
 Isso assegura que a assinatura contenha só os dados detalhados relativos aos dados de pedido de cada vendedor. Esse exemplo mostra uma tabela única com junção em cada ponto; também é possível realizar junção em mais de uma tabela em cada ponto.  
  
 Os filtros de junção podem ser adicionados um por vez por meio do Assistente para Nova Publicação e da caixa de diálogo **Propriedades da Publicação** , ou podem ser adicionados programaticamente. Eles também podem ser gerados automaticamente por meio do Assistente para Nova Publicação: você especifica um filtro de linha para uma tabela e os filtros de junção são aplicados a todas as tabelas relacionadas. Para obter mais informações, consulte [Definir e modificar um filtro de junção entre artigos de mesclagem](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Gerar automaticamente um conjunto de filtros de junção entre artigos de mesclagem &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md) e [Definir um artigo](../publish/define-an-article.md).  
  
## <a name="optimizing-join-filter-performance"></a>Aperfeiçoando o desempenho dos filtros de junção  
 O desempenho dos filtros de junção pode ser otimizado seguindo-se estas diretrizes:  
  
-   Limite o número de tabelas na hierarquia de filtro de junção.  
  
     Os filtros de junção podem envolver um número ilimitado de tabelas, mas filtros com um grande número de tabelas podem ter um impacto significativo no desempenho durante o processo de mesclagem. Se você estiver gerando filtros de junção de cinco ou mais tabelas, considere outras soluções: não filtre tabelas pequenas, que não estão sujeitas a alterações ou que sejam basicamente tabelas de pesquisa. Use filtros de junção somente entre tabelas que devem ser particionadas entre assinaturas.  
  
-   Defina a opção **join unique key** como **Verdadeiro** onde apropriado.  
  
     O processo de mesclagem terá otimizações de desempenho especiais disponíveis se a coluna unida no pai for exclusiva. Se a condição de junção estiver baseada em uma coluna exclusiva, defina a opção **join unique key** para o filtro de junção. Para obter informações sobre como definir essa opção, consulte os tópicos de instruções listados na seção anterior.  
  
-   Certifique-se de que as colunas referenciadas nos filtros de junção estejam indexadas.  
  
     Se as colunas referenciadas no filtro estiverem indexadas, a replicação poderá processar os filtros de modo mais eficiente.  
  
-   Não crie filtros de linha que imitem filtros de junção.  
  
     É possível criar filtros de linha que imitem filtros de junção por meio de uma subconsulta em uma cláusula WHERE, como:  
  
    ```  
    WHERE Customer.SalesPersonID IN (SELECT EmployeeID FROM Employee WHERE LoginID = SUSER_SNAME())   
    ```  
  
     É altamente recomendável que toda lógica desse tipo seja expressa em um filtro de junção em vez de em uma subconsulta. Se seu aplicativo requer que um filtro de linha use uma subconsulta, certifique-se de que a subconsulta só referencie dados de pesquisa que não sejam alterados.  
  
## <a name="see-also"></a>Consulte também  
 [Filtrar dados publicados para a replicação de mesclagem](filter-published-data-for-merge-replication.md)   
 [Filtros de linha com parâmetros](parameterized-filters-parameterized-row-filters.md)  
  
  
