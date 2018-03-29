---
title: Table /errorreport dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: La table /errorreport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement est une occurrence de l’erreur. Les erreurs sont capturées par l’agent de CD-r en cours d’exécution sur le serveur frontal ou envoyées par le client.
ms.openlocfilehash: 80ae8cb9fb4bea586ac31456fc396856e5263a34
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Table /errorreport dans Skype pour Business Server 2015
 
La table /errorreport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement est une occurrence de l’erreur. Les erreurs sont capturées par l’agent de CD-r en cours d’exécution sur le serveur frontal ou envoyées par le client.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Principal  <br/> |Date et heure de l’erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier l’état d’erreur. Utilisé en association avec **ErrorTime** pour identifier de façon unique un rapport d’erreur. <br/> |
|**Code d’erreur** <br/> |int  <br/> |Étrangère  <br/> |ID unique du type d’erreur. Consultez la [table ErrorDef dans Skype pour Business Server 2015](errordef.md) pour plus d’informations. <br/> |
|**FromUserId** <br/> |int  <br/> |Étrangère  <br/> |Utilisateur à l’origine de la demande qui a provoqué l’erreur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ToUserId** <br/> |int  <br/> |Étrangère  <br/> |Utilisateur de destination de la demande qui a provoqué l’erreur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étrangère  <br/> |Conférence URI relatifs à l’erreur. Consultez la [table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) pour plus d’informations. En général, si ConferenceUriId n’est pas null, puis FromUserId ou ToUserId est null. <br/> |
|**SessionIdTime** <br/> |DateHeure  <br/> |Étrangère  <br/> |Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SourceId** <br/> |int  <br/> |Étrangère  <br/> |Serveur qui a envoyé le rapport d’erreur (si le rapport est envoyé à partir d’un composant de serveur). Consultez le [tableau des serveurs](servers.md) pour plus d’informations. <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Étrangère  <br/> |Serveur qui a envoyé le rapport d’erreur (si le rapport est envoyé à partir d’un composant de serveur). Consultez la [table de l’Application dans Skype pour Business Server 2015](application.md) pour plus d’informations. <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |Plus d’informations sur l’erreur.  <br/> Ces données peuvent être converties au format de texte à l’aide de cette syntaxe :  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Étrangère  <br/> |La version du client de point de terminaison qui envoie le rapport d’erreurs. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Le rapport d’erreurs capturé par l’agent de CD-r en cours d’exécution sur le serveur frontal, ou envoyé par le client.  <br/> |
|**Indicateur** <br/> |smallint  <br/> ||Réservé pour utilisation ultérieure.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificateur de corrélation des informations de durée de jointure pour les différents composants impliqués dans une conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Durée (en millisecondes) pour un composant spécifique à joindre la conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Étrangère  <br/> |Représente le nom de domaine complet du serveur qui a généré le rapport d’erreurs.  <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |Représente le nom de domaine complet du pool dans lequel le rapport d’erreurs a été généré.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   

