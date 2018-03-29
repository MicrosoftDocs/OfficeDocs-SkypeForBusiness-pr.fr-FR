---
title: Table ProgressReport
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Rapports de progression sont basées sur les données téléchargées par le client à la base de données après qu’un appel ou une session est terminée. Rapports de progression seront écrites uniquement pour les appels et les sessions Skype pour Business Server 2015 détermine peut s’avérer utile à des fins de Diagnostics.
ms.openlocfilehash: 9acf54e7fb00917ad8263d4c40e534beb29b628c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="progressreport-table"></a>Table ProgressReport
 
Rapports de progression sont basées sur les données téléchargées par le client à la base de données après qu’un appel ou une session est terminée. Rapports de progression seront écrites uniquement pour les appels et les sessions Skype pour Business Server 2015 détermine peut s’avérer utile à des fins de Diagnostics.
  
Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne pas nécessairement référence à erreurs, mais à des messages qui indiquent l’état des messages ou d’appels.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Date et heure du rapport d’erreur qui contient ce rapport de progression. Consultez le [tableau /errorreport dans Skype pour Business Server 2015](errorreport.md) pour plus d’informations. <br/> |
|**Code d’erreur** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’identification utilisé conjointement avec ErrorTime, ProgressReportSeq pour identifier de façon unique un rapport de progression. Consultez le [tableau /errorreport dans Skype pour Business Server 2015](errorreport.md) pour plus d’informations. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’ID qui identifie le rapport d’erreurs. ErrorReporSeq est utilisé en association avec ErrorTime pour identifier de façon unique un rapport d’erreur. Consultez le [tableau /errorreport dans Skype pour Business Server 2015](errorreport.md) pour plus d’informations <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier l’état d’avancement. Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de façon unique un rapport de progression.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID de diagnostic de l’état d’avancement.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Étrangère  <br/> |Serveur qui a envoyé le rapport d’erreur (si le rapport a été envoyé à partir d’un composant de serveur). Consultez le [tableau des serveurs](servers.md) pour plus d’informations. Ce champ a été introduit dans Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Le processus de Lync Server que le rapport. Consultez la Table de l’Application pour plus d’informations.  <br/> |
|**Détails** <br/> |image  <br/> ||Détails du rapport Progression, stockés au format binaire pour économiser de l’espace. Ces données peuvent être converties au format de texte à l’aide de la syntaxe suivante :  <br/> cast (cast (détail comme varbinary(max)) comme varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificateur unique que corrélation joindre des informations de durée pour les différents composants impliqués dans une conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Durée (en millisecondes) pour un composant spécifique à joindre la conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
   

