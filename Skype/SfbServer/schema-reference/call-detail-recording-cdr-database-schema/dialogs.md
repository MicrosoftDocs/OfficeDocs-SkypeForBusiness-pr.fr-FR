---
title: Boîtes de dialogue tableau Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La table Dialogs est une table de prise en charge qui stocke les informations sur le Dialogid pour les sessions d’égal à égal.
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889627"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Boîtes de dialogue tableau Skype pour Business Server 2015
 
La table Dialogs est une table de prise en charge qui stocke les informations sur le Dialogid pour les sessions d’égal à égal.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Heure de la demande de session ; utilisé en conjonction avec SessionIDSeq pour identifier de manière unique une session.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec SessionIDTime pour identifier de manière unique une session.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Somme de contrôle de la ExternalID. Ce champ est utilisé pour augmenter la vitesse des recherches de base de données.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID de boîte de dialogue SIP, stockée sous forme d’un fichier binaire. Le format de fichier binaire est :  <br/> boîte de dialogue de balise ; pour une balise  <br/> Ces données peuvent être converties au format texte à l’aide de la syntaxe suivante :  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

