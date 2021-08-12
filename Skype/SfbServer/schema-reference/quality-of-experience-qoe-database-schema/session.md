---
title: Table Session
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Chaque enregistrement représente une session qui implique de l’audio ou de l’audio et de la vidéo. Il contient des informations générales sur la session. Une session est définie comme une boîte de dialogue SIP (Session Initiation Protocol) audio ou vidéo entre deux points de terminaison.
ms.openlocfilehash: 749f151def046abdb5169b39ccbd81ea5f07f5d4ee3d1c971ac112a2d4b90cce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340030"
---
# <a name="session-table"></a>Table Session
 
Chaque enregistrement représente une session qui implique de l’audio ou de l’audio et de la vidéo. Il contient des informations générales sur la session. Une session est définie comme une boîte de dialogue SIP (Session Initiation Protocol) audio ou vidéo entre deux points de terminaison.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Référencé à partir de [la table Dialog](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |Référencé à partir de [la table Dialog](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Étranger  <br/> |Clé de conférence. Référencé à partir de la [table Conference](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Étranger  <br/> |Clé de corrélation. Référencé à partir [de la table SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Catégorie de boîte de dialogue ; 0 est Skype Entreprise Server la partie serveur de médiation ; 1 est la partie serveur de médiation vers passerelle PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Indicateur signalant si l’appel a été contourné ou non.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Ce champ, s’il est présent, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient. Par Skype Entreprise Server, une seule valeur est définie.  <br/> 0x0001 - ID de contournement inconnu pour la carte réseau par défaut.  <br/> |
|**StartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de l’appel.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> | <br/> |Heure de fin de l’appel.  <br/> |
|**CallerPool** <br/> |int  <br/> |Étranger  <br/> |Pool de l’appelant. Référencé à partir de la [table Pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Étranger  <br/> |Pool du récepteur d’appels. Référencé à partir de la [table Pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Étranger  <br/> |URI SIP dans l’identité p-asserted SIP (PAI) du point de terminaison de réception. Référencé à partir de [la table User](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Étranger  <br/> |URI de l’appelant. Référencé à partir de [la table User](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Étranger  <br/> |Point de terminaison de l’appelant. Référencé à partir de [la table Endpoint](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Étranger  <br/> |Agent utilisateur de l’appelant. Référencé à partir [de la table UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Priorité de cet appel.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Cette colonne a été dépréciée et n’est pas utilisée dans Skype Entreprise Server. Au lieu de cela, ces informations sont signalées sur une base de lignes par média. Pour plus [d’informations, voir la table MediaLine.](medialine-0.md) <br/> |
|**CallerPAI** <br/> |int  <br/> |Étranger  <br/> |P-Asserted-Identity de l’utilisateur qui a passé l’appel. L’identité P-Asserted-Identity (PAI) est utilisée pour transmettre la véritable identité de l’utilisateur qui a passé l’appel.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Étranger  <br/> |Point de terminaison qui a reçu l’appel.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Étranger  <br/> |Agent utilisateur employé par l’utilisateur qui a reçu l’appel. Les agents utilisateur représentent l’appareil de point de terminaison client.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Étranger  <br/> |URI SIP de l’utilisateur qui a reçu l’appel.  <br/> |
   

