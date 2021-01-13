---
title: Liste des tables de conformité du serveur de conversation permanente dans Skype Entreprise Server
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
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité de conversation permanente se compose des tableaux suivants.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813054"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Liste des tables de conformité du serveur de conversation permanente dans Skype Entreprise Server
 
Le schéma de base de données de conformité de conversation permanente se compose des tableaux suivants.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste des tables de serveur de conformité de la conversation permanente

|**Table**|**Description**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contient les événements de conformité qui n’ont pas encore été traités par la carte configurée.  <br/> Ce tableau inclut les événements de conversation permanente, tels que les messages de conversation et les téléchargements de fichiers. (Les événements des participants sont suivis par la table tblComplianceParticipant.)  <br/> (Les serveurs qui ont traité les événements de cette table sont répertoriés dans la table tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contient les serveurs qui ont traité un événement de conformité. Celle-ci est étroitement associée à la table tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contient les participants actifs par service de conversation et par serveur. Il est maintenu en fonction des événements de conformité de jointrie et de partie reçus du service de conversation permanente.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contient les informations d’état de conformité au niveau du pool.  <br/> |
   

