---
title: Affichage de session
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: Le mode session stocke les informations sur les sessions contenant des enregistrements dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: cd304123022e0d4d921ecb1cd2599c636aaa9013
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805902"
---
# <a name="session-view"></a>Affichage de session
 
Le mode session stocke les informations sur les sessions contenant des enregistrements dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |DateHeure  <br/> |Fait référence à partir de la table MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar (450)  <br/> |URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.  <br/> |
|Correspondance  <br/> |varchar (max)  <br/> |ID de corrélation de la session.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Catégorie de boîte de dialogue. 0 est Skype entreprise Server vers une jambe du serveur de médiation ; 1 est un serveur de médiation en tronçon de passerelle PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indique si l’appel a été ignoré.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Ce champ, s’il est présent, indique pourquoi un appel n’a pas été ignoré, même si les ID de contournement correspondent. Pour Skype entreprise Server, une seule valeur est définie :  <br/> 0x0001-ID de contournement inconnu pour la carte réseau par défaut  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début de l’appel.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de l’appel.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool d’appelant.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du pool d’appel.  <br/> |
|CallerPAI  <br/> |nvarchar (450)  <br/> |URI d’identité ayant une assertion p d’appelant.  <br/> |
|CalleePAI  <br/> |nvarchar (450)  <br/> |URI d’identité affirmée de l’appelant.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur de l’appelant.  <br/> |
|CallerUserAgentType  <br/> |type  <br/> |Type de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la [table UserAgent](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la [table UserAgentDef](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur de l’appelant.  <br/> |
|CalleeUserAgentType  <br/> |type  <br/> |Type d’agent utilisateur pour l’appelant. Pour plus d’informations, voir la [table UserAgent](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la [table UserAgentDef](useragentdef-qoe.md) . <br/> |
|CallerURI  <br/> |nvarchar (450)  <br/> |URI de l’appelant.  <br/> |
|CalleeURI  <br/> |nvarchar (450)  <br/> |URI de l’appelant.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorité de l’appel.  <br/> |
   

