---
title: "Instanciação de evento do ADO: Visual Basic | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: dce0a2a3-326f-4aaf-a822-6c5549833afa
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 56510bc99d0a6a7c20d18b93b22a60decdfcc2e2
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="ado-event-instantiation-visual-basic"></a>Instanciação de evento do ADO: Visual Basic
Para manipular eventos de ADO no Microsoft® Visual Basic®, você deve declarar uma variável de nível de módulo usando o **WithEvents** palavra-chave. A variável pode ser declarada apenas como parte de um módulo de classe e deve ser declarada no nível de módulo. Isso não é tão restritivo quanto parece, no entanto, como Visual Basic **formulário** objetos também são classes. É a maneira mais simples para tratar eventos de ADO para declarar uma variável usando **WithEvents**. A exemplo a seguir trata o **ConnectComplete** evento para um **Conexão** objeto:  
  
```  
' BeginEventExampleVB02  
Dim WithEvents connEvent As Connection  
Attribute connEvent.VB_VarHelpID = -1  
  
Private Sub Form_Load()  
Dim strConn As String  
  
   ' Create a new object with event  
   ' handling enabled.  
   strConn = "Provider=sqloledb;" & _  
      "Data Source=MyServer;" & _  
      "Initial Catalog=Northwind;" & _  
      "Integrated Security=SSPI;"  
   Set connEvent = New ADODB.Connection  
   connEvent.Open strConn  
End Sub  
  
Private Sub connEvent_ConnectComplete(ByVal pError As ADODB.Error, _  
    adStatus As ADODB.EventStatusEnum, _  
    ByVal pConnection As ADODB.Connection)  
Dim strMsg As String  
  
   If adStatus = adStatusErrorsOccurred Then  
      Select Case pError.Number  
         Case adErrOperationCancelled  
            ' The operation was cancelled in the  
            ' Will event. Notify the user and exit.  
            strMsg = "I'm sorry you can't connect right now." & vbCrLf  
            strMsg = strMsg & "Click OK to exit."  
            Unload Me  
         Case Else  
            strMsg = "Error " & Format(pError.Number) & vbCrLf  
            strMsg = strMsg & pError.Description  
            strMsg = strMsg & "Click OK to exit."  
            Unload Me  
      End Select  
   End If  
   frmWait.btnOK.Enabled = True  
End Sub  
' EndEventExampleVB02  
```  
  
 O **Conexão** objeto for declarado no **formulário** nível usando o **WithEvents** palavra-chave para habilitar a manipulação de eventos. O manipulador de eventos Form_Load realmente cria o objeto atribuindo um novo **Conexão** do objeto para *connEvent* e, em seguida, abre a conexão. Logicamente, um aplicativo real faria mais processamento no manipulador de eventos Form_Load que é mostrada aqui.