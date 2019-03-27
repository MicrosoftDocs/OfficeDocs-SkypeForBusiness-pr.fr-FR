---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants actifs par canal et par serveur.
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881415"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contient les participants actifs par canal et par serveur.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), non null  <br/> |Canal Uniform Resource Identifier (URI).  <br/> |
|nom d’utilisateur  <br/> |int, non null  <br/> |ID principal du participant (correspondant à la table tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, non null  <br/> |Horodatage de l’événement qui se joint.  <br/> |
|partedAt  <br/> |bigint  <br/> |Null si le participant est toujours lié. La date et l’heure du canal en laissant événement si non null.  <br/> Ces entrées sont finissent par être supprimées lorsque tous les traducteurs traitent l’événement.  <br/> |
|userUri  <br/> |nvarchar (255), non null  <br/> |URI de l’utilisateur.  <br/> |
|serverID  <br/> |int  <br/> |Identité du serveur (comme dans tblServerIdentity.serverID table).  <br/> |
|ID de session  <br/> |bigint  <br/> |Session de serveur. Il s’agit d’un nombre aléatoire généré chaque fois qu’un service de conversation démarre. Il est utilisé pour différencier les sessions en vue d’identifier les participants orphelins.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Clé primaire.  <br/> |
   

