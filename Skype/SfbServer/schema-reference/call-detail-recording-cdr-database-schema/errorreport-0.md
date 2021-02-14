---
title: Affichage ErrorReport
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: La vue ErrorReport stocke les informations sur les erreurs signalées. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: e00e2bddaea34be6b09bc211991539ad6123603e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821714"
---
# <a name="errorreport-view"></a>Affichage ErrorReport
 
La vue ErrorReport stocke les informations sur les erreurs signalées. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numéro d’ID identifiant l’erreur. Utilisé conjointement à ErrorTime pour identifier une erreur de manière unique.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnostic pour le rapport d’erreurs.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur à l’origine de l’erreur.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur à l’origine de l’erreur. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur à l’origine de l’erreur. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur cible du rapport d’erreurs.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur cible du rapport d’erreurs. Voir la table UriTypes pour plus d’informations.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur cible du rapport d’erreurs. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence cible du rapport d’erreurs.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de la conférence cible du rapport d’erreurs. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session à l’origine du rapport d’erreurs. Utilisé conjointement à SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’ID identifiant la demande de session à l’origine du rapport d’erreurs. Utilisé conjointement à SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md) <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de dialogue SIP de la session à l’origine de l’erreur. Le format est :  <br/> dialog;from-tag;to-tag  <br/> Ces données peuvent être converties au format texte à l’aide de cette syntaxe :  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur à l’origine de l’erreur.  <br/> |
|**ClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur à l’origine de l’erreur. Pour plus d’informations, voir la [table UserAgentDef.](useragentdef.md) <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur à l’origine de l’erreur.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à la session du message SIP contenant le rapport d’erreurs.  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |Type de la demande ayant échoué.  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |Type de contenu de la demande ayant échoué.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Type de session. Pour plus d’informations, voir la table CallType dans Skype Entreprise [Server 2015.](calltype.md) <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.  <br/> |
|**SetupTime** <br/> |int  <br/> |Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indique si le rapport d’erreurs a été capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.  <br/> |
|**Indicateur** <br/> |smallint  <br/> |Réservé à un usage ultérieur.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Informations supplémentaires sur l’erreur.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nom de domaine complet du serveur frontal qui a envoyé le rapport.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nom de domaine complet du pool contenant le serveur frontal qui a envoyé le rapport.  <br/> |
   

