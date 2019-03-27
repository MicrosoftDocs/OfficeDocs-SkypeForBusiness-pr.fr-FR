---
title: Vue Registration
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: L’affichage de l’enregistrement stocke des informations sur l’inscription des utilisateurs. Cet affichage est une nouveauté de Lync Server 2013.
ms.openlocfilehash: bf6797bee124653515744d3c1bcd481c2ea1bfc2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887885"
---
# <a name="registration-view"></a>Vue Registration
 
L’affichage de l’enregistrement stocke des informations sur l’inscription des utilisateurs. Cet affichage est une nouveauté de Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**RegisterTime** <br/> |DateHeure  <br/> |Heure à laquelle l’enregistrement.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur inscrit.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur inscrit. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur inscrit. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison de l’utilisateur inscrit avec.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificateur unique utilisé pour différencier des inscriptions qui impliquent le même utilisateur et le même point de terminaison.  <br/> |
|**DeRegisterType** <br/> |DateHeure  <br/> |Heure à laquelle la désinscription a eu lieu.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Raison de la désinscription.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur inscrit.  <br/> |
|**TypeClient** <br/> |int  <br/> |Client utilisé par l’utilisateur inscrit. Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Catégorie du client utilisé par l’utilisateur inscrit.  <br/> |
|**Adresse IP** <br/> |nvarchar(256)  <br/> |Adresse IP associée à l’utilisateur. Cela peut être une adresse IPv4 ou IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID du dialogue SIP. Le format de l’est :  <br/> boîte de dialogue de balise ; pour une balise  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**serveur d’inscriptions** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur d’inscriptions.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant capturé les données pour la session.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur inscrit.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indique si l’utilisateur connecté à partir du réseau interne.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indique si UserService était disponible au moment de l’inscription.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indique si l’inscription a avec le serveur d’inscriptions principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Adresse MAC du périphérique est enregistré.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricant du périphérique enregistré. Voir la [table Manufacturers dans Skype pour Business Server 2015](manufacturers.md) pour plus d’informations. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Version du matériel de l’appareil inscrit. Consultez la [table HardwareVersions dans Skype pour Business Server 2015](hardwareversions.md) pour plus d’informations. <br/> |
   

