---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants actifs, par canal et par serveur.
ms.openlocfilehash: d28b81d6ce0169999297dbcde65b1d7fbde38780
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854068"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contient les participants actifs, par canal et par serveur.
  
**Colonnes**

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
   

