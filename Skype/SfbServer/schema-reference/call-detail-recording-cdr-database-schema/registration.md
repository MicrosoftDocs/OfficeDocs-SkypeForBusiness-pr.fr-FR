---
title: Table Registration
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
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Chaque enregistrement représente un événement d’inscription utilisateur.
ms.openlocfilehash: bca31b85a0b88854760c2a79528792ee82bd272e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814942"
---
# <a name="registration-table"></a>Table Registration
 
Chaque enregistrement représente un événement d’inscription utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de la demande de session. Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**UserId** <br/> |int  <br/> |Externes  <br/> |IDENTIFIant de l’utilisateur. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**EndpointId** <br/> |identificateur  <br/> ||GUID permettant d’identifier un point de terminaison d’inscription. En règle générale, l’événement Register sur le même ordinateur que le même utilisateur aura le même ID de point de terminaison. Différents ordinateurs ont un ID de point de terminaison différent.  <br/> |
|**EndpointEra** <br/> |Identificateur  <br/> ||ID utilisé pour différencier les inscriptions qui impliquent le même utilisateur et le même point de terminaison.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Externes  <br/> |Version du client de l’utilisateur actuel. Pour plus d’informations, reportez-vous [à la table ClientVersions dans Skype entreprise Server 2015](clientversions.md) . <br/> |
|**RegistrarId** <br/> |int  <br/> |Externes  <br/> |ID du serveur d’inscriptions utilisé pour l’inscription. Pour plus d’informations, voir la [table serveurs](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Externes  <br/> |ID du pool dans lequel la session a été capturée. Pour plus d’informations, voir la [table pools](pools.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Externes  <br/> |Serveur Edge le passage à l’inscription. Pour plus d’informations, reportez-vous [à la table EdgeServers dans Skype entreprise Server 2015](edgeservers.md) . <br/> |
|**IsInternal** <br/> |Résolution  <br/> ||Si l’utilisateur est connecté à partir d’une connexion interne ou non.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Si le UserService est disponible ou non.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||S’il est inscrit au bureau d’enregistrement principal ou non.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indique si l’utilisateur est inscrit auprès d’une unité de branchement survivant.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |DateHeure  <br/> ||Durée de l’inscription.  <br/> |
|**DeRegisterTime** <br/> |DateHeure  <br/> ||Durée de l’inscription.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse de la demande Register.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic de la demande d’enregistrement. Ce type d’informations indique ce type d’informations de diagnostic.  <br/> |
|**DeviceId** <br/> |int  <br/> |Externes  <br/> |L’appareil à partir duquel la requête d’enregistrement provient. Pour plus d’informations, voir le [tableau des appareils dans Skype entreprise Server 2015](devices.md) . <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Externes  <br/> |La raison de l’annulation de l’inscription, par exemple « initié par l’utilisateur », « inscription expirée », « échec du client », etc. Pour plus d’informations, reportez-vous [à la table DeRegisterType dans Skype entreprise Server 2015](deregistertype.md) . <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Adresse IP du point de terminaison avec lequel l’utilisateur a été enregistré. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   

