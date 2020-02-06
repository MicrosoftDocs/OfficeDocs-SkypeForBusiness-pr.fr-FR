---
title: Table Session
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Chaque enregistrement représente une session qui implique du son, de l’audio et de la vidéo. Il contient des informations générales sur la session. Une session est définie comme une boîte de dialogue SIP (Session Initiation Protocol) audio ou vidéo entre deux points de terminaison.
ms.openlocfilehash: f48857f826a4e85519d7dc7d2942d48967df8b01
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805772"
---
# <a name="session-table"></a>Table Session
 
Chaque enregistrement représente une session qui implique du son, de l’audio et de la vidéo. Il contient des informations générales sur la session. Une session est définie comme une boîte de dialogue SIP (Session Initiation Protocol) audio ou vidéo entre deux points de terminaison.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé dans la [table de boîte de dialogue](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé dans la [table de boîte de dialogue](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Externes  <br/> |Clé de conférence. Référence à partir de la [table Conference](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Externes  <br/> |Clé de corrélation. Fait référence à partir de la [table SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Catégorie de boîte de dialogue. 0 est Skype entreprise Server vers une jambe du serveur de médiation ; 1 est un serveur de médiation en tronçon de passerelle PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Indicateur indiquant si l’appel a été ignoré ou non.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Ce champ, s’il est présent, indique pourquoi un appel n’a pas été ignoré, même si les ID de contournement correspondent. Pour Skype entreprise Server, une seule valeur est définie.  <br/> 0x0001-ID de contournement inconnu pour la carte réseau par défaut.  <br/> |
|**StartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de l’appel.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> | <br/> |Heure de fin de l’appel.  <br/> |
|**CallerPool** <br/> |int  <br/> |Externes  <br/> |Le pool de l’appelant. Fait référence à partir de la [table de réserve](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Externes  <br/> |Le regroupement du destinataire de l’appel. Fait référence à partir de la [table de réserve](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Externes  <br/> |URI SIP dans l’identité SIP p-assertion (PAI) du point de terminaison de réception. Référence à partir de la [table utilisateur](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Externes  <br/> |URI de l’appelant. Référence à partir de la [table utilisateur](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Externes  <br/> |Point de terminaison de l’appelant. Fait référence à partir de la [table de points de terminaison](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Externes  <br/> |Agent utilisateur de l’appelant. Référence à partir de la [table UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |type  <br/> ||Priorité de cet appel.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Cette colonne a été déconseillée et n’est pas utilisée dans Skype entreprise Server. À la place, ces informations sont communiquées sur une base de lignes par média. Pour plus d’informations, reportez-vous à la [table MediaLine](medialine-0.md) . <br/> |
|**CallerPAI** <br/> |int  <br/> |Externes  <br/> |P-assertion-identité de l’utilisateur qui a placé l’appel. Le P-assertion-Identity (PAI) est utilisé pour transmettre la véritable identité de l’utilisateur qui a placé l’appel.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Externes  <br/> |Point de terminaison ayant reçu l’appel.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Externes  <br/> |Agent utilisateur utilisé par l’utilisateur qui a reçu l’appel. Les agents utilisateurs représentent l’appareil de point de terminaison client.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Externes  <br/> |URI SIP de l’utilisateur qui a reçu l’appel.  <br/> |
   

