---
title: Table IMReportSummary dans Skype Entreprise Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues dans une organisation. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 41856ffd49029f627fd9af93c5bbe296cddd429a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746670"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Table IMReportSummary dans Skype Entreprise Server 2015
 
IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues dans une organisation. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Date et heure de début de la session de messagerie instantanée.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primaire  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primaire  <br/> |Nom de domaine complet du pool hébergeant la session.  <br/> |
|**AuthType** <br/> |int  <br/> |Primaire  <br/> |Priorité (par exemple, urgent ou non urgent) de l’appel. Les informations de priorité sont stockées dans la [table CallPriorities Skype Entreprise Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Nombre total de messages instantanés échangés au cours de la session.  <br/> |
   

