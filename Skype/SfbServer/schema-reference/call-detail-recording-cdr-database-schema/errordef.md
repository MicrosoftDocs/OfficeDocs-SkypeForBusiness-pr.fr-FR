---
title: Table ErrorDef dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur qui peut se produire. Chaque enregistrement est un type d’erreur.
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899066"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Table ErrorDef dans Skype pour Business Server 2015
 
La table ErrorDef stocke des informations sur chaque type d’erreur qui peut se produire. Chaque enregistrement est un type d’erreur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Code d’erreur** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce type d’erreur.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Code de réponse SIP standard associé à cette erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID de Diagnostic de Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Étrangère  <br/> |Type de l’appel. Voir la [table CallType dans Skype pour Business Server 2015](calltype.md) pour plus d’informations. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Type de demande ayant échoué.  <br/> Ces données peuvent être converties au format texte à l’aide de la syntaxe suivante :  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Type de contenu de la demande ayant échoué.  <br/> Ces données peuvent être converties au format texte à l’aide de cette syntaxe :  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

