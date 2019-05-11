---
title: Table Registration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Chaque enregistrement représente un événement d’inscription utilisateur.
ms.openlocfilehash: 1a487a01b0f8b3f6a087099daa32da99b7007445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930601"
---
# <a name="registration-table"></a>Table Registration
 
Chaque enregistrement représente un événement d’inscription utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**Nom d’utilisateur** <br/> |int  <br/> |Étrangère  <br/> |L’ID utilisateur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||GUID pour identifier un point de terminaison d’inscription. Généralement, l’événement de Registre de l’ordinateur de l’utilisateur même même aura le même ID de point de terminaison. Des ordinateurs différents ont un ID de point de terminaison différent.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID utilisé pour différencier des inscriptions qui impliquent le même utilisateur et le même point de terminaison.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Étrangère  <br/> |Version du client de l’utilisateur actuel. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**RegistrarId** <br/> |int  <br/> |Étrangère  <br/> |ID du serveur du serveur d’inscriptions utilisés pour l’enregistrement. Consultez le [tableau de serveurs](servers.md) pour plus d’informations. <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |ID du pool dans lequel la session a été capturée. Consultez le [tableau de Pools](pools.md) pour plus d’informations. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Étrangère  <br/> |Traverse le serveur Edge l’inscription. Consultez la [table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) pour plus d’informations. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Indique si l’utilisateur est connecté interne ou non.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si UserService est disponible ou non.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||S’inscrire pour le serveur d’inscriptions principal ou non.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indique si l’utilisateur est inscrit avec un survivable branch appliance.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |DateHeure  <br/> ||Heure d’inscription.  <br/> |
|**DeRegisterTime** <br/> |DateHeure  <br/> ||Désinscription heure.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse de la demande d’inscription.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic de la demande d’inscription. Indique ce type d’informations de diagnostic.  <br/> |
|**ID de périphérique** <br/> |int  <br/> |Étrangère  <br/> |Le périphérique provenant de la demande d’inscription. Consultez le [tableau des périphériques dans Skype pour Business Server 2015](devices.md) pour plus d’informations. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Étrangère  <br/> |La raison de de-register, par exemple « lancée par l’utilisateur », « expiration de l’inscription », « défaillance du client » et plus. Consultez la [table DeRegisterType dans Skype pour Business Server 2015](deregistertype.md) pour plus d’informations. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Adresse IP du point de terminaison de l’utilisateur inscrit avec. Il peut s’agir d’une adresse IPv4 ou une adresse IPv6.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   

