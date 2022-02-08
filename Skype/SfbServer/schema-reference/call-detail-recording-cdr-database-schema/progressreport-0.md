---
title: Affichage ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: L’affichage ProgressReport stocke les informations relatives aux sessions terminées. Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: c9a7d093cea7388f66129b94233e29c6e25f21ae
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392266"
---
# <a name="progressreport-view"></a>Affichage ProgressReport
 
L’affichage ProgressReport stocke les informations relatives aux sessions terminées. Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence à des erreurs, mais à des messages qui indiquent l’état des appels ou des messages. 
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numéro d’identification de l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID utilisé pour identifier le rapport d’avancement. Utilisé pour distinguer des rapports d’avancement du même rapport d’erreurs.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnostic pour le rapport d’erreurs.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Durée (en millisecondes) requise pour qu’un composant spécifique rejoigne une conférence.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Informations supplémentaires sur l’erreur.  <br/> |
   

