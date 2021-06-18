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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809794"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
  
**Columns**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID d’événement.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identité du serveur (correspondant à la table tblServerIdentity.serverID).  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|fanoutEventID  <br/> |Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.  <br/> |
   

