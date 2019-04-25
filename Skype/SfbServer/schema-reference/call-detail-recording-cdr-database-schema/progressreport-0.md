---
title: Vue progressreport
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La vue ProgressReport stocke des informations sur les sessions terminées. Rapports de progression seront écrit uniquement pour les appels et les sessions qui détermine de Lync Server 2013 peut s’avérer utile à des fins de Diagnostics. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 5f7cbba2580b83a65dbce00588f3c567317f4df4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212872"
---
# <a name="progressreport-view"></a>Vue progressreport
 
La vue ProgressReport stocke des informations sur les sessions terminées. Rapports de progression seront écrit uniquement pour les appels et les sessions qui détermine de Lync Server 2013 peut s’avérer utile à des fins de Diagnostics. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Les champs ErrorTime, ErrorReportSeq et progressreportseq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages. 
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Moment de l’erreur s’est produite. Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique une erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.  <br/> |
|**Progressreportseq ne font** <br/> |int  <br/> |ID pour identifier le rapport de progression. Utilisé pour distinguer les rapports de progression du même rapport d’erreurs.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnostic pour le rapport d’erreurs.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificateur unique corrélant les informations d’heure jointure pour les différents composants impliqués dans une conférence.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Temps (en millisecondes) nécessaire pour un composant spécifique pour participer à une conférence.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informations d’erreur supplémentaires.  <br/> |
   

