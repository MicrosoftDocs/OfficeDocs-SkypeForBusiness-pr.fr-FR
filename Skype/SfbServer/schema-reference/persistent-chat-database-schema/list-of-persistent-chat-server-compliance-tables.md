---
title: Liste des tables de conformité serveur Chat permanent dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité des conversations permanentes se compose des tables suivantes.
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295656"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Liste des tables de conformité serveur Chat permanent dans Skype entreprise Server
 
Le schéma de base de données de conformité des conversations permanentes se compose des tables suivantes.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste des tables de compatibilité de serveur Chat permanent

|**Table**|**Description**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contient les événements de conformité qui n’ont pas encore été traités par l’adaptateur configuré.  <br/> Le tableau suivant contient des événements liés à des discussions permanentes, tels que des messages de discussion et des téléchargements de fichiers. (Les événements de participants sont suivis par la table tblComplianceParticipant.)  <br/> (Les serveurs qui ont géré les événements dans ce tableau apparaissent dans la table tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contient les serveurs qui ont traité un événement de conformité. Ce tableau est étroitement couplé à la table tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contient les participants actuels par service de conversation et par serveur. Elle est conservée en fonction des événements de jointure et de conformité de partie reçus du service de chat permanent.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contient des informations sur l’état de conformité au pool.  <br/> |
   

