---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations d’état de conformité au niveau du pool.
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212634"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contient des informations d’état de conformité au niveau du pool.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, non null  <br/> |ID du dernier événement de conformité traité.  <br/> |
|activeServerID  <br/> |int, non null  <br/> |ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou -1 si aucun.  <br/> |
|lockExpirationTime  <br/> |dateheure2, non null  <br/> |Verrouiller le délai d’expiration (si activeServerID est différent de -1).  <br/> |
   

