---
title: /Errorreport affichage
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: La vue /errorreport stocke des informations sur les erreurs signalées. Chaque enregistrement est une occurrence de l’erreur. Les erreurs sont capturées par l’agent de CD-r en cours d’exécution sur le serveur frontal ou envoyées par le client. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: b1815d4420b5768b065a5695ea09174ecff91912
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-view"></a>/Errorreport affichage
 
La vue /errorreport stocke des informations sur les erreurs signalées. Chaque enregistrement est une occurrence de l’erreur. Les erreurs sont capturées par l’agent de CD-r en cours d’exécution sur le serveur frontal ou envoyées par le client. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Moment de l’erreur s’est produite. Utilisé en association avec ErrorReportSeq pour identifier de manière unique une erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’erreur. Utilisé en association avec ErrorTime pour identifier de manière unique une erreur.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID de diagnostic pour le rapport d’erreurs.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur à l’origine de l’erreur.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur à l’origine de l’erreur. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Clients de l’utilisateur à l’origine de l’erreur. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a été la cible de l’état d’erreur.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur cible du rapport d’erreurs. Consultez le tableau UriTypes pour plus d’informations.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Les clients de l’utilisateur cible du rapport d’erreurs. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence a été la cible de l’état d’erreur.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de la conférence a été la cible de l’état d’erreur. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session provenant du rapport d’erreurs. Utilisé en association avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’ID pour identifier la demande de session provenant du rapport d’erreurs. Utilisé en association avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de boîte de dialogue SIP de la session d’origine de l’erreur. Le format est :  <br/> boîte de dialogue, à partir de balise ; de balise  <br/> Ces données peuvent être converties au format de texte à l’aide de cette syntaxe :  <br/> cast (cast (ExternalId comme varbinary(max)) comme varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur à l’origine de l’erreur.  <br/> |
|**TypeClient** <br/> |int  <br/> |Client utilisé par l’utilisateur à l’origine de l’erreur. Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus de détails. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur à l’origine de l’erreur.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nom du serveur qui a pour origine l’erreur (si le rapport a été envoyé à partir d’un composant de serveur).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant de serveur).  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP code de réponse à la session de message SIP contenant le rapport d’erreurs.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Type de demande qui a échoué.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |Type de contenu de la demande qui a échoué.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Type de session. Consultez le [tableau CallType dans Skype pour Business Server 2015](calltype.md) pour plus d’informations. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificateur de corrélation des informations de durée de jointure pour les différents composants impliqués dans une conférence.  <br/> |
|**SetupTime** <br/> |int  <br/> |Durée (en millisecondes) pour un composant spécifique à joindre la conférence.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indique si le rapport d’erreurs a été capturé par l’agent de CD-r en cours d’exécution sur le serveur frontal, ou envoyé par le client.  <br/> |
|**Indicateur** <br/> |smallint  <br/> |Réservé pour utilisation ultérieure.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Informations supplémentaires sur l’erreur.  <br/> |
|**Site Web frontal** <br/> |nvarchar  <br/> |Nom de domaine pleinement qualifié du serveur frontal qui a présenté le rapport.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nom de domaine du pool contenant le serveur frontal qui a présenté le rapport complet.  <br/> |
   

