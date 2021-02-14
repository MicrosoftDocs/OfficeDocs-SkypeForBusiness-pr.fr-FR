---
title: Affichage d’inscription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: L’affichage Inscription stocke les informations relatives à l’inscription de l’utilisateur. Cette vue a été introduite dans Lync Server 2013.
ms.openlocfilehash: 12508e7efcd96bdb9e3956b4e62c1065235a3f60
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823124"
---
# <a name="registration-view"></a>Affichage d’inscription
 
L’affichage Inscription stocke les informations relatives à l’inscription de l’utilisateur. Cette vue a été introduite dans Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification de la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md) <br/> |
|**RegisterTime** <br/> |DateHeure  <br/> |Heure de l’enregistrement.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur inscrit.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur inscrit. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locataire de l’utilisateur inscrit. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison auprès duquel l’utilisateur est inscrit.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificateur unique utilisé pour différencier les inscriptions du même utilisateur auprès du même point de terminaison.  <br/> |
|**DeRegisterType** <br/> |DateHeure  <br/> |Heure à laquelle la désinscription a eu lieu.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Raison de la désinscription.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur inscrit.  <br/> |
|**ClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur inscrit. Pour plus d’informations, voir la [table UserAgentDef.](useragentdef.md) <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Catégorie du client utilisée par l’utilisateur inscrit.  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |Adresse IP avec laquelle l’utilisateur s’est inscrit. Il peut s’agit d’une adresse IPv4 ou IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de dialogue SIP. Le format est :  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**Registrar** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur d’inscriptions.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur inscrit.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indique si UserService était disponible au moment de l’inscription.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indique si l’inscription a eu lieu auprès du serveur d’inscriptions principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Adresse MAC de l’appareil inscrit.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricant de l’appareil inscrit. Pour plus d’informations, voir le tableau Manufacturers dans [Skype Entreprise Server 2015.](manufacturers.md) <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Version matérielle de l’appareil inscrit. Pour plus d’informations, voir le tableau HardwareVersions dans Skype Entreprise [Server 2015.](hardwareversions.md) <br/> |
   

