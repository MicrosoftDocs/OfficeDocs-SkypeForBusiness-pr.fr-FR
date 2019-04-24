---
title: Table ProgressReport
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Rapports de progression sont basées sur les données téléchargées par le client à la base de données après qu’un appel ou une session est terminée. Rapports de progression seront écrit uniquement pour les appels et les sessions Skype pour Business Server 2015 détermine peut s’avérer utile à des fins de Diagnostics.
ms.openlocfilehash: 6d638411f39956664c977e87785a1269ee788a5f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212865"
---
# <a name="progressreport-table"></a>Table ProgressReport
 
Rapports de progression sont basées sur les données téléchargées par le client à la base de données après qu’un appel ou une session est terminée. Rapports de progression seront écrit uniquement pour les appels et les sessions Skype pour Business Server 2015 détermine peut s’avérer utile à des fins de Diagnostics.
  
Les champs ErrorTime, ErrorReportSeq et progressreportseq ne font pas nécessairement référence aux erreurs mais aux messages qui indiquent l’état des appels ou des messages.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Date et heure du rapport d’erreur qui contient ce rapport de progression. Voir la [table ErrorReport dans Skype pour Business Server 2015](errorreport.md) pour plus d’informations. <br/> |
|**Code d’erreur** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification utilisé conjointement avec ErrorTime, progressreportseq ne font pour identifier de manière unique un rapport de progression. Voir la [table ErrorReport dans Skype pour Business Server 2015](errorreport.md) pour plus d’informations. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification qui identifie le rapport d’erreurs. ErrorReporSeq est utilisé conjointement avec ErrorTime pour identifier de manière unique un rapport d’erreurs. Reportez-vous à la [table ErrorReport dans Skype pour Business Server 2015](errorreport.md) pour plus d’informations <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**Progressreportseq ne font** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier le rapport de progression. Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de manière unique un rapport de progression.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID de diagnostic du rapport de progression.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ID source** <br/> |int  <br/> |Étrangère  <br/> |Serveur qui a envoyé le rapport d’erreurs (si le rapport a été envoyé à partir d’un composant serveur). Consultez le [tableau de serveurs](servers.md) pour plus d’informations. Ce champ est une nouveauté dans Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Le processus de Lync Server du rapport. Voir le tableau des applications pour plus d’informations.  <br/> |
|**Détails** <br/> |image  <br/> ||Détails du rapport d’avancement, stockés dans un format binaire pour économiser de l’espace. Ces données peuvent être converties au format texte à l’aide de la syntaxe suivante :  <br/> cast (cast (Detail as varchar(max)) varbinary  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificateur unique que met en corrélation participer à des informations d’heure pour les différents composants impliqués dans une conférence.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Temps (en millisecondes) pour un composant spécifique pour participer à une conférence.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
   

