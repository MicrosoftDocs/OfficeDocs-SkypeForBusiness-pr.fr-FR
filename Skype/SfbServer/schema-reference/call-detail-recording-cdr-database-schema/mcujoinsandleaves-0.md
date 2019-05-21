---
title: Affichage McuJoinsAndLeaves
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: Le mode McuJoinsAndLeaves stocke les informations sur les utilisateurs qui rejoignent et laissent des informations pour un serveur de conférence. Chaque enregistrement de cette vue contient les détails de l’une des combinaisons d’un utilisateur qui rejoint ou quittent le serveur de conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 9d5617449e5b12c13d855c1a93b39490e2177f0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296076"
---
# <a name="mcujoinsandleaves-view"></a>Affichage McuJoinsAndLeaves
 
Le mode McuJoinsAndLeaves stocke les informations sur les utilisateurs qui rejoignent et laissent des informations pour un serveur de conférence. Chaque enregistrement de cette vue contient les détails de l’une des combinaisons d’un utilisateur qui rejoint ou quittent le serveur de conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Durée de l’instance de conférence. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |URI du serveur de conférence auquel l’utilisateur s’est connecté.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |URI du serveur de conférence auquel l’utilisateur s’est connecté. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Le type d’URI de l’utilisateur dont le serveur de conférence a été capturé. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Le client de l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |La version du client utilisée par l’utilisateur dont les informations de jointure/de conservation du serveur de conférence ont été capturées.  <br/> |
|**UserClientType** <br/> |int  <br/> |Le client utilisé par l’utilisateur qui a capturé les informations de jointure/conservation du serveur de conférence. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Le nom de la catégorie du client utilisée par l’utilisateur dont les informations de jointure/conservation du serveur de conférence ont été capturées.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifie de manière unique la combinaison utilisateur/appareil pour les utilisateurs connectés simultanément à plusieurs appareils.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est ou non un utilisateur interne.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Durée de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |IDENTIFIant de la session. Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |ID de la boîte de dialogue SIP de la session. Le format est: boîte de dialogue; de-balise; à balise.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Temps pendant lequel l’utilisateur a rejoint le serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Temps pendant lequel l’utilisateur a quitté le serveur de conférence.  <br/> |
   

