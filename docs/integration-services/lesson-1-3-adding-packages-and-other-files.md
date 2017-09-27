---
title: 'Etapa 3: Adicionando pacotes e outros arquivos | Microsoft Docs'
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: a7e6ec9c-d31d-4613-9525-8947a7b358f7
caps.latest.revision: 24
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: f8cf4eedc8930492e28f41cee67f0c25a382bacd
ms.contentlocale: pt-br
ms.lasthandoff: 09/26/2017

---
# <a name="lesson-1-3---adding-packages-and-other-files"></a>Lição 1-3 - adicionar pacotes e outros arquivos
Nesta tarefa, você adicionará pacotes existentes, arquivos auxiliares, que oferecem suporte a pacotes individuais, e um Leiame para o projeto do Tutorial de Implantação criado na tarefa anterior. Por exemplo, você adicionará um arquivo de dados XML que contém os dados para um pacote e um arquivo de texto que fornece as informações do Leiame sobre todos os pacotes do projeto.  
  
Quando você implanta pacotes em um ambiente de teste ou de produção, normalmente não inclui os arquivos de dados na implantação, em vez disso, usa as configurações para atualizar os caminhos das fontes de dados para acessar testes ou versões de produção dos arquivos de dados ou de bancos de dados. Para fins instrutivos, esse tutorial inclui arquivos de dados na implantação do pacote.  
  
Os pacotes e os dados de exemplo que os pacotes usam são instalados quando você instala os exemplos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] . Você adicionará os seguintes pacotes ao projeto do Tutorial de Implantação:  
  
-   **DataTransfer.** Um pacote básico que extrai dados de um arquivo simples, avalia os valores da coluna para manter as linhas condicionalmente no conjunto de dados e carrega os dados em uma tabela no banco de dados AdventureWorks.  
  
-   **LoadXMLData.** Um pacote de transferência de dados que extrai dados de um arquivo de dados XML, avalia e agrega valores da coluna e carrega dados em uma tabela no banco de dados AdventureWorks.  
  
Para oferecer suporte à implantação desses pacotes, você adicionará os arquivos auxiliares a seguir no projeto do Tutorial de Implantação.  
  
|Pacote|Arquivo|  
|-----------|--------|  
|DataTransfer|NewCustomers.txt|  
|LoadXMLData|orders.xml e orders.xsd|  
  
Você também adicionará um Leiame, que é um arquivo de texto que fornece informações sobre o projeto do Tutorial de Implantação.  
  
Os caminhos usados nos procedimentos a seguir assumem que os exemplos do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] foram instalados no local padrão, [!INCLUDE[ssSampPathIS](../includes/sssamppathis-md.md)]. Se você tiver instalado os exemplos em um local diferente, deverá usar esse local nos procedimentos.  
  
Na próxima tarefa, você adicionará configurações aos pacotes DataTransfer e LoadXMLData. Todas as configurações são armazenadas em arquivos XML e você usará uma variável de ambiente do sistema para especificar o local dos arquivos. Após criar os arquivos de configuração, você os adicionará ao projeto.  
  
### <a name="to-add-packages-to-the-deployment-tutorial-project"></a>Para adicionar pacotes ao projeto do Tutorial de Implantação  
  
1.  Se o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ainda não estiver aberto, clique em **Iniciar**, aponte para **Todos os Programas**, aponte para **Microsoft SQL Server**e clique em **SQL Server Data Tools**.  
  
2.  No menu **Arquivo** , clique em **Abrir**, em **Projeto/Solução**, clique na pasta **Tutorial de Implantação** , clique em **Abrir**e clique duas vezes em **Deployment Tutorial.sln**.  
  
3.  No Gerenciador de Soluções, clique com o botão direito do mouse no Tutorial de Implantação, clique em **Adicionar**e em **Pacote Existente**.  
  
4.  Na caixa de diálogo **Adicionar Cópia do Pacote Existente** , em **Local do pacote**, selecione **Sistema de Arquivos**.  
  
5.  Clique no botão Procurar **(…)** , vá para C:\Program Files\Microsoft SQL Server\100\Samples\Integration ServicesTutorial\Deploying Packages\Completed Packages, selecione **DataTransfer.dtsx**e clique em **Abrir**.  
  
6.  Clique em **OK**.  
  
7.  Repita as etapas de 3 a 6 e, desta vez, adicione LoadXMLData.dtsx, localizado em C:\Arquivos de Programas\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deploying Packages\Completed Packages.  
  
### <a name="to-add-ancillary-files-to-the-deployment-tutorial-project"></a>Para adicionar arquivos auxiliares ao projeto do Tutorial de Implantação  
  
1.  No Gerenciador de Soluções, clique com o botão direito do mouse no Tutorial de Implantação, clique em **Adicionar**e em **Item Existente**.  
  
2.  Na caixa de diálogo **Adicionar Item Existente – Tutorial de Implantação** , vá para C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deployment Packages\Sample Data, selecione orders.xml, orders.xsd e NewCustomers.txt e clique em **Adicionar**.  
  
3.  Na caixa de diálogo **Adicionar Item Existente – Tutorial de Implantação** , vá para C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services\Tutorial\Deployment Packages\\, selecione Readme.txt e clique em **Adicionar**.  
  
4.  No menu Arquivo, clique em **Salvar Tudo**.  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
[Etapa 4: Adicionando configurações de pacote](../integration-services/lesson-1-4-adding-package-configurations.md)  
  
  
  
