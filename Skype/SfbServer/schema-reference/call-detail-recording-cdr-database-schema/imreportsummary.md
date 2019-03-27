---
title: Table IMReportSummary dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Le IMReportSummaryTable fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: fd907165f7db131e94d09d2b9a531eeb20812734
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881021"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Table IMReportSummary dans Skype pour Business Server 2015
 
Le IMReportSummaryTable fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |DateHeure  <br/> |Principal  <br/> |Date et heure de début de la session de messagerie instantanée.  <br/> |
|**Période** <br/> |char (1)  <br/> |Principal  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Principal  <br/> |Nom de domaine complet du pool hébergeant la session.  <br/> |
|**AuthType** <br/> |int  <br/> |Principal  <br/> |Priorité (par exemple, urgent ou non urgent) de l’appel. Informations de priorité sont stockées dans la [table CallPriorities dans Skype pour Business Server 2015](callpriorities.md).  <br/> |
|**CompteSession** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Nombre total de messages instantanés échangés au cours de la session.  <br/> |
   

