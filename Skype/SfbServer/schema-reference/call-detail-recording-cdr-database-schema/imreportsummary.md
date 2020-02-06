---
title: Table IMReportSummary dans Skype entreprise Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Le IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815142"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Table IMReportSummary dans Skype entreprise Server 2015
 
Le IMReportSummaryTable fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |DateHeure  <br/> |Principal  <br/> |Date et heure de début de la session de messagerie instantanée.  <br/> |
|**TimePeriod** <br/> |Char(1  <br/> |Principal  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)  <br/> |Principal  <br/> |Nom de domaine complet du pool hébergeant la session.  <br/> |
|**AuthType** <br/> |int  <br/> |Principal  <br/> |Priorité (par exemple, urgent ou non urgent) de l’appel. Les informations de priorité sont stockées dans la [table CallPriorities dans Skype entreprise Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Nombre total de messages instantanés échangés lors de la session.  <br/> |
   

