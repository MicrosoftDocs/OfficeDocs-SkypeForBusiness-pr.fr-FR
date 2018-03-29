---
title: Table Session
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Chaque enregistrement représente une session qui implique audio ou audio et vidéo. Il contient des informations générales sur la session. Une session est définie comme une boîte de dialogue Session Initiation Protocol (SIP) audio ou vidéo entre deux points de terminaison.
ms.openlocfilehash: 24acf23d2dab2dbc4b6586e40aa49cba632d6a68
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="session-table"></a>Table Session
 
Chaque enregistrement représente une session qui implique audio ou audio et vidéo. Il contient des informations générales sur la session. Une session est définie comme une boîte de dialogue Session Initiation Protocol (SIP) audio ou vidéo entre deux points de terminaison.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé à partir de la [table de la boîte de dialogue](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé à partir de la [table de la boîte de dialogue](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Étrangère  <br/> |Clé de la conférence. Référencé à partir de la [table de conférence](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Étrangère  <br/> |Clé de corrélation. Référencé à partir de la [table de SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Catégorie de la boîte de dialogue ; 0 est Skype pour Business Server à la branche de serveur de médiation ; 1 est le serveur de médiation pour jambe de passerelle RTPC.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Indicateur signalant si l’appel a été ignoré ou non.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Ce champ, le cas échéant, indique pourquoi un appel a été ignoré pas même si la mise en correspondance des ID du contournement. Skype pour Business Server, une seule valeur est définie.  <br/> 0 x 0001 - ID de contournement inconnu pour l’adaptateur de réseau par défaut.  <br/> |
|**Heure de début** <br/> |DateHeure  <br/> | <br/> |Appelez l’heure de début.  <br/> |
|**Heure de fin** <br/> |DateHeure  <br/> | <br/> |Appelez l’heure de fin.  <br/> |
|**CallerPool** <br/> |int  <br/> |Étrangère  <br/> |Le pool de l’appelant. Référencé à partir de la [table primaire](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Étrangère  <br/> |Le pool du destinataire de l’appel. Référencé à partir de la [table primaire](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Étrangère  <br/> |URI SIP de l’identité p-assertion de SIP (PAI) du point de terminaison de réception. Référencé à partir de la [table de l’utilisateur](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Étrangère  <br/> |URI de l’appelant. Référencé à partir de la [table de l’utilisateur](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Étrangère  <br/> |Point de terminaison de l’appelant. Référencé à partir de la [table du point de terminaison](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Étrangère  <br/> |Agent utilisateur de l’appelant. Référencé à partir de la [table de l’agent utilisateur](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||La priorité de cet appel.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Cette colonne est déconseillée et n’est pas utilisée dans Skype pour Business Server. Au lieu de cela, cette information est reportée sur un par-ligne d’amarrage. Dans la [table de MediaLine](medialine-0.md) pour plus d’informations, reportez-vous à la section. <br/> |
|**CallerPAI** <br/> |int  <br/> |Étrangère  <br/> |P-affirmée-identité de l’utilisateur qui a passé l’appel. L’identité affirmée P (PAI) est utilisé pour transmettre la véritable identité de l’utilisateur qui a passé l’appel.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Étrangère  <br/> |Point de terminaison qui a reçu l’appel.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Étrangère  <br/> |Agent utilisateur employé par l’utilisateur qui a reçu l’appel. Les agents utilisateurs représentent le périphérique de point de terminaison de client.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Étrangère  <br/> |URI SIP de l’utilisateur qui a reçu l’appel.  <br/> |
   

