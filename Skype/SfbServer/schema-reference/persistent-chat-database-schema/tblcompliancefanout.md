---
title: tblComplianceFanout
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
ms.localizationpriority: medium
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: 34f1a5d7d6ea9f1f37e0f9e8d43159523f0f183a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623456"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID d’événement.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identité du serveur (correspondant à la table tblServerIdentity.serverID).  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|fanoutEventID  <br/> |Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.  <br/> |
   

