---
title: Vue de ProgressReport
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La vue ProgressReport stocke des informations sur la session terminée. Rapports de progression seront écrites uniquement pour les appels et les sessions qui détermine de Lync Server 2013 peut s’avérer utile à des fins de Diagnostics. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 7dab41202eb098e2e49e5d4960b0c7b4e4c6570d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="progressreport-view"></a>Vue de ProgressReport
 
La vue ProgressReport stocke des informations sur la session terminée. Rapports de progression seront écrites uniquement pour les appels et les sessions qui détermine de Lync Server 2013 peut s’avérer utile à des fins de Diagnostics. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne pas nécessairement référence à erreurs, mais à des messages qui indiquent l’état des messages ou d’appels. 
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Moment de l’erreur s’est produite. Utilisé en association avec ErrorReportSeq pour identifier de manière unique une erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’erreur. Utilisé en association avec ErrorTime pour identifier de manière unique une erreur.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID pour identifier le rapport de progression. Permet de distinguer les rapports d’avancement du même rapport d’erreurs.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnostic pour le rapport d’erreurs.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nom du serveur qui a pour origine l’erreur (si le rapport a été envoyé à partir d’un composant de serveur).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant de serveur).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificateur de corrélation des informations de durée de jointure pour les différents composants impliqués dans une conférence.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Durée (en millisecondes) pour un composant spécifique à joindre la conférence.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informations d’erreur supplémentaires.  <br/> |
   

