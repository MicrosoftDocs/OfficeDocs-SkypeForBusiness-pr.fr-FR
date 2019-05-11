---
title: Table Session
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Chaque enregistrement représente une session impliquant audio ou audio et vidéo. Il contient des informations générales sur la session. Une session est définie comme une boîte de dialogue protocole SIP (Session Initiation) audio ou vidéo entre deux points de terminaison.
ms.openlocfilehash: 8aff8bb8be8366fe2e81e4d649d62562e899aab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897154"
---
# <a name="session-table"></a>Table Session
 
Chaque enregistrement représente une session impliquant audio ou audio et vidéo. Il contient des informations générales sur la session. Une session est définie comme une boîte de dialogue protocole SIP (Session Initiation) audio ou vidéo entre deux points de terminaison.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé à partir de la [table de la boîte de dialogue](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé à partir de la [table de la boîte de dialogue](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Étrangère  <br/> |Clé de conférence. Référencé à partir de la [table de conférence](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Étrangère  <br/> |Clé de corrélation. Référencé à partir de la [table SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Catégorie de la boîte de dialogue ; 0 est Skype pour Business Server vers le serveur de médiation ; 1 est le serveur de médiation vers branche de passerelle PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Indicateur signalant si l’appel a été contourné ou non.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Ce champ, s’il est présent, indique pourquoi un appel a été contourné pas même si le contournement de média ID correspondant. Skype pour Business Server, une seule valeur est définie.  <br/> 0 x 0001 - ID de contournement inconnu pour la carte réseau par défaut.  <br/> |
|**StartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début d’appel.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> | <br/> |Heure de fin de l’appel.  <br/> |
|**CallerPool** <br/> |int  <br/> |Étrangère  <br/> |Le pool de l’appelant. Référencé à partir de la [table primaire](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Étrangère  <br/> |Le pool du destinataire de l’appel. Référencé à partir de la [table primaire](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Étrangère  <br/> |URI SIP dans le SIP p-asserted-identity (PAI) de point de terminaison du destinataire. Référencé à partir de la [table de l’utilisateur](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Étrangère  <br/> |URI de l’appelant. Référencé à partir de la [table de l’utilisateur](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Étrangère  <br/> |Point de terminaison de l’appelant. Référencé à partir de la [table de point de terminaison](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Étrangère  <br/> |Agent utilisateur de l’appelant. Référencé depuis la [table UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||La priorité de cet appel.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Cette colonne est déconseillée et n’est pas utilisée dans Skype pour Business Server. Au lieu de cela, ces informations sont signalées sur une ligne par multimédia des bases. Reportez-vous à la [table MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|**CallerPAI** <br/> |int  <br/> |Étrangère  <br/> |P-Asserted-Identity de l’utilisateur qui a passé l’appel. P-Asserted-Identity (PAI) est utilisé pour transmettre l’identité de l’utilisateur qui a passé l’appel de la valeur true.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Étrangère  <br/> |Point de terminaison qui a reçu l’appel.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Étrangère  <br/> |Agent utilisateur employé par l’utilisateur qui a reçu l’appel. Agents utilisateurs représentent le périphérique de point de terminaison client.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Étrangère  <br/> |URI SIP de l’utilisateur qui a reçu l’appel.  <br/> |
   

