---
title: Table ProgressReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Les rapports de progression sont basés sur les données chargées par le client dans la base de données une fois l’appel ou la session terminée. Les rapports de progression seront écrits uniquement pour les appels et les sessions que Skype entreprise Server 2015 détermine peut être utile à des fins de diagnostic.
ms.openlocfilehash: 9022c7707e0d2f0a4346ed629bf51420c312b10a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295901"
---
# <a name="progressreport-table"></a>Table ProgressReport
 
Les rapports de progression sont basés sur les données chargées par le client dans la base de données une fois l’appel ou la session terminée. Les rapports de progression seront écrits uniquement pour les appels et les sessions que Skype entreprise Server 2015 détermine peut être utile à des fins de diagnostic.
  
Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs, mais aux messages indiquant l’état des appels ou des messages.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Date et heure du rapport d’erreur de progression contenant ce rapport de progression. Pour plus d’informations, reportez-vous [à la table errorreport dans Skype entreprise Server 2015](errorreport.md) . <br/> |
|**ErrorId** <br/> |int  <br/> |Etranger principal  <br/> |Numéro d’identification utilisé conjointement avec ErrorTime, ProgressReportSeq pour identifier de façon unique un rapport de progression. Pour plus d’informations, reportez-vous [à la table errorreport dans Skype entreprise Server 2015](errorreport.md) . <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Etranger principal  <br/> |Numéro identifiant le rapport d’erreur. ErrorReporSeq est utilisé en conjonction avec ErrorTime pour identifier de manière unique un rapport d’erreur. Pour plus d’informations, reportez-vous [à la table errorreport dans Skype entreprise Server 2015](errorreport.md) . <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier le rapport de progression. Utilisé conjointement avec ErrorTime et ErrorReportSeq pour identifier de manière unique un rapport de progression.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID de diagnostic du rapport de progression.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Externes  <br/> |Serveur ayant envoyé le rapport d’erreur (si le rapport a été envoyé à partir d’un composant serveur). Pour plus d’informations, voir la [table serveurs](servers.md) . Ce champ a été présenté dans Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Le processus serveur Lync dont le rapport est sujet. Pour plus d’informations, consultez le tableau de l’application.  <br/> |
|**Détails** <br/> |image  <br/> ||Détails du rapport de progression, enregistrés au format binaire pour économiser de l’espace. Il est possible de convertir les données au format texte à l’aide de la syntaxe suivante:  <br/> Cast (de type «detail») As varchar (max))  <br/> |
|**TelemetryId** <br/> |Identificateur  <br/> ||Identificateur unique qui met en corrélation les informations de connexion aux différents composants impliqués dans une conférence.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Durée (en millisecondes) d’un composant spécifique pour participer à une conférence.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
   

