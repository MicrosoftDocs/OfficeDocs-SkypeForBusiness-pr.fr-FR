---
title: Affichage d’inscription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: Le mode d’enregistrement enregistre des informations sur l’inscription des utilisateurs. Cet affichage a été présenté dans Lync Server 2013.
ms.openlocfilehash: 0ee19d4addae9ee7318828c4ab294dc15bd72f86
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814952"
---
# <a name="registration-view"></a>Affichage d’inscription
 
Le mode d’enregistrement enregistre des informations sur l’inscription des utilisateurs. Cet affichage a été présenté dans Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Durée de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |IDENTIFIant de la session. Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**RegisterTime** <br/> |DateHeure  <br/> |Heure à laquelle l’inscription s’est produite.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur inscrit.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur inscrit. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur inscrit. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**EndpointId** <br/> |identificateur  <br/> |Identificateur unique du point de terminaison de l’utilisateur enregistré avec.  <br/> |
|**EndpointEra** <br/> |identificateur  <br/> |Identificateur unique utilisé pour différencier les inscriptions qui impliquent le même utilisateur et le même point de terminaison.  <br/> |
|**DeRegisterType** <br/> |DateHeure  <br/> |Heure à laquelle l’annulation de l’inscription s’est produite.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Raison de l’annulation de l’inscription.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur inscrit.  <br/> |
|**TypeClient** <br/> |int  <br/> |Client utilisé par l’utilisateur inscrit. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Catégorie du client utilisée par l’utilisateur qui est inscrit.  <br/> |
|**Grat** <br/> |nvarchar(256)  <br/> |Adresse IP de l’utilisateur avec lequel il a été enregistré. Il s’agit éventuellement d’une adresse IPv4 ou IPv6.  <br/> |
|**DialogId** <br/> |varstring (LGA775)  <br/> |ID de boîte de dialogue SIP. Le format de :  <br/> boîte de dialogue ; à partir d’une balise  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de la session. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**serveur d’inscriptions** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du Bureau d’enregistrement.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui est inscrit.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indique si l’utilisateur s’est connecté à partir du réseau interne.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indique si l’UserService a été disponible au moment de l’inscription.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indique si l’inscription a été apportée au bureau d’enregistrement principal.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Adresse MAC de l’appareil inscrit.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Fabricant de l’appareil inscrit. Pour plus d’informations, reportez-vous [à la table constructeurs dans Skype entreprise Server 2015](manufacturers.md) . <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Version matérielle de l’appareil inscrit. Pour plus d’informations, reportez-vous [à la table HardwareVersions dans Skype entreprise Server 2015](hardwareversions.md) . <br/> |
   

