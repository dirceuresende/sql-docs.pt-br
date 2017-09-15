---
title: SERVERPROPERTY (Transact-SQL) | Microsoft Docs
ms.custom:
- SQL2016_New_Updated
ms.date: 03/02/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SERVERPROPERTY_TSQL
- SERVERPROPERTY
dev_langs:
- TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- SERVERPROPERTY function
- server instance property information [SQL Server]
- IsHadrEnabled server property
- instances of SQL Server, property information
- server properties [SQL Server]
ms.assetid: 11e166fa-3dd2-42d8-ac4b-04f18c612c4a
caps.latest.revision: 128
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 7060a8aaf668a69184503fa0995dd4f37085d5f1
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="serverproperty-transact-sql"></a>SERVERPROPERTY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retorna informações de propriedade sobre a instância de servidor.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
SERVERPROPERTY ( 'propertyname' )  
```  
  
## <a name="arguments"></a>Argumentos  
 *PropertyName*  
 É uma expressão que contém as informações de propriedade que serão retornadas para o servidor. *PropertyName* pode ser um dos valores a seguir.  
  
|Propriedade|Valores retornados|  
|--------------|---------------------|  
|BuildClrVersion|Versão do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR) que foi usada durante a criação da instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|Agrupamento|Nome do agrupamento padrão para o servidor.<br /><br /> NULL = Entrada inválida ou um erro.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|CollationID|ID do agrupamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].<br /><br /> Tipo de dados base: **int**|  
|ComparisonStyle|Estilo de comparação do agrupamento do Windows.<br /><br /> Tipo de dados base: **int**|  
|ComputerNamePhysicalNetBIOS|O nome NetBIOS do computador local no qual a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está em execução no momento.<br /><br /> Para uma instância clusterizada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um cluster de failover, este valor muda à medida que a instância de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] efetua failover para os outros nós no cluster de failover.<br /><br /> Em uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], esse valor permanece constante e retorna o mesmo valor da propriedade MachineName.<br /><br /> **Observação:** se a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está em um failover cluster e você deseja obter o nome da instância de cluster de failover, use a propriedade MachineName.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|Edição|Edição instalada do produto da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Use o valor dessa propriedade para determinar os recursos e os limites, como [Compute Capacity Limits by Edition of SQL Server](../../sql-server/compute-capacity-limits-by-edition-of-sql-server.md). Versões de 64 bits do [!INCLUDE[ssDE](../../includes/ssde-md.md)] anexam (64 bits) à versão.<br /><br /> Retorna:<br /><br /> 'Enterprise Edition'<br /><br /> ‘Enterprise Edition: licenciamento baseado em núcleo’<br /><br /> 'Enterprise Evaluation Edition'<br /><br /> ‘Business Intelligence Edition’<br /><br /> 'Developer Edition'<br /><br /> 'Express Edition'<br /><br /> 'Express Edition com Advanced Services'<br /><br /> 'Standard Edition'<br /><br /> 'Web Edition'<br /><br /> 'SQL Azure' indica [!INCLUDE[ssSDS](../../includes/sssds-md.md)] ou[!INCLUDE[ssDW](../../includes/ssdw-md.md)]<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|EditionID|EditionID representa a edição instalada do produto da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Use o valor dessa propriedade para determinar os recursos e limites, como [Compute Capacity Limits by Edition of SQL Server](../../sql-server/compute-capacity-limits-by-edition-of-sql-server.md).<br /><br /> 1804890536 = Enterprise<br /><br /> 1872460670 = Enterprise Edition: licenciamento baseado em núcleo<br /><br /> 610778273= Enterprise Evaluation<br /><br /> 284895786 = Business Intelligence<br /><br /> -2117995310 = Developer<br /><br /> -1592396055 = Express<br /><br /> -133711905= Express com Advanced Services<br /><br /> -1534726760 = padrão<br /><br /> 1293598313 = Web<br /><br /> 1674378470 = banco de dados SQL ou SQL Data Warehouse<br /><br /> Tipo de dados base: **bigint**|  
|EngineEdition|Edição do [!INCLUDE[ssDE](../../includes/ssde-md.md)] da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalada no servidor.<br /><br /> 1 = Personal ou Desktop Engine (Não disponível no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e em versões posteriores.)<br /><br /> 2 = Standard (Retornada para Standard, Web e Business Intelligence.)<br /><br /> 3 = Enterprise (This is returned for Evaluation, Developer e Enterprise editions.)<br /><br /> 4 = Express (Retornada para Express, Express with Tools e Express com Advanced Services)<br /><br /> 5 = [!INCLUDE[ssSDS](../../includes/sssds-md.md)]<br /><br /> 6 - [!INCLUDE[ssDW](../../includes/ssdw-md.md)]<br /><br /> Tipo de dados base: **int**|  
|HadrManagerStatus|**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Indica se o gerenciador do [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] foi iniciado.<br /><br /> 0 = não iniciado, comunicação pendente.<br /><br /> 1 = iniciado e em execução.<br /><br /> 2 = não iniciado e com falha.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.|  
|InstanceDefaultDataPath|**Aplica-se a**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] até a versão atual em atualizações a partir do final de 2015.<br /><br /> Nome do caminho padrão para os arquivos de dados de instância.|  
|InstanceDefaultLogPath|**Aplica-se a**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] até a versão atual em atualizações a partir do final de 2015.<br /><br /> Nome do caminho padrão para os arquivos de log da instância.|  
|InstanceName|Nome da instância à qual o usuário está conectado.<br /><br /> Retornará NULL se o nome de instância for a instância padrão, se a entrada não for válida, ou erro.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|IsAdvancedAnalyticsInstalled|Retornará 1 se o recurso Advanced Analytics foi instalado durante a instalação; 0 se Advanced Analytics não foi instalado.|  
|IsClustered|A instância de servidor é configurada em um cluster de failover.<br /><br /> 1 = Clusterizado.<br /><br /> 0 = Não clusterizado.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **int**|  
|IsFullTextInstalled|Os componentes de indexação de texto completo e semântica são instalados na instância atual do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].<br /><br /> 1 = Componentes de indexação de texto completo e semântica são instalados.<br /><br /> 0 = Componentes de indexação de texto completo e semântica não são instalados.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **int**|  
|IsHadrEnabled|**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] é habilitado nessa instância do servidor.<br /><br /> 0 = O [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] está desabilitado.<br /><br /> 1 = O recurso [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] está habilitado.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **int**<br /><br /> Para que réplicas de disponibilidade sejam criadas e executadas em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] deve estar habilitado na instância do servidor. Para obter mais informações, consulte [habilitar e desabilitar grupos de disponibilidade do AlwaysOn (SQL Server)](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md).<br /><br /> **Observação:** a propriedade IsHadrEnabled pertence somente ao [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]. Outros recursos de alta disponibilidade ou de recuperação de desastre, como espelhamento de banco de dados ou envio de logs, não são afetados por essa propriedade de servidor.|  
|IsIntegratedSecurityOnly|O servidor está em modo de segurança integrado.<br /><br /> 1 = Segurança integrada (Autenticação do Windows)<br /><br /> 0 = Segurança não integrada. (Autenticação do Windows e Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **int**|  
|IsLocalDB|**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> O servidor é uma instância do [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] LocalDB.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.|  
|IsPolybaseInstalled|**Aplica-se a**: [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Retorna se a instância do servidor tem o recurso PolyBase instalado.<br /><br /> 0 = PolyBase não está instalado.<br /><br /> 1 = PolyBase está instalado.<br /><br /> Tipo de dados base: **int**|  
|IsSingleUser|O servidor está em modo de usuário único.<br /><br /> 1 = Usuário único.<br /><br /> 0 = Usuário não único<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **int**|  
|IsXTPSupported|**Aplica-se a**: SQL Server ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] por meio de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]), [!INCLUDE[ssSDS](../../includes/sssds-md.md)].<br /><br /> Servidor dá suporte a OLTP na memória.<br /><br /> 1= Servidor dá suporte a OLTP na memória.<br /><br /> 0 = O servidor não oferece suporte a OLTP na memória.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **int**|  
|LCID|Identificador de localidade do Windows (LCID) do agrupamento.<br /><br /> Tipo de dados base: **int**|  
|LicenseType|Não utilizado. As informações de licença não são preservadas ou mantidas pelo produto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Sempre retorna DISABLED.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|MachineName|Nome do computador do Windows no qual a instância de servidor está sendo executada.<br /><br /> Para uma instância clusterizada, uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em execução em um servidor virtual no Microsoft Cluster Service, retorna o nome do servidor virtual.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|NumLicenses|Não utilizado. As informações de licença não são preservadas ou mantidas pelo produto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Sempre retorna NULL.<br /><br /> Tipo de dados base: **int**|  
|ProcessID|ID do processo do serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. ProcessID é útil para identificar qual Sqlservr.exe pertence a esta instância.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.<br /><br /> Tipo de dados base: **int**|  
|ProductBuild|**Aplica-se a**: [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] a partir de outubro de 2015.<br /><br /> O número de compilação.|  
|ProductBuildType|**Aplica-se a**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] até a versão atual em atualizações a partir do final de 2015.<br /><br /> Tipo de compilação a compilação atual.<br /><br /> Retorna uma destas opções:<br /><br /> OD = versão sob demanda de um cliente específico.<br /><br /> GDR = versão de distribuição geral lançada pelo windows update.<br /><br /> NULL<br />= Não aplicável.|  
|ProductLevel|Nível da versão da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].<br /><br /> Retorna uma destas opções:<br /><br /> 'RTM' = Versão original<br /><br /> ' SP*n*' = versão Service pack<br /><br /> ' CTP*n*', = versão Community Technology Preview<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|ProductMajorVersion|**Aplica-se a**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] até a versão atual em atualizações a partir do final de 2015.<br /><br /> A versão principal.|  
|ProductMinorVersion|**Aplica-se a**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] até a versão atual em atualizações a partir do final de 2015.<br /><br /> A versão secundária.|  
|ProductUpdateLevel|**Aplica-se a**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] até a versão atual em atualizações a partir do final de 2015.<br /><br /> Atualize o nível da compilação atual. CU indica uma atualização cumulativa.<br /><br /> Retorna uma destas opções:<br /><br /> CU *n*  = atualização cumulativa<br /><br /> NULL<br />= Não aplicável.|  
|ProductUpdateReference|**Aplica-se a**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] até a versão atual em atualizações a partir do final de 2015.<br /><br /> Artigo KB para essa versão.|  
|ProductVersion|Versão da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], na forma de '*Revision*'.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|ResourceLastUpdateDateTime|Retorna a data e a hora da última atualização do banco de dados do Recurso.<br /><br /> Tipo de dados base: **datetime**|  
|ResourceVersion|Retorna o banco de dados do Recurso da versão.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|ServerName|As informações do servidor e da instância do Windows associadas a uma instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].<br /><br /> NULL = Entrada inválida ou um erro.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|SqlCharSet|A ID do conjunto de caracteres SQL da ID do agrupamento.<br /><br /> Tipo de dados base: **tinyint**|  
|SqlCharSetName|O nome do conjunto de caracteres SQL do agrupamento.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|SqlSortOrder|O ID da ordem de classificação SQL do agrupamento<br /><br /> Tipo de dados base: **tinyint**|  
|SqlSortOrderName|O nome da ordem de classificação SQL do agrupamento.<br /><br /> Tipo de dados base: **nvarchar (128)**|  
|FilestreamShareName|O nome do compartilhamento usado por FILESTREAM.<br /><br /> NULL = Entrada inválida, um erro ou não aplicável.|  
|FilestreamConfiguredLevel|O nível de acesso ao FILESTREAM configurado. Para obter mais informações, consulte [nível de acesso de filestream](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).|  
|FilestreamEffectiveLevel|O nível de acesso ao FILESTREAM efetivo. Esse valor poderá ser diferente de FilestreamConfiguredLevel se o nível foi alterado e se a reinicialização de uma instância ou de um computador estiver pendente. Para obter mais informações, consulte [nível de acesso de filestream](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).|  
  
## <a name="return-types"></a>Tipos de retorno  
 **sql_variant**  
  
## <a name="remarks"></a>Comentários  
  
### <a name="servername-property"></a>Propriedade ServerName  
 O `ServerName` propriedade o `SERVERPROPERTY` função e [@@SERVERNAME ](../../t-sql/functions/servername-transact-sql.md) retorna informações semelhantes. A propriedade `ServerName` fornece o servidor do Windows e o nome da instância que, juntos, compõem a instância exclusiva do servidor. [@@SERVERNAME ](../../t-sql/functions/servername-transact-sql.md) fornece o nome do servidor local configurado atualmente.  
  
 O `ServerName` propriedade e [@@SERVERNAME ](../../t-sql/functions/servername-transact-sql.md) retornam as mesmas informações se o nome do servidor padrão no momento da instalação não tiver sido alterado. O nome de servidor local pode ser configurado executando o seguinte:  
  
```  
EXEC sp_dropserver 'current_server_name';  
GO  
EXEC sp_addserver 'new_server_name', 'local';  
GO  
```  
  
 Se o nome do servidor local foi alterado de nome de servidor padrão no momento da instalação [@@SERVERNAME ](../../t-sql/functions/servername-transact-sql.md) retorna o novo nome.  
  
### <a name="version-properties"></a>Propriedades da versão  
 O `SERVERPROPERTY` função retorna propriedades individuais relacionadas às informações de versão, enquanto o [@@VERSION ](../../t-sql/functions/version-transact-sql-configuration-functions.md) função combina a saída em uma cadeia de caracteres. Se seu aplicativo exigir cadeias de caracteres de propriedade individuais, você pode usar o `SERVERPROPERTY` função para retorná-los em vez de analisar o [@@VERSION ](../../t-sql/functions/version-transact-sql-configuration-functions.md) resultados.  

## <a name="permissions"></a>Permissões

Todos os usuários podem consultar as propriedades do servidor. 
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir usa o `SERVERPROPERTY` funcionar em um `SELECT` instrução para retornar informações sobre a instância atual do [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)].   
  
```  
SELECT  
  SERVERPROPERTY('MachineName') AS ComputerName,
  SERVERPROPERTY('ServerName') AS InstanceName,  
  SERVERPROPERTY('Edition') AS Edition,
  SERVERPROPERTY('ProductVersion') AS ProductVersion,  
  SERVERPROPERTY('ProductLevel') AS ProductLevel;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Edições e componentes do SQL Server 2016](../../sql-server/editions-and-components-of-sql-server-2016.md)  
  
  
