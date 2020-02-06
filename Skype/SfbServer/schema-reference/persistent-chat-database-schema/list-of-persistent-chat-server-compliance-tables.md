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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité des conversations permanentes se compose des tables suivantes.
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814762"
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
   

