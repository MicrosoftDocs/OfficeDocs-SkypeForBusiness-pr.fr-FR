---
title: Table ErrorReport dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: La table ErrorReport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR exécuté sur le serveur frontal ou envoyées par le client.
ms.openlocfilehash: de103c61f74b50297f9c012ae7f4c6e1586e87d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815222"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Table ErrorReport dans Skype entreprise Server 2015
 
La table ErrorReport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR exécuté sur le serveur frontal ou envoyées par le client.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Principal  <br/> |Date et heure auxquelles l’erreur s’est produite.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier le rapport d’erreur. Utilisé conjointement avec **ErrorTime** pour identifier de manière unique un rapport d’erreur. <br/> |
|**ErrorId** <br/> |int  <br/> |Externes  <br/> |ID unique du type d’erreur. Pour plus d’informations, reportez-vous [à la table ErrorDef dans Skype entreprise Server 2015](errordef.md) . <br/> |
|**FromUserId** <br/> |int  <br/> |Externes  <br/> |Utilisateur à l’origine de la demande à l’origine de l’erreur. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**ToUserId** <br/> |int  <br/> |Externes  <br/> |Utilisateur de destination pour la requête à l’origine de l’erreur. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externes  <br/> |URI de la conférence liée à l’erreur. Pour plus d’informations, reportez-vous [à la table ConferenceUris dans Skype entreprise Server 2015](conferenceuris.md) . En règle générale, si ConferenceUriId n’est pas null, FromUserId ou ToUserId seront NULL. <br/> |
|**SessionIdTime** <br/> |DateHeure  <br/> |Externes  <br/> |Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Externes  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SourceId** <br/> |int  <br/> |Externes  <br/> |Serveur ayant envoyé le rapport d’erreur (si le rapport est envoyé à partir d’un composant serveur). Pour plus d’informations, voir la [table serveurs](servers.md) . <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Externes  <br/> |Serveur ayant envoyé le rapport d’erreur (si le rapport est envoyé à partir d’un composant serveur). Pour plus d’informations, reportez-vous [à la table d’application dans Skype entreprise Server 2015](application.md) . <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |Plus d’informations sur l’erreur.  <br/> Vous pouvez convertir ces données en format texte à l’aide de la syntaxe suivante :  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Externes  <br/> |Version du client de point de terminaison qui envoie le rapport d’erreur. Pour plus d’informations, reportez-vous [à la table ClientVersions dans Skype entreprise Server 2015](clientversions.md) . <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Est le rapport d’erreur capturé par l’agent CDR exécuté sur le serveur frontal ou envoyé par le client.  <br/> |
|**Indication** <br/> |type  <br/> ||Réservé pour une utilisation ultérieure.  <br/> |
|**TelemetryId** <br/> |Identificateur  <br/> ||Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Externes  <br/> |Représente le nom de domaine complet du serveur qui a généré le rapport d’erreur.  <br/> |
|**PoolId** <br/> |int  <br/> |Externes  <br/> |Représente le nom de domaine complet du pool dans lequel le rapport d’erreur a été généré.  <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   

