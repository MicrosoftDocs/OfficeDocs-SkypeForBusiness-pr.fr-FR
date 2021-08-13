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
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contient les connexions pair à pair actuelles entre les services de conversation.
ms.openlocfilehash: 7ba8bb5730dc1c08a3d0f8aa13d1173192b7cc65134d90c75061ede0db5aa98d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336394"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contient les connexions pair à pair actuelles entre les services de conversation.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, non null  <br/> |ID du serveur qui a publié l’entrée.  <br/> |
|aplPeerID  <br/> |int, non null  <br/> |ID de l’homologue à qui le serveur de publication est connecté.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clé primaire.  <br/> |
|aplServerID  <br/> |Clé étrangère avec recherche dans la table tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Clé étrangère avec recherche dans la table tblServerIdentity.serverID.  <br/> |
   

