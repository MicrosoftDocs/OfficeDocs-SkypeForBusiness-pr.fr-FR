---
title: Table Registration
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Chaque enregistrement représente un événement relatif à l’inscription d’un utilisateur.
ms.openlocfilehash: c4c9ca266ac366526df1723bebc7ef58e9470187
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746540"
---
# <a name="registration-table"></a>Table Registration
 
Chaque enregistrement représente un événement relatif à l’inscription d’un utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |int  <br/> |Étranger  <br/> |ID de l’utilisateur. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||GUID pour identifier un système d’extrémité d’inscription. Généralement, l’événement d’inscription d’un même ordinateur et d’un même utilisateur aura le même ID de système d’extrémité. Des ordinateurs différents ont un ID de système d’extrémité différent.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID utilisé pour différencier des inscriptions qui impliquent le même utilisateur et le même point de terminaison.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Étranger  <br/> |Version du client de l’utilisateur actuel. Pour plus [d’informations, voir la table ClientVersions Skype Entreprise Server 2015.](clientversions.md) <br/> |
|**RegistrarId** <br/> |int  <br/> |Étranger  <br/> |ID du serveur d’inscriptions utilisé pour l’inscription. Pour plus [d’informations, voir](servers.md) la table Servers. <br/> |
|**PoolId** <br/> |int  <br/> |Étranger  <br/> |ID du pool dans lequel la session a été capturée. Pour plus [d’informations, voir](pools.md) la table Pools. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Étranger  <br/> |Serveur Edge sur lequel l’inscription a lieu. Pour plus d’informations, voir la [table EdgeServers Skype Entreprise Server 2015.](edgeservers.md) <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Si l’utilisateur est connecté en interne ou non.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si UserService est disponible ou non.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Si l’inscription est effectuée sur le serveur d’inscriptions principal ou non.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indique si l’utilisateur est inscrit ou non avec un Survivable Branch Appliance.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |DateHeure  <br/> ||Heure d’inscription.  <br/> |
|**DeRegisterTime** <br/> |DateHeure  <br/> ||Heure de désinscription.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse de la demande d’inscription.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic de la demande d’inscription. Indique les informations du type de diagnostic.  <br/> |
|**DeviceId** <br/> |int  <br/> |Étranger  <br/> |L’appareil à partir duquel est émise la demande d’inscription. Pour plus d’informations, voir la table Devices [Skype Entreprise Server 2015.](devices.md) <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Étranger  <br/> |Raison de la dés-inscription, telle que « initié par l’utilisateur » et « expiration de l’inscription » et « échec du client » et bien plus encore. Pour plus d’informations, voir la [table DeRegisterType Skype Entreprise Server 2015.](deregistertype.md) <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Adresse IP du point de terminaison avec laquelle l’utilisateur s’est inscrit. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

