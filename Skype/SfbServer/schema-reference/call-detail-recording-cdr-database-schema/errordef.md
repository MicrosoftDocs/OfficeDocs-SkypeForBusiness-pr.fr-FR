---
title: Table ErrorDef dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur pouvant se produire. Chaque enregistrement correspond à un type d’erreur.
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815232"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Table ErrorDef dans Skype entreprise Server 2015
 
La table ErrorDef stocke des informations sur chaque type d’erreur pouvant se produire. Chaque enregistrement correspond à un type d’erreur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification unique identifiant ce type d’erreur.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Code de réponse SIP standard associé à cette erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID de diagnostic Microsoft.  <br/> |
|**CallTypeId** <br/> |Ent  <br/> |Externes  <br/> |Type de l’appel. Pour plus d’informations, reportez-vous [à la table CallType dans Skype entreprise Server 2015](calltype.md) . <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Type de requête ayant échoué.  <br/> Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante :  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**Indiquez** <br/> |varbinary (257)  <br/> | <br/> |Type de contenu de la requête qui a échoué.  <br/> Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante :  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

