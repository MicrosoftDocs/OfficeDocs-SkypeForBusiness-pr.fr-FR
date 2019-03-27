---
title: Affichage de la session
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: L’affichage de la Session stocke des informations sur les sessions disposant d’enregistrements dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: c72773b4ff87786ab5b4e73b67e89032dc393fa1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880220"
---
# <a name="session-view"></a>Affichage de la session
 
L’affichage de la Session stocke des informations sur les sessions disposant d’enregistrements dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|Paramètre ConferenceDateTime  <br/> |DateHeure  <br/> |Référencé depuis la MediaLine Table.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |Conférence URI s’il s’agit une conférence, ou DialogID s’il est une session d’égal à égal.  <br/> |
|Corrélation  <br/> |varchar (max)  <br/> |ID de corrélation de la session.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Catégorie de la boîte de dialogue ; 0 est Skype pour Business Server vers le serveur de médiation ; 1 est le serveur de médiation vers branche de passerelle PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indique si l’appel a été contourné.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Ce champ, s’il est présent, indique pourquoi un appel a été contourné pas même si le contournement de média ID correspondant. Pour Skype pour Business Server, une seule valeur est définie :  <br/> 0 x 0001 - ID de contournement inconnu pour la carte réseau par défaut  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début d’appel.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de l’appel.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN du pool de l’appelant.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN du pool de l’appelé.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |P-asserted-identity l’appelant URI.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |P-asserted-identity l’appelé URI.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur l’appelant.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Type d’agent utilisateur de l’appelant. Voir la [table UserAgent](useragent.md) pour plus d’informations. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Consultez la [table UserAgentDef (QoE)](useragentdef-qoe.md) pour plus d’informations. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur appelé.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Type d’agent utilisateur de l’appelé. Voir la [table UserAgent](useragent.md) pour plus d’informations. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelé. Consultez la [table UserAgentDef (QoE)](useragentdef-qoe.md) pour plus d’informations. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI de l’appelant.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI de l’appelé.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorité de l’appel.  <br/> |
   

