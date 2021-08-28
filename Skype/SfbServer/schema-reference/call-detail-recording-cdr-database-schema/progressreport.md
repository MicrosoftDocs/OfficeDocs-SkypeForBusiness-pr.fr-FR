---
title: Table ProgressReport
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Les rapports d’avancement sont basés sur les données téléchargées par le client dans la base de données à l’issue d’un appel ou d’une session. Les rapports d’avancement sont écrits uniquement pour les appels et les sessions qui, selon Skype Entreprise Server 2015, peuvent être utiles à des fins de diagnostic.
ms.openlocfilehash: 2c744cbf3755118a6d6fbee4837363e80b00ae44
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623526"
---
# <a name="progressreport-table"></a>Table ProgressReport
 
Les rapports d’avancement sont basés sur les données téléchargées par le client dans la base de données à l’issue d’un appel ou d’une session. Les rapports d’avancement sont écrits uniquement pour les appels et les sessions qui, selon Skype Entreprise Server 2015, peuvent être utiles à des fins de diagnostic.
  
Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence à des erreurs, mais à des messages qui indiquent l’état des appels ou des messages.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Date et heure du rapport d’erreurs d’avancement qui contient ce rapport d’avancement. Pour plus d’informations, voir le [tableau ErrorReport Skype Entreprise Server 2015.](errorreport.md) <br/> |
|**ErrorId** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification utilisé conjointement avec ErrorTime et ProgressReportSeq pour identifier de manière unique un rapport d’avancement. Pour plus d’informations, voir le [tableau ErrorReport Skype Entreprise Server 2015.](errorreport.md) <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification qui identifie le rapport d’erreurs. ErrorReportSeq est utilisé conjointement avec ErrorTime pour identifier de manière unique un rapport d’erreurs. Voir le [tableau ErrorReport dans Skype Entreprise Server 2015](errorreport.md) pour plus d’informations <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro d’identification utilisé pour identifier le rapport d’avancement. Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de manière unique un rapport d’avancement.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID de diagnostic du rapport d’avancement.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Étranger  <br/> |Serveur qui a envoyé le rapport d’erreurs (si le rapport a été envoyé à partir d’un composant serveur). Pour plus [d’informations, voir](servers.md) la table Servers. Ce champ a été introduit dans Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Processus Lync Server sur lequel porte le rapport. Pour plus d’informations, voir la Table Application.  <br/> |
|**Detail** <br/> |image  <br/> ||Détails du rapport d’avancement, stockés dans un format binaire pour économiser de l’espace. Ces données peuvent être converties au format texte en utilisant la syntaxe suivante :  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificateur unique qui met en corrélation des informations d’heure d’arrivée pour les différents composants impliqués dans la conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Durée (en millisecondes) nécessaire à un composant spécifique pour se joindre à une conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
   

