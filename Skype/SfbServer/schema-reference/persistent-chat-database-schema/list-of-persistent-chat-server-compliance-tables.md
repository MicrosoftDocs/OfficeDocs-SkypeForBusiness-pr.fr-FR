---
title: Liste des tables de conformité Persistent Chat Server dans Skype pour Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité conversation permanente comprend les tables suivantes.
ms.openlocfilehash: 18c35cc71da43dcf25bb477e81a2471b483ee86d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874314"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Liste des tables de conformité Persistent Chat Server dans Skype pour Business Server
 
Le schéma de base de données de conformité conversation permanente comprend les tables suivantes.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste des Tables de conformité de serveur de conversation permanente

|**Table**|**Description**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contient les événements de conformité qui n’ont pas encore été traitées par la carte configurée.  <br/> Ce tableau inclut les événements liés à la conversation permanente, telles que les messages de conversation et les téléchargements de fichiers. (Participant événements suivis par le tableau tblComplianceParticipant.)  <br/> (Les serveurs qui ont traité les événements de cette table sont répertoriés dans la table tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contient les serveurs qui ont traité un événement de conformité. Ce tableau est étroitement associé à la table tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contient les participants actifs par le service de conversation et par serveur. Il est conservé en fonction des événements de conformité join et composant reçus à partir du service de conversation permanente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contient des informations d’état de conformité au niveau du pool.  <br/> |
   

