---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 7ef1121c16bb7d99c9b2624e5afaa90fc3a388ba
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394816"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contient les participants actifs, par canal et par serveur.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
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
   

