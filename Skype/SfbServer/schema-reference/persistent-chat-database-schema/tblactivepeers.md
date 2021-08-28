---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contient les connexions pair à pair actuelles entre les services de conversation.
ms.openlocfilehash: 21623df3acf8ec8077fa4f2f490f28d2e8482907
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622096"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contient les connexions pair à pair actuelles entre les services de conversation.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, non null  <br/> |ID du serveur qui a publié l’entrée.  <br/> |
|aplPeerID  <br/> |int, non null  <br/> |ID de l’homologue à qui le serveur de publication est connecté.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clé primaire.  <br/> |
|aplServerID  <br/> |Clé étrangère avec recherche dans la table tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Clé étrangère avec recherche dans la table tblServerIdentity.serverID.  <br/> |
   

