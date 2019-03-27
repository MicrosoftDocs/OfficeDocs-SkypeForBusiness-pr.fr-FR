---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Activepeers contient les connexions d’égal à égal actuelles entre les services de conversation.
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884166"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
Activepeers contient les connexions d’égal à égal actuelles entre les services de conversation.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, non null  <br/> |ID du serveur ayant publié l’entrée.  <br/> |
|aplPeerID  <br/> |int, non null  <br/> |ID de l’homologue auquel est connecté le serveur de publication.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clé primaire.  <br/> |
|aplServerID  <br/> |Clé étrangère avec recherche dans la table tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Clé étrangère avec recherche dans la table tblServerIdentity.serverID.  <br/> |
   

