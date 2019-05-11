---
title: Table ErrorReport dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: La table ErrorReport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement est une occurrence de l’erreur. Les erreurs sont capturés par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé à partir du client.
ms.openlocfilehash: 4cb3cebba59201daa6f2a601ec969ed976ec3167
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930247"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Table ErrorReport dans Skype pour Business Server 2015
 
La table ErrorReport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement est une occurrence de l’erreur. Les erreurs sont capturés par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé à partir du client.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Principal  <br/> |Date et heure de l’erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier le rapport d’erreurs. Utilisé conjointement avec **ErrorTime** pour identifier de manière unique un rapport d’erreurs. <br/> |
|**Code d’erreur** <br/> |int  <br/> |Étrangère  <br/> |ID unique du type d’erreur. Consultez la [table ErrorDef dans Skype pour Business Server 2015](errordef.md) pour plus d’informations. <br/> |
|**FromUserId** <br/> |int  <br/> |Étrangère  <br/> |Utilisateur à l’origine de la demande qui a provoqué l’erreur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ToUserId** <br/> |int  <br/> |Étrangère  <br/> |Utilisateur de destination de la demande qui a provoqué l’erreur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étrangère  <br/> |URI de conférence relatives à l’erreur. Consultez la [table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) pour plus d’informations. En règle générale, si ConferenceUriId n’est pas null, puis FromUserId ou ToUserId est null. <br/> |
|**SessionIdTime** <br/> |DateHeure  <br/> |Étrangère  <br/> |Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ID source** <br/> |int  <br/> |Étrangère  <br/> |Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur). Consultez le [tableau de serveurs](servers.md) pour plus d’informations. <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Étrangère  <br/> |Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur). Consultez la [table de l’Application dans Skype pour Business Server 2015](application.md) pour plus d’informations. <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |Plus d’informations sur l’erreur.  <br/> Ces données peuvent être converties au format texte à l’aide de la syntaxe suivante :  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Étrangère  <br/> |La version du client du point de terminaison qui envoie le rapport d’erreurs. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Est le rapport d’erreurs capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.  <br/> |
|**Indicateur** <br/> |smallint  <br/> ||Réservé pour une utilisation future.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificateur unique corrélant les informations d’heure jointure pour les différents composants impliqués dans une conférence.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Temps (en millisecondes) nécessaire pour un composant spécifique pour participer à une conférence.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Étrangère  <br/> |Représente le nom de domaine complet du serveur qui a généré le rapport d’erreurs.  <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |Représente le nom de domaine complet du pool où le rapport d’erreurs a été généré.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   

