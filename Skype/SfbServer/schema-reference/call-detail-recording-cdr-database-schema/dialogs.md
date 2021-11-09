---
title: Table Dialogs dans Skype Entreprise Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La table Dialogs est une table de prise en charge qui stocke les informations sur les DialogIDs pour les sessions d’égal à égal.
ms.openlocfilehash: c59f3a2d84f4ebed243cba3dbe22f465551cbfaf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850677"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Table Dialogs dans Skype Entreprise Server 2015
 
La table Dialogs est une table de prise en charge qui stocke les informations sur les DialogIDs pour les sessions d’égal à égal.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure de la demande de session ; utilisé conjointement avec SessionIDSeq pour identifier de manière unique une session.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro d’ID identifiant la session. Utilisé conjointement avec SessionIDTime pour identifier de manière unique une session.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum de l’ExternalID. Ce champ est utilisé pour augmenter la vitesse des recherches dans la base de données.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID de boîte de dialogue SIP, stocké en tant que fichier binaire. Le format du fichier binaire est :  <br/> dialog;from-tag;to-tag  <br/> Ces données peuvent être converties au format texte à l’aide de cette syntaxe :  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

