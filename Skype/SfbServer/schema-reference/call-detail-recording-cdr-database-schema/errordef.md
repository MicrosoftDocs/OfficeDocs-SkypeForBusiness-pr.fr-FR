---
title: Table ErrorDef dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La table ErrorDef stocke des informations sur chaque type d’erreur qui peut se produire. Chaque enregistrement est un type d’erreur.
ms.openlocfilehash: c725baeeefa750d8feded45483c74ec849b7842a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858191"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Table ErrorDef dans Skype Entreprise Server 2015
 
La table ErrorDef stocke des informations sur chaque type d’erreur qui peut se produire. Chaque enregistrement est un type d’erreur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primaire  <br/> |Numéro d’identification unique identifiant ce type d’erreur.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Code de réponse SIP standard associé à cette erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID de diagnostic Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Étranger  <br/> |Type de l’appel. Pour plus [d’informations, voir la table CallType Skype Entreprise Server 2015.](calltype.md) <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Type de la demande ayant échoué.  <br/> Ces données peuvent être converties au format texte à l’aide de cette syntaxe :  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Type de contenu de la demande ayant échoué.  <br/> Ces données peuvent être converties au format texte à l’aide de cette syntaxe :  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

