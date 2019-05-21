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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations sur l’état de compatibilité à l’échelle du pool.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295474"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState contient des informations sur l’état de compatibilité à l’échelle du pool.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, pas null  <br/> |ID de l’événement de conformité traité le plus récent.  <br/> |
|activeServerID  <br/> |ent, non null  <br/> |ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou-1 si aucun.  <br/> |
|lockExpirationTime  <br/> |datetime2, pas null  <br/> |Durée d’expiration du verrouillage (si activeServerID n’est pas-1).  <br/> |
   

