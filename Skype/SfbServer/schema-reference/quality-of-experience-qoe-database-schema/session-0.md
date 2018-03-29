---
title: Affichage de la session
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: L’affichage de la Session stocke des informations sur les sessions qui ont des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 056067b0c0e06b3ce9eb862898345fe4c8ff131c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="session-view"></a>Affichage de la session
 
L’affichage de la Session stocke des informations sur les sessions qui ont des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |DateHeure  <br/> |Référencé à partir de la Table MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |Conférence URI si il s’agit d’une conférence, ou DialogID si ce est une session peer-to-peer.  <br/> |
|Corrélation  <br/> |varchar (max)  <br/> |ID de corrélation de la session.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Catégorie de la boîte de dialogue ; 0 est Skype pour Business Server à la branche de serveur de médiation ; 1 est le serveur de médiation pour jambe de passerelle RTPC.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indique si l’appel a été ignoré.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Ce champ, le cas échéant, indique pourquoi un appel a été ignoré pas même si la mise en correspondance des ID du contournement. Pour Skype pour Business Server, une seule valeur est définie :  <br/> 0 x 0001 - ID de contournement inconnu pour l’adaptateur de réseau par défaut  <br/> |
|Heure de début  <br/> |DateHeure  <br/> |Appelez l’heure de début.  <br/> |
|Heure de fin  <br/> |DateHeure  <br/> |Appelez l’heure de fin.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet de pool d’appelant.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Pool appelé nom de domaine complet.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |Identité de p-affirmée l’appelant URI.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |Identité affirmée de p l’appelé URI.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur de l’appelant.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Type d’agent utilisateur de l’appelant. Consultez le [tableau de UserAgent](useragent.md) pour plus de détails. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Consultez le [tableau de UserAgentDef (QoE)](useragentdef-qoe.md) pour plus d’informations. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur l’appelé.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Type d’agent utilisateur de l’appelé. Consultez le [tableau de UserAgent](useragent.md) pour plus de détails. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelé. Consultez le [tableau de UserAgentDef (QoE)](useragentdef-qoe.md) pour plus d’informations. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI de l’appelant.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI de l’appelé.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorité de l’appel.  <br/> |
   

