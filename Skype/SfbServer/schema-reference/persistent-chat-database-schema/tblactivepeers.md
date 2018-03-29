---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contient les connexions de pair à pair en cours entre les services de conversation.
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contient les connexions de pair à pair en cours entre les services de conversation.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, non null  <br/> |ID du serveur qui a validé l’écriture.  <br/> |
|aplPeerID  <br/> |int, non null  <br/> |ID de l’hôte auquel est connecté le serveur de validation.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clé primaire.  <br/> |
|aplServerID  <br/> |Clé étrangère avec la recherche dans la table de tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Clé étrangère avec la recherche dans la table de tblServerIdentity.serverID.  <br/> |
   

