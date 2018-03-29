---
title: tblComplianceParticipant
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants en cours par canal et par serveur.
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contient les participants en cours par canal et par serveur.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), non null  <br/> |Chaîne identifiant universel (URI).  <br/> |
|ID utilisateur  <br/> |int, non null  <br/> |ID principal du participant (correspondant à la table de tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, non null  <br/> |Horodatage de l’événement joint.  <br/> |
|partedAt  <br/> |bigint  <br/> |Valeur null si le participant est rejoint encore. L’horodatage du canal en laissant des événements si elle est non null.  <br/> Ces entrées sont finalement supprimées lorsque tous les traducteurs de traitent l’événement.  <br/> |
|userUri  <br/> |nvarchar(255), non null  <br/> |URI de l’utilisateur.  <br/> |
|serverID  <br/> |int  <br/> |Identité du serveur (comme dans la table de tblServerIdentity.serverID).  <br/> |
|ID de session  <br/> |bigint  <br/> |Session du serveur. Il s’agit d’un nombre aléatoire généré à chaque démarrage d’un service de conversation. Il est utilisé pour différencier les sessions pour identifier les participants orphelins.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Clé primaire.  <br/> |
   

