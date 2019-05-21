---
title: Affichage ErrorReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: Le mode ErrorReport stocke les informations sur les erreurs signalées. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR exécuté sur le serveur frontal ou envoyées par le client. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: a95d3d1e99fc41727c10ecef7beaafddc213dd17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296272"
---
# <a name="errorreport-view"></a>Affichage ErrorReport
 
Le mode ErrorReport stocke les informations sur les erreurs signalées. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR exécuté sur le serveur frontal ou envoyées par le client. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |L’heure de l’erreur s’est produite. Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique une erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnostic du rapport d’erreur.  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur à l’origine de l’erreur.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur à l’origine de l’erreur. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur à l’origine de l’erreur. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**Visite guidée** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a été la cible du rapport d’erreur.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a ciblé le rapport d’erreur. Pour plus d’informations, voir la table UriTypes.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui cible le rapport d’erreur. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI de la Conférence qui était la cible du rapport d’erreur.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de la Conférence qui était la cible du rapport d’erreur. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**SessionIdTime** <br/> |DateHeure  <br/> |Durée de la demande de session à l’origine du rapport d’erreur. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification identifiant la demande de session à l’origine du rapport d’erreur. Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**DialogId** <br/> |varstring (LGA775)  <br/> |ID de boîte de dialogue SIP de session à l’origine de l’erreur. Le format est le suivant:  <br/> boîte de dialogue; à partir d’une balise  <br/> Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante:  <br/> Cast (Cast (ExternalId) en tant que varchar (max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur à l’origine de l’erreur.  <br/> |
|**TypeClient** <br/> |int  <br/> |Client utilisé par l’utilisateur à l’origine de l’erreur. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Nom de la catégorie du client utilisée par l’utilisateur à l’origine de l’erreur.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à la session du message SIP contenant le rapport d’erreur.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Type de requête ayant échoué.  <br/> |
|**Indiquez** <br/> |varchar (max)  <br/> |Type de contenu de la requête qui a échoué.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Type de session. Pour plus d’informations, reportez-vous [à la table CallType dans Skype entreprise Server 2015](calltype.md) . <br/> |
|**TelemetryId** <br/> |identificateur  <br/> |Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.  <br/> |
|**SetupTime** <br/> |int  <br/> |Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indique si le rapport d’erreur a été capturé par l’agent CDR exécuté sur le serveur frontal ou envoyé par le client.  <br/> |
|**Indication** <br/> |type  <br/> |Réservé pour une utilisation ultérieure.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informations supplémentaires sur l’erreur.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nom de domaine complet du serveur frontal qui a soumis le rapport.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nom de domaine complet du pool contenant le serveur frontal qui a soumis le rapport.  <br/> |
   

