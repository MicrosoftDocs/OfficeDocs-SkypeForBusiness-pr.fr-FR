---
title: Table de boîtes de dialogue dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La table de boîtes de dialogue est une table de support qui stocke les informations sur les DialogIDs pour les sessions de peer-to-peer.
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Table de boîtes de dialogue dans Skype pour Business Server 2015
 
La table de boîtes de dialogue est une table de support qui stocke les informations sur les DialogIDs pour les sessions de peer-to-peer.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Heure de la demande de la session ; utilisé en association avec SessionIDSeq pour identifier de manière unique une session.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec SessionIDTime pour identifier de manière unique une session.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Total de contrôle de la ExternalID. Ce champ est utilisé pour augmenter la vitesse des recherches de base de données.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID de boîte de dialogue SIP, stockée sous la forme d’un fichier binaire. Le format de fichier binaire est :  <br/> boîte de dialogue, à partir de balise ; de balise  <br/> Ces données peuvent être converties au format de texte à l’aide de cette syntaxe :  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

