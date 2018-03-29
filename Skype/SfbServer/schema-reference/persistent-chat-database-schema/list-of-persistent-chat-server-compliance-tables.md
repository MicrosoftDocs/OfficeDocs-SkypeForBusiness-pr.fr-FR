---
title: Liste des tableaux de conformité permanente Chat Server dans Skype pour Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Le schéma de base de données de conformité Chat persistant est constitué par les tableaux suivants.
ms.openlocfilehash: 801e8d5457a26ef968f700df16a68d36560548c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Liste des tableaux de conformité permanente Chat Server dans Skype pour Business Server
 
Le schéma de base de données de conformité Chat persistant est constitué par les tableaux suivants.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste des Tables de la conformité permanente de Chat Server

|**Table**|**Description**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Contient les événements de conformité qui n’ont pas encore été traitées par l’adaptateur configuré.  <br/> Ce tableau inclut les événements liés à Chat persistants, tels que des messages de conversation et les téléchargements de fichiers. (Les événements participant sont suivis par la table de tblComplianceParticipant).  <br/> (Les serveurs de traitement des événements dans cette table sont répertoriés dans le tableau tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Contient les serveurs dont le traitement d’un événement de conformité. Cette table est étroitement associée à la table tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Contient des participants en cours par le service chat et par serveur. Il est conservé en fonction des événements de conformité jointure et une partie reçus du service Chat persistant.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Contient des informations d’état de conformité de l’ensemble du pool.  <br/> |
   

