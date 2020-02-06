---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations sur l’état de compatibilité à l’échelle du pool.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814632"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contient des informations sur l’état de compatibilité à l’échelle du pool.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, pas null  <br/> |ID de l’événement de conformité traité le plus récent.  <br/> |
|activeServerID  <br/> |ent, non null  <br/> |ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou-1 si aucun.  <br/> |
|lockExpirationTime  <br/> |datetime2, pas null  <br/> |Durée d’expiration du verrouillage (si activeServerID n’est pas-1).  <br/> |
   

