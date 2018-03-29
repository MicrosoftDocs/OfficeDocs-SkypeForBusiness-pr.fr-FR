---
title: Table ErrorDef dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur qui peut-être se produire. Chaque fiche correspond à un type d’erreur.
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Table ErrorDef dans Skype pour Business Server 2015
 
La table ErrorDef stocke des informations sur chaque type d’erreur qui peut-être se produire. Chaque fiche correspond à un type d’erreur.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Code d’erreur** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification unique qui identifie ce type d’erreur.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Code de réponse SIP standard associé à cette erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID de Diagnostic de Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Étrangère  <br/> |Type de l’appel. Consultez le [tableau CallType dans Skype pour Business Server 2015](calltype.md) pour plus d’informations. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Type de demande qui a échoué.  <br/> Ces données peuvent être converties au format de texte à l’aide de cette syntaxe :  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Type de contenu de la demande qui a échoué.  <br/> Ces données peuvent être converties au format de texte à l’aide de cette syntaxt :  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

