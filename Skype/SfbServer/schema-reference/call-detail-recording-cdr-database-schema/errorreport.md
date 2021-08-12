---
title: Table ErrorReport dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: La table ErrorReport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client.
ms.openlocfilehash: 1cac143f50e361598c7985aa585485bd73c9aa79d3b47bd21fb0b70e75b9377e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303677"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Table ErrorReport dans Skype Entreprise Server 2015
 
La table ErrorReport stocke des informations sur les erreurs qui se sont produites. Chaque enregistrement correspond à une occurrence d’erreur. Les erreurs sont capturées par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyées à partir du client.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Date et heure de l’erreur.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro d’identification pour identifier le rapport d’erreurs. Utilisé conjointement avec **ErrorTime** pour identifier de manière unique un rapport d’erreurs. <br/> |
|**ErrorId** <br/> |int  <br/> |Étranger  <br/> |ID unique du type d’erreur. Pour plus [d’informations, voir la table ErrorDef Skype Entreprise Server 2015.](errordef.md) <br/> |
|**FromUserId** <br/> |int  <br/> |Étranger  <br/> |Utilisateur à l’origine de la demande à l’origine de l’erreur. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**ToUserId** <br/> |int  <br/> |Étranger  <br/> |Utilisateur de destination de la demande à l’origine de l’erreur. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étranger  <br/> |URI de conférence lié à l’erreur. Pour plus d’informations, voir la [table ConferenceUris Skype Entreprise Server 2015.](conferenceuris.md) En règle générale, si ConferenceUriId n’est pas null, FromUserId ou ToUserId sera null. <br/> |
|**SessionIdTime** <br/> |DateHeure  <br/> |Étranger  <br/> |Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Étranger  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SourceId** <br/> |int  <br/> |Étranger  <br/> |Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur). Pour plus [d’informations, voir](servers.md) la table Servers. <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Étranger  <br/> |Serveur qui a envoyé le rapport d’erreurs (si le rapport est envoyé à partir d’un composant serveur). Pour plus [d’informations, voir la table Application Skype Entreprise Server 2015.](application.md) <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |Plus d’informations sur l’erreur.  <br/> Ces données peuvent être converties au format texte à l’aide de cette syntaxe :  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Étranger  <br/> |Version du client du point de terminaison qui envoie le rapport d’erreurs. Pour plus [d’informations, voir la table ClientVersions Skype Entreprise Server 2015.](clientversions.md) <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Est-ce que le rapport d’erreurs est capturé par l’agent CDR en cours d’exécution sur le serveur frontal ou envoyé par le client.  <br/> |
|**Indicateur** <br/> |smallint  <br/> ||Réservé à un usage ultérieur.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Délai (en millisecondes) nécessaire pour un composant spécifique pour rejoindre une conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Étranger  <br/> |Représente le nom de domaine complet du serveur qui a généré le rapport d’erreurs.  <br/> |
|**PoolId** <br/> |int  <br/> |Étranger  <br/> |Représente le nom de domaine complet du pool dans lequel le rapport d’erreurs a été généré.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

