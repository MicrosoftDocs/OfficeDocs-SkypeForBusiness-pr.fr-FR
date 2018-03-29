---
title: Table Registration
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Chaque enregistrement représente un événement de l’enregistrement d’utilisateur.
ms.openlocfilehash: 87a05d49c9dbf723203bf8efe02dee7cd16550a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="registration-table"></a>Table Registration
 
Chaque enregistrement représente un événement de l’enregistrement d’utilisateur.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Heure de la demande de la session. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ID utilisateur** <br/> |int  <br/> |Étrangère  <br/> |L’ID utilisateur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||Un GUID pour identifier un point de terminaison de l’enregistrement. Généralement, l’événement d’historique à partir de l’ordinateur de l’utilisateur aura le même ID de point de terminaison. Différentes machines ont un code de point de terminaison différent.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID utilisé pour différencier les enregistrements qui concernent le même utilisateur et le même point de terminaison.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Étrangère  <br/> |Version du client de l’utilisateur actuel. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**RegistrarId** <br/> |int  <br/> |Étrangère  <br/> |ID du serveur Registrar utilisés pour l’enregistrement. Consultez le [tableau des serveurs](servers.md) pour plus d’informations. <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |ID du pool dans lequel la session a été capturée. Consultez la [table de regroupements](pools.md) pour plus d’informations. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur de transport Edge l’inscription s’effectue via. Consultez la [table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) pour plus d’informations. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Si l’utilisateur est connecté à partir d’interne ou non.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si le UserService est disponible ou non.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||S’inscrire au greffier principal ou non.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indique si l’utilisateur est enregistré grâce à une appliance survivable branch.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |DateHeure  <br/> ||Heure d’enregistrement.  <br/> |
|**DeRegisterTime** <br/> |DateHeure  <br/> ||L’enregistrement des temps.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse de la demande du Registre.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic de la demande du Registre. Cela indique ce type d’informations de diagnostic.  <br/> |
|**ID de périphérique** <br/> |int  <br/> |Étrangère  <br/> |Le périphérique qui provenance de la demande du Registre. Consultez la [table des périphériques dans Skype pour Business Server 2015](devices.md) pour plus d’informations. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Étrangère  <br/> |La raison de le de-register, par exemple « initiée par l’utilisateur », « enregistrement expiré », « défaillance du client » et bien plus encore. Consultez la [table DeRegisterType dans Skype pour Business Server 2015](deregistertype.md) pour plus d’informations. <br/> |
|**Adresse IP** <br/> |nvarchar(256)  <br/> ||Adresse IP du point de terminaison de l’utilisateur inscrit avec. Il peut s’agir d’une adresse IPv4 ou une adresse IPv6.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   

