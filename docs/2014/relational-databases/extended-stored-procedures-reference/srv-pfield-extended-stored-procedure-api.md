---
title: srv_pfield (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- srv_pfield
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfield
ms.assetid: a61e4c1f-e65b-48ea-a7d1-3e1544af389d
caps.latest.revision: 32
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: ee6011adaf4db7dbb3de7d915bb05786f89c0a73
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37262832"
---
# <a name="srvpfield-extended-stored-procedure-api"></a>srv_pfield (API de procedimento armazenado estendido)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Em vez disso, use a Integração CLR.  
  
 Retorna informações sobre uma conexão de banco de dados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
DBCHAR * srv_pfield (  
SRV_PROC *  
srvproc  
,  
int   
field  
,  
int *  
len  
);  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *srvproc*  
 Ponteiro que identifica uma conexão de banco de dados.  
  
 *field*  
 Especifica dados na conexão que será retornada.  
  
|Valor|Retorna|  
|-----------|-------------|  
|SRV_APPLNAME|O nome dó aplicativo fornecido pelo cliente quando estabeleceu a conexão.|  
|SRV_BCPFLAG|Um sinalizador que será TRUE se o cliente estiver se preparando para uma operação de cópia em massa; caso contrário, será FALSE.|  
|SRV_CLIB|O nome da biblioteca que permite ao cliente falar com um servidor.|  
|SRV_CPID|A ID de processo de cliente no computador original de cliente.|  
|SRV_HOST|O nome do computador do cliente fornecido pelo cliente quando estabeleceu a conexão.|  
|SRV_LIBVERS|A versão da biblioteca do cliente.|  
|SRV_LSECURE|Um sinalizador. TRUE se a conexão usava segurança integrada para fazer logon.|  
|SRV_NETWORK_MODULE|O nome da DLL de Biblioteca de Rede usado pela conexão.|  
|SRV_NETWORK_VERSION|A versão da DLL de Biblioteca de Rede usada pela conexão.|  
|SRV_NETWORK_CONNECTION|A cadeia de conexão passada para a DLL de Net-Library usada para a conexão *srvproc* atual.|  
|SRV_PIPEHANDLE|Uma cadeia de caracteres que contém o controle de pipe de um cliente conectado ou NULL se o cliente estiver conectado em uma rede que não usa pipes nomeados. Para usar esse controle como um controle de pipe válido com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, converta essa cadeia de caracteres em um inteiro.|  
|SRV_RMTSERVER|O servidor do qual o processo de cliente fez logon. Se o logon for de um cliente, esse valor será uma cadeia de caracteres vazia.|  
|SRV_ROWSENT|O número de linhas já enviadas por *srvproc* para o conjunto atual de resultados.|  
|SRV_SPID|A ID de thread do servidor do *srvproc*. Para obter procedimentos armazenados estendidos, esse valor será igual à coluna **kpid** de **sys.sysprocesses** e pode mudar ao longo do tempo.|  
|SRV_SPROC_CODEPAGE|Página de código que o servidor usa para interpretar dados multibyte.|  
|SRV_STATUS|O status atual de *srvproc*: em execução ou fechado|  
|SRV_TYPE|O tipo de conexão de *srvproc*. Se o servidor for retornado, *srvproc* será proveniente de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Se o cliente for retornado, *srvproc* será proveniente de um cliente ODBC ou DB-Library.|  
|SRV_USER|O nome do usuário da conexão.|  
|||  
  
 *len*  
 É um ponteiro para uma variável **int** que contém o tamanho do valor de *field* retornado. Se *len* for NULL, o tamanho da cadeia de caracteres não será retornado.  
  
## <a name="returns"></a>Retorna  
 Um ponteiro para uma cadeia de caracteres terminada por caractere nulo que contém o valor atual do campo especificado na estrutura SRV_PROC. Se o campo for vazio, um ponteiro válido para uma cadeia de caracteres vazia será retornado e *len* conterá 0. Se o campo for desconhecido, NULL será retornado e *len* conterá o valor -1.  
  
> [!IMPORTANT]  
>  Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção. Para obter informações sobre análise e teste de segurança, consulte a [ 	Central de Desenvolvedores de Segurança](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  
