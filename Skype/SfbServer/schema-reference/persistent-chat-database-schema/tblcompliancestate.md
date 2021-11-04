---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 6b7f2af97ab25fc7ad2320921941cc7b1828aa1e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746520"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contient des informations d’état de conformité à l’échelle du pool.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, non null  <br/> |ID du dernier événement de conformité traitée.  <br/> |
|activeServerID  <br/> |int, non null  <br/> |ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou -1 si aucun.  <br/> |
|lockExpirationTime  <br/> |datetime2, non null  <br/> |Délai d’expiration du verrouillage (si activeServerID n’est pas -1).  <br/> |
   

