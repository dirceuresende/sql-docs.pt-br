---
title: Iniciar o SQL Server Management Studio | Microsoft Docs
ms.custom: 
ms.date: 07/11/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: 25ffaea6-0eee-4169-8dd0-1da417c28fc6
caps.latest.revision: 45
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 109b5a18604b2111f3344ba216a6d3d98131d116
ms.openlocfilehash: 2d5147747a0b9bac8e90c77cca24fd3632d42240
ms.contentlocale: pt-br
ms.lasthandoff: 07/12/2017

---
# <a name="lesson-1-1---start-sql-server-management-studio"></a>Lição 1-1 – Iniciar o SQL Server Management Studio
Para iniciar este tutorial, vamos olhar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
## <a name="opening-sql-server-management-studio"></a>Abrindo o SQL Server Management Studio  
  
#### <a name="to-open-sql-server-management-studio"></a>Para abrir o SQL Server Management Studio  
  
1.  O modo de inicialização do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] (SSMS) depende do seu sistema operacional.  
  * Para versões mais recentes do Windows com uma **Página Inicial**, na **Página Inicial**, digite **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]** e o programa será exibido. Clique no programa para abrir o SSMS. Talvez você queira clicar com o botão direito do mouse do programa e fixá-lo na **Página Inicial**.   
  * Para versões mais antigas do Windows, no menu **Iniciar** , aponte para **Todos os Programas**, aponte para [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]e clique em **SQL Server Management Studio**. Como alternativa, na caixa de diálogo **Executar** , digite **SSMS.exe** e clique em **OK**.  
  
    > [!NOTE]  
    >  Caso o SSMS não seja exibido, você pode não ter instalado o SSMS com êxito. Instale o SSMS no [centro de download](https://msdn.microsoft.com/library/mt238290.aspx). O SSMS não é instalado automaticamente com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016. Use a versão mais recente para acessar todos os recursos.  
  
2.  Na próxima etapa, você se conecta ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o componente **Pesquisador de Objetos** do SSMS. Se o painel Pesquisador de Objetos não estiver visível, no menu **Exibir** , clique em **Pesquisador de Objetos**. No menu Pesquisador de Objetos, clique no botão **Conectar** e em **Mecanismo de Banco de Dados**. A caixa de diálogo **Conectar ao Servidor** deverá ser exibida. (Se você já tiver instalado o SSMS, as configurações do usuário poderão estar fazendo com que a caixa de diálogo **Conectar-se ao Servidor** seja exibida automaticamente.)  
  
3.  Na caixa de diálogo **Conectar ao Servidor** , preencha a caixa **Nome do servidor** . Você pode se conectar a um dos três tipos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Cada tipo tem um formato um pouco diferente para a caixa **Nome do servidor** . Escolha um dos seguintes formatos:  
  -  **Uma instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:** quando você instala o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um computador, você pode especificar que a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será uma instância padrão (sem nome) ou nomeada. Se você estiver se conectando a uma instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], insira o nome do computador. Por exemplo, se você estiver executando o SSMS em um computador chamado Contabilidade e estiver se conectando a uma instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  instalada nesse computador, digite **Contabilidade** na caixa **Nome do servidor** .  
  -  **Uma instância nomeada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:** durante a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você pode especificar um nome para a instância; por exemplo, em um computador chamado Contabilidade, você pode especificar uma instância nomeada chamada **Contas a Receber**. Para se conectar a uma instância nomeada, na caixa **Nome do servidor** , digite o nome do computador barra invertida nome da instância; por exemplo **Contabilidade\Contas a Receber**.  
  -  **Um banco de dados SQL do Azure:** o formato do nome do servidor do banco de dados SQL é SQL_Server_name.database.windows.net, por exemplo **mydb2.database.windows.net**. Se você tiver problemas para determinar o nome do servidor, visite o portal do Azure para ajudar a criar uma cadeia de conexão.  
  
4. Na área **Autenticação**, selecione um método de autenticação.  
  - Se você for o administrador do computador e tiver instalado recentemente o SQL Server, experimente a **Autenticação do Windows**.  Isso funciona se você estiver configurado como um usuário de domínio com acesso ao SQL Server. Como a tentativa de login usa as credenciais que você utilizou para se conectar ao Windows, as caixas **Nome de usuário** e **Senha** estão esmaecidas. 
  -  Se você souber o nome e a senha de uma conta de usuário, selecione **Autenticação do SQL Server** e forneça o **Nome de usuário** e a **Senha**.
  - Caso tenha a versão mais recente do SSMS, você terá mais 3 opções, começando por **Autenticação do Active Directory**. Para mais informações sobre essas opções mais avançadas, confira [Autenticação Universal com Banco de Dados SQL e SQL Data Warehouse (suporte do SSMS para MFA)](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-ssms-mfa-authentication).  
  
## <a name="management-studio-components"></a>Componentes do Management Studio  
[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] apresenta informações em janelas dedicadas a tipos específicos de informações. Informações de banco de dados são exibidas no Pesquisador de Objetos e janelas de documentos.  
  
-   Pesquisador de Objetos é uma exibição de árvore de todos os objetos de banco de dados em um servidor. Isso pode incluir os bancos de dados do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. O Pesquisador de Objetos inclui informações de todos os servidores aos quais está conectado. Ao abrir o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], você é solicitado a conectar o Pesquisador de Objetos às configurações utilizadas na última vez. Você pode clicar duas vezes em qualquer componente de Servidores Registrados e conectar-se a ele, mas não é necessário registrar um servidor para fazer a conexão.  
  
-   A janela de documentos é a maior parte do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]. As janelas de documentos podem conter editores de consulta e janelas de navegador. Por padrão, é exibida a página de Resumo, conectada à instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] no computador atual.  
  
## <a name="showing-additional-windows"></a>Exibindo janelas adicionais  
  
#### <a name="to-show-the-registered-servers-window"></a>Para exibir a janela de Servidores Registrados  
  
1.  No menu **Exibir** , clique em **Servidores Registrados**.  
  
    A janela Servidores Registrados é exibida acima ou ao lado do Pesquisador de Objetos. Você pode arrastá-la e encaixá-la em vários locais. Servidores Registrados relaciona servidores gerenciados frequentemente. Você pode adicionar ou remover servidores dessa lista. Os únicos servidores relacionados serão as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no computador em que você estiver executando o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].  
  
2.  Se seu servidor não for exibido em Servidores Registrados, clique com o botão direito do mouse em **Mecanismo de Banco de Dados**, clique em **Tarefas**e em **Atualizar Registro do Servidor Local**. Para adicionar outros SQL Servers ou um Banco de Dados SQL, clique com o botão direito do mouse em um local em Servidores Registrados e clique em **Novo Registro de Servidor**. Preencha a área **Logon** da mesma forma como preencheu a caixa de diálogo **Conectar ao Servidor** .  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
[Conectar com os Servidores Registrados e o Pesquisador de Objetos](../../tools/sql-server-management-studio/lesson-1-2-connect-with-registered-servers-and-object-explorer.md)  

  
