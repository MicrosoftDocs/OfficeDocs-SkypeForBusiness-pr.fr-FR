---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: la table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212627"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
la table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID d’événement.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identité du serveur (correspondant à la table tblServerIdentity.serverID).  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|fanoutEventID  <br/> |Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.  <br/> |
   

