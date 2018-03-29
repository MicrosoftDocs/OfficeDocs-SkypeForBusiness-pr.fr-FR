---
title: Vue de l’inscription
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: La vue de l’enregistrement stocke des informations sur l’enregistrement de l’utilisateur. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: e116c2609f1f26268eaaa3413c3a4491da096585
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="registration-view"></a>Vue de l’inscription
 
La vue de l’enregistrement stocke des informations sur l’enregistrement de l’utilisateur. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de la session. Utilisé en association avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**RegisterTime** <br/> |DateHeure  <br/> |Heure à laquelle l’enregistrement s’est produite.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a enregistré.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a enregistré. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Clients de l’utilisateur qui a enregistré. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison de l’utilisateur inscrit avec.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificateur unique utilisé pour différencier les enregistrements qui concernent le même utilisateur et le même point de terminaison.  <br/> |
|**DeRegisterType** <br/> |DateHeure  <br/> |Heure à laquelle la désinscription s’est produite.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motif de l’annulation de l’enregistrement.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur qui a enregistré.  <br/> |
|**TypeClient** <br/> |int  <br/> |Client utilisé par l’utilisateur qui a enregistré. Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus de détails. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Catégorie du client utilisé par l’utilisateur qui a enregistré.  <br/> |
|**Adresse IP** <br/> |nvarchar(256)  <br/> |Adresse IP associée à l’utilisateur. Cela peut être une adresse IPv4 ou IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de boîte de dialogue SIP. Le format de l’est :  <br/> boîte de dialogue, à partir de balise ; de balise  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturée à partir de l’en-tête SIP.  <br/> |
|**Greffier** <br/> |nvarchar(256)  <br/> |Nom de domaine complet de l’agent d’enregistrement.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant capturé les données pour la session.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a enregistré.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indique si l’utilisateur connecté à partir du réseau interne.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indique si le UserService n’était disponible au moment de l’enregistrement.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indique si l’enregistrement a dans le Registre principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Adresse MAC du périphérique est enregistré.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricant du périphérique enregistré. Consultez le [tableau des fabricants dans Skype pour Business Server 2015](manufacturers.md) pour plus d’informations. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Version du matériel du périphérique enregistré. Consultez la [table HardwareVersions dans Skype pour Business Server 2015](hardwareversions.md) pour plus d’informations. <br/> |
   

