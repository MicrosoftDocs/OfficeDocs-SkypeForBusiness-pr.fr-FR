---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: d2d28c70cbb1bc35acdeca4739a667a5e991e52f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756304"
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
   

