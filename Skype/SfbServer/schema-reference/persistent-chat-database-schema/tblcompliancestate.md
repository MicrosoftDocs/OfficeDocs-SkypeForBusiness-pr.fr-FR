---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations d’état de conformité à l’échelle du pool.
ms.openlocfilehash: 627632625e5898557d650009974fe709ff00e35d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398638"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contient des informations d’état de conformité à l’échelle du pool.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, non null  <br/> |ID du dernier événement de conformité traitée.  <br/> |
|activeServerID  <br/> |int, non null  <br/> |ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou -1 si aucun.  <br/> |
|lockExpirationTime  <br/> |datetime2, non null  <br/> |Délai d’expiration du verrouillage (si activeServerID n’est pas -1).  <br/> |
   

