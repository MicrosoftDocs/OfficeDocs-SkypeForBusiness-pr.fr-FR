---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814652"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |ID de l’événement.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Identité du serveur (correspondant à la table tblServerIdentity. serverID).  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|fanoutEventID  <br/> |Clé étrangère avec recherche dans la table tblComplianceData. cmplEventID.  <br/> |
   

