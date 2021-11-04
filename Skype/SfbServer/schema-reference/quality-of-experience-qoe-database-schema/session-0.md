---
title: Affichage de session
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: L’affichage Session stocke des informations sur les sessions pour lesquelles il existe des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 22ad5fdc02eb7b3dc7531a18f4b40bee0334ce09
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776014"
---
# <a name="session-view"></a>Affichage de session
 
L’affichage Session stocke des informations sur les sessions pour lesquelles il existe des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |DateHeure  <br/> |Référencé depuis la table MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |ID de corrélation de la session.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Catégorie de boîte de dialogue ; 0 est Skype Entreprise Server la partie serveur de médiation ; 1 est la partie serveur de médiation vers passerelle PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indique si l’appel a été contourné ou non.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Ce champ, s’il est présent, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient. Par Skype Entreprise Server, une seule valeur est définie :  <br/> 0x0001 - ID de contournement inconnu pour la carte réseau par défaut  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début de l’appel.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de l’appel.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool des appelants.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool des appelés.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |URI d’identité p-asserted de l’appelant.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |URI d’identité p-asserted de l’appelé.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur de l’appelant.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Type de l’agent utilisateur de l’appelant. Pour plus [d’informations, voir le tableau UserAgent.](useragent.md) <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la [table UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur de l’appelé.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Type de l’agent utilisateur de l’appelé. Pour plus [d’informations, voir le tableau UserAgent.](useragent.md) <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelé. Pour plus d’informations, voir la [table UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI de l’appelant.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI de l’appelé.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorité de l’appel.  <br/> |
   

