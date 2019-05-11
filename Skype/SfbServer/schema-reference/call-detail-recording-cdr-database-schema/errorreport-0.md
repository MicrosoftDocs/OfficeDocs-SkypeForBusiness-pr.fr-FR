---
title: Vue errorreport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: La vue ErrorReport stocke des informations sur les erreurs signalés. Chaque enregistrement est une occurrence de l’erreur. Les erreurs sont capturés par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé à partir du client. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: d188972cfa806b162e8da251af045cc10c84b47d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901100"
---
# <a name="errorreport-view"></a>Vue errorreport
 
La vue ErrorReport stocke des informations sur les erreurs signalés. Chaque enregistrement est une occurrence de l’erreur. Les erreurs sont capturés par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé à partir du client. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Moment de l’erreur s’est produite. Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique une erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnostic pour le rapport d’erreurs.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur à l’origine de l’erreur.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur à l’origine de l’erreur. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur à l’origine de l’erreur. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui était la cible du rapport d’erreurs.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur cible du rapport d’erreurs. Voir la UriTypes Table pour plus d’informations.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur cible du rapport d’erreurs. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence qui était la cible du rapport d’erreurs.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de la conférence qui était la cible du rapport d’erreurs. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session à l’origine le rapport d’erreurs. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier la demande de session à l’origine le rapport d’erreurs. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de boîte de dialogue SIP de session à l’origine de l’erreur. Le format est :  <br/> boîte de dialogue de balise ; pour une balise  <br/> Ces données peuvent être converties au format texte à l’aide de la syntaxe suivante :  <br/> cast (cast (ExternalId as varchar(max)) varbinary  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur à l’origine de l’erreur.  <br/> |
|**TypeClient** <br/> |int  <br/> |Client utilisé par l’utilisateur à l’origine de l’erreur. Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur à l’origine de l’erreur.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse à la session de message SIP contenant le rapport d’erreurs SIP.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Type de demande ayant échoué.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |Type de contenu de la demande ayant échoué.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Type de session. Voir la [table CallType dans Skype pour Business Server 2015](calltype.md) pour plus d’informations. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificateur unique corrélant les informations d’heure jointure pour les différents composants impliqués dans une conférence.  <br/> |
|**SetupTime** <br/> |int  <br/> |Temps (en millisecondes) nécessaire pour un composant spécifique pour participer à une conférence.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indique si le rapport d’erreurs a été capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.  <br/> |
|**Indicateur** <br/> |smallint  <br/> |Réservé pour une utilisation future.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informations supplémentaires sur l’erreur.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nom de domaine complet du serveur frontal qui a envoyé le rapport.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nom de domaine du pool contenant le serveur frontal qui a envoyé le rapport complet.  <br/> |
   

