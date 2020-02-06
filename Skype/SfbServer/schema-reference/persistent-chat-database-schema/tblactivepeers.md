---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contient les connexions d’égal à égal actuelles entre les services de discussion.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814712"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contient les connexions d’égal à égal actuelles entre les services de discussion.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|aplServerID  <br/> |ent, non null  <br/> |ID du serveur qui a publié l’entrée.  <br/> |
|aplPeerID  <br/> |ent, non null  <br/> |ID de l’homologue auquel est connecté le serveur de publication.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Clé primaire.  <br/> |
|aplServerID  <br/> |Clé étrangère avec recherche dans la table tblServerIdentity. serverID.  <br/> |
|aplPeerID  <br/> |Clé étrangère avec recherche dans la table tblServerIdentity. serverID.  <br/> |
   

