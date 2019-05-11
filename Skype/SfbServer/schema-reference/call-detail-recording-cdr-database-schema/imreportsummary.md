---
title: Table IMReportSummary dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Le IMReportSummaryTable fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901044"
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
   

