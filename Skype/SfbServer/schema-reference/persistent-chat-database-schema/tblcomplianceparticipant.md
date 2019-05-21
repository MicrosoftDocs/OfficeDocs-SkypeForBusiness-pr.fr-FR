---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contient les participants actuels par canal et par serveur.
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295460"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant contient les participants actuels par canal et par serveur.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), pas null  <br/> |URI (Uniform Resource Identifier) de canal.  <br/> |
|userId  <br/> |ent, non null  <br/> |ID principal du participant (correspondant à la table tblPrincipal. prinID).  <br/> |
|joinedAt  <br/> |bigint, pas null  <br/> |Date et heure de l’événement de jointure.  <br/> |
|partedAt  <br/> |bigint  <br/> |NULL si le participant reste connecté. Horodatage du canal quittant l’événement s’il n’a pas la valeur null.  <br/> Ces entrées sont finalement supprimées lorsque tous les traducteurs traitent l’événement.  <br/> |
|userUri  <br/> |nvarchar (255), pas null  <br/> |URI de l’utilisateur.  <br/> |
|serverID  <br/> |int  <br/> |Identité du serveur (comme dans la table tblServerIdentity. serverID).  <br/> |
|ID  <br/> |bigint  <br/> |Session du serveur. Il s’agit d’un nombre aléatoire généré chaque fois qu’un service de conversation démarre. Il est utilisé pour différencier les sessions à des fins d’identification de participants orphelins.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Clé primaire.  <br/> |
   

