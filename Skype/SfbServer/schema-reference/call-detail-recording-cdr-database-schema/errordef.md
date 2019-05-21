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
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur pouvant se produire. Chaque enregistrement correspond à un type d’erreur.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296279"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Table ErrorDef dans Skype entreprise Server 2015
 
La table ErrorDef stocke des informations sur chaque type d’erreur pouvant se produire. Chaque enregistrement correspond à un type d’erreur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification unique identifiant ce type d’erreur.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Code de réponse SIP standard associé à cette erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID de diagnostic Microsoft.  <br/> |
|**CallTypeId** <br/> |Ent  <br/> |Externes  <br/> |Type de l’appel. Pour plus d’informations, reportez-vous [à la table CallType dans Skype entreprise Server 2015](calltype.md) . <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Type de requête ayant échoué.  <br/> Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**Indiquez** <br/> |varbinary (257)  <br/> | <br/> |Type de contenu de la requête qui a échoué.  <br/> Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

