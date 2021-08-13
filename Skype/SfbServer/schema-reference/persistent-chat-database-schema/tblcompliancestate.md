---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations d’état de conformité à l’échelle du pool.
ms.openlocfilehash: c9027068550b4320e1e7d170ee23b6cb6e060d6162583132f927c720c09d6ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315420"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contient des informations d’état de conformité à l’échelle du pool.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, non null  <br/> |ID du dernier événement de conformité traitée.  <br/> |
|activeServerID  <br/> |int, non null  <br/> |ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou -1 si aucun.  <br/> |
|lockExpirationTime  <br/> |datetime2, non null  <br/> |Délai d’expiration du verrouillage (si activeServerID n’est pas -1).  <br/> |
   

