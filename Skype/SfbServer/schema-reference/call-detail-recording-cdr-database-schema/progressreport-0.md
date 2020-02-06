---
title: Affichage ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: L’affichage ProgressReport stocke les informations sur les sessions terminées. Les rapports de progression seront écrits uniquement pour les appels et les sessions que Lync Server 2013 détermine peut être utile à des fins de diagnostic. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814982"
---
# <a name="progressreport-view"></a>Affichage ProgressReport
 
L’affichage ProgressReport stocke les informations sur les sessions terminées. Les rapports de progression seront écrits uniquement pour les appels et les sessions que Lync Server 2013 détermine peut être utile à des fins de diagnostic. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs, mais aux messages indiquant l’état des appels ou des messages. 
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |L’heure de l’erreur s’est produite. Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique une erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID pour identifier le rapport de progression. Permet de distinguer les rapports de progression d’un même rapport d’erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnostic du rapport d’erreur.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**TelemetryId** <br/> |identificateur  <br/> |Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informations supplémentaires sur l’erreur.  <br/> |
   

