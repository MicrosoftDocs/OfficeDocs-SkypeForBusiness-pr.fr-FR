---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants actifs, par canal et par serveur.
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809744"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contient les participants actifs, par canal et par serveur.
  
**Columns**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), non null  <br/> |URI (Uniform Resource Identifier) du canal.  <br/> |
|userId  <br/> |int, non null  <br/> |ID Principal du participant (correspondant à la table tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, non null  <br/> |Horodatage de l’événement qui se joint.  <br/> |
|partedAt  <br/> |bigint  <br/> |Null si le participant est encore joint. Horodatage de l’événement qui quitte le canal s’il n’est pas null.  <br/> Ces entrées finissent par être supprimées lorsque tous les traducteurs traitent l’événement.  <br/> |
|userUri  <br/> |nvarchar (255), non null  <br/> |URI de l’utilisateur.  <br/> |
|serverID  <br/> |int  <br/> |Identité du serveur (comme dans tblServerIdentity.serverID table).  <br/> |
|sessionId  <br/> |bigint  <br/> |Session du serveur. Il s’agit d’un nombre aléatoire généré chaque fois que le service de conversation démarre. Il sert à différencier les sessions dans le but d’identifier les participants orphelins.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Clé primaire.  <br/> |
   

