---
title: Conectar-se a um banco de dados do SQL do Azure do Windows usando o SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.reviewer: ''
ms.suite: sql
ms.prod: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0dc20bb6-b142-4259-b87b-427d2ba798af
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 96f08121dfcc02fff43c6842b6c319291192c354
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43071990"
---
# <a name="connecting-to-a-windows-azure-sql-database-using-sql-server-native-client"></a>Conectando a um banco de dados SQL do Windows Azure usando o SQL Server Native Client
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  Para obter um exemplo que mostra como se conectar a um [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] usando [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, consulte [desenvolvimento: tópicos de instruções (Windows Azure SQL Database)](http://msdn.microsoft.com/library/ee621787.aspx).  
  
## <a name="known-issues-when-connecting-to-a-sql-database"></a>Problemas conhecidos ao conectar a um banco de dados SQL  
 Estes são problemas conhecidos ao conectar a um [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] usando o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:  
  
-   Uma conexão feita com **SQLBrowseConnect** pode ser rejeitada se **SQLBrowseConnect** for usado em fases.  Por exemplo, se o nome do driver for enviado na primeira chamada, o servidor e as credenciais (usuário e senha) serão enviados na segunda chamada, estabelecendo a conexão, e um nome de banco de dados e um idioma na terceira chamada.  A terceira chamada levará o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client a emitir uma instrução USE para alterar bancos de dados. Entretanto, a instrução USE não tem suporte no [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], gerando o seguinte erro:  
  
    ```  
    [Microsoft][SQL Server Native Client 11.0][SQL Server]USE statement is not supported to switch between databases. Use a new connection to connect to a different Database.  
    ```  
  
## <a name="see-also"></a>Consulte também  
 [Criando aplicativos com o SQL Server Native Client](../../../relational-databases/native-client/applications/building-applications-with-sql-server-native-client.md)  
  
  
