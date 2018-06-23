---
title: Opção de reprodução (ferramenta de administração do Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7bce6a5-d414-488d-a3cd-50c1c62019c4
caps.latest.revision: 24
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e9829a1b3df098be4637921bb9b779635d24376b
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36115140"
---
# <a name="replay-option-distributed-replay-administration-tool"></a>Opção Replay (ferramenta de administração do Distributed Replay)
  O [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ferramenta de administração do Distributed Replay, `DReplay.exe`, é uma ferramenta de linha de comando que você pode usar para se comunicar com o controlador de reprodução distribuída. Este tópico descreve a opção de linha de comando **replay** e a sintaxe correspondente.  
  
 A opção **replay** inicia o estágio de reprodução de eventos, no qual o controlador despacha dados de reprodução aos clientes especificados, inicia a reprodução distribuída e sincroniza os clientes. Opcionalmente, cada cliente que participa da reprodução pode gravar a atividade de reprodução e salvar um arquivo de rastreamento de resultado localmente.  
  
 ![Ícone de link do tópico](../../database-engine/media/topic-link.gif "Ícone de link do tópico") Para obter mais informações sobre as convenções de sintaxe usadas com a sintaxe da ferramenta de administração, confira [Convenções de sintaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
      dreplay replay [-mcontroller] -dcontroller_working_dir [-o]  
    [-starget_server] -wclients [-cconfig_file]  
    [-fstatus_interval]  
```  
  
#### <a name="parameters"></a>Parâmetros  
 **-m** *controller*  
 Especifica o nome do computador do controlador. Você pode usar "`localhost`" ou "`.`" para fazer referência ao computador local.  
  
 Se o parâmetro **-m** não for especificado, será usado o computador local.  
  
 **-d** *controller_working_dir*  
 Especifica o diretório no controlador onde o arquivo intermediário será armazenado. O parâmetro **-d** é obrigatório.  
  
 Os seguintes requisitos são aplicados:  
  
-   O diretório deve residir no controlador.  
  
-   Você deve especificar o caminho completo, iniciando com uma letra da unidade (por exemplo, `c:\WorkingDir`).  
  
-   O caminho não deve terminar com uma barra invertida "`\`".  
  
-   Não há suporte para caminhos UNC.  
  
 **-o**  
 Captura a atividade de reprodução dos clientes e salva-a em um arquivo de rastreamento de resultado no caminho especificado pelo elemento `<ResultDirectory>` no arquivo de configuração do cliente, `DReplayClient.xml`.  
  
 Quando o parâmetro **–o** não é especificado, o arquivo de rastreamento de resultado não é gerado. A saída do console retorna informações resumidas ao término da reprodução, mas nenhuma outra estatística de reprodução está disponível.  
  
 **-s** *target_server*  
 Especifica a instância de destino do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na qual a carga de trabalho distribuída deve ser reproduzida. Você deve especificar esse parâmetro no formato **server_name[\nome da instância]**.  
  
 Você não pode usar "`localhost`" ou "`.`" como o servidor de destino.  
  
 O parâmetro **-s** não será necessário se o elemento `<Server>` for especificado na seção `<ReplayOptions>` do arquivo de configuração de reprodução, `DReplay.exe.replay.config`.  
  
 Se o parâmetro **-s** for usado, o elemento `<Server>` na seção `<ReplayOptions>` do arquivo de configuração de reprodução será ignorado.  
  
 **-w** *clients*  
 Esse parâmetro necessário é uma lista separada por vírgulas (sem espaços) que especifica os nomes de computadores de clientes que devem participar da reprodução distribuída. Endereços IP não são permitidos. Lembre-se de que os clientes já devem estar registrados com o controlador.  
  
> [!NOTE]  
>  Cada cliente efetua o registro com o controlador que é especificado no arquivo de configuração de cliente quando o serviço de cliente é iniciado.  
  
 **-c** *config_file*  
 É o caminho completo do arquivo de configuração de reprodução; usado para especificar o local em que ele é armazenado em um local diferente.  
  
 O parâmetro **-c** não será necessário se você quiser usar os valores padrão do arquivo de configuração de reprodução, `DReplay.exe.replay.config`.  
  
 **-f** *status_interval*  
 Especifica a frequência (em segundos) na qual exibir o status.  
  
 Se **-f** não for especificado, o intervalo padrão será de 30 segundos.  
  
## <a name="examples"></a>Exemplos  
 Neste exemplo, a reprodução distribuída deriva muito de seu comportamento a partir de um arquivo de configuração de reprodução modificado, `DReplay.exe.replay.config`.  
  
-   O parâmetro **-m** especifica que um computador denominado `controller1` atua como o controlador. O nome do computador deve ser especificado quando o serviço de controlador é executado em um computador diferente.  
  
-   O parâmetro **-d** especifica o local do arquivo intermediário no controlador, `c:\WorkingDir`.  
  
-   O parâmetro **-o** especifica que cada cliente especificado captura a atividade de reprodução e salva-a em um arquivo de rastreamento de resultado. Observação: o elemento `<ResultTrace>` no arquivo de configuração pode ser usado para especificar se a contagem de linhas e o conjunto de resultados são registrados.  
  
-   O parâmetro **-w** especifica que os computadores `client1` a `client4` participam como clientes na reprodução distribuída.  
  
-   O parâmetro **-c** é usado para apontar para o arquivo de configuração modificado, `DReplay.exe.replay.config`.  
  
-   O parâmetro **-s** não é necessário porque o elemento `<Server>` é especificado no elemento `<ReplayOptions>` do arquivo de configuração de reprodução, `DReplay.exe.replay.config`.  
  
 O estágio de reprodução de eventos é iniciado com a sintaxe a seguir, quando a ferramenta de administração é executada a partir de um computador diferente do controlador:  
  
```  
dreplay replay -m controller1 -d c:\WorkingDir -o -w client1,client2,client3,client4 -c c:\DReplay.exe.replay.config  
```  
  
 Para especificar um modo de sequenciamento síncrono, o elemento `<SequencingMode>` do arquivo `DReplay.exe.replay.config` é definido igual ao valor `synchronization`. A seção `<ResultTrace>` do arquivo de configuração de reprodução é modificado para especificar que a contagem de linhas seja registrada. Essas alterações são mostradas no seguinte exemplo XML:  
  
```  
<?xml version='1.0'?>  
<Options>  
    <ReplayOptions>  
        <Server>server_name\replay_target_instance</Server>  
        <SequencingMode>synchronization</SequencingMode>  
        <ConnectTimeScale></ConnectTimeScale>  
        <ThinkTimeScale></ThinkTimeScale>  
        <HealthmonInterval>60</HealthmonInterval>  
        <QueryTimeout>3600</QueryTimeout>  
        <ThreadsPerClient></ThreadsPerClient>  
    </ReplayOptions>  
    <OutputOptions>  
        <ResultTrace>  
            <RecordRowCount>Yes</RecordRowCount>  
            <RecordResultSet>No</RecordResultSet>  
        </ResultTrace>  
    </OutputOptions>  
</Options>  
```  
  
 Para especificar um modo de sequenciamento de estresse, o elemento `<SequencingMode>` do arquivo `DReplay.exe.replay.config` é definido igual ao valor `stress`. Os elementos `<ConnectTimeScale>` e `<ThinkTimeScale>` são definidos como o valor `50` (para especificar 50 por cento). Para obter mais informações sobre tempo de conexão e tempo de raciocínio, consulte [Configure Distributed Replay](configure-distributed-replay.md). Essas alterações são mostradas no seguinte exemplo XML:  
  
```  
<?xml version='1.0'?>  
<Options>  
    <ReplayOptions>  
        <Server>server_name\replay_target_instance_name</Server>  
        <SequencingMode>stress</SequencingMode>  
        <ConnectTimeScale>50</ConnectTimeScale>  
        <ThinkTimeScale>50</ThinkTimeScale>  
        <HealthmonInterval>60</HealthmonInterval>  
        <QueryTimeout>3600</QueryTimeout>  
        <ThreadsPerClient></ThreadsPerClient>  
    </ReplayOptions>  
    <OutputOptions>  
        <ResultTrace>  
            <RecordRowCount>Yes</RecordRowCount>  
            <RecordResultSet>No</RecordResultSet>  
        </ResultTrace>  
    </OutputOptions>  
</Options>  
```  
  
## <a name="permissions"></a>Permissões  
 Você deve executar a ferramenta de administração como um usuário interativo, um usuário local ou uma conta de usuário de domínio. Para usar uma conta de usuário local, a ferramenta de administração e o controlador devem estar em execução no mesmo computador.  
  
 Para saber mais, confira [Distributed Replay Security](distributed-replay-security.md).  
  
## <a name="see-also"></a>Consulte também  
 [Reproduzir dados de rastreamento](replay-trace-data.md)   
 [Examinar os resultados da reprodução](review-the-replay-results.md)   
 [SQL Server Distributed Replay](sql-server-distributed-replay.md)   
 [Configurar o Distributed Replay](configure-distributed-replay.md)   
 [Fórum do SQL Server Distributed Replay](http://social.technet.microsoft.com/Forums/sl/sqldru/)   
 [Usando o Distributed Replay para teste de carga do SQL Server – Parte 2](http://blogs.msdn.com/b/mspfe/archive/2012/11/14/using-distributed-replay-to-load-test-your-sql-server-part-2.aspx)   
 [Usando o Distributed Replay para teste de carga do SQL Server – Parte 1](http://blogs.msdn.com/b/mspfe/archive/2012/11/08/using-distributed-replay-to-load-test-your-sql-server-part-1.aspx)  
  
  