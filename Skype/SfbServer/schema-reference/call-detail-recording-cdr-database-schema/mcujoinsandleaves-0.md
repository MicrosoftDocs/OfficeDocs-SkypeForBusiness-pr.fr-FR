---
title: Affichage McuJoinsAndLeaves
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: 'La vue McuJoinsAndLeaves stocke des informations sur la participation ou l’arrêt de la participation des utilisateurs pour un serveur de conférence. Chaque enregistrement de cette vue contient les détails des appels sur la participation ou l’arrêt de la participation d’un utilisateur à une conférence, ainsi que sur le serveur de conférence concerné. Cette vue a été introduite dans Microsoft Lync Server 2013.'
---

# <a name="mcujoinsandleaves-view"></a>Affichage McuJoinsAndLeaves
 
La vue McuJoinsAndLeaves stocke des informations sur la participation ou l’arrêt de la participation des utilisateurs pour un serveur de conférence. Chaque enregistrement de cette vue contient les détails des appels sur la participation ou l’arrêt de la participation d’un utilisateur à une conférence, ainsi que sur le serveur de conférence concerné. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de l’instance de conférence. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence. Pour plus [d’informations, voir le tableau Conferences Skype Entreprise Server 2015](conferences.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification de l’instance de conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence. Pour plus [d’informations, voir le tableau Conferences Skype Entreprise Server 2015](conferences.md). <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |URI du serveur de conférence auquel s’est connecté l’utilisateur.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |URI du serveur de conférence auquel s’est connecté l’utilisateur. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence. Pour plus [d’informations, voir le tableau Tenants](tenants.md) . <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence. Pour plus [d’informations, voir la table UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/d’arrêt de participation ont été capturées sur le serveur de conférence.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifie de manière unique la combinaison utilisateur/périphérique pour les utilisateurs connectés simultanément à plusieurs périphériques.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est un utilisateur interne ou non.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Numéro d’identification de la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de dialogue SIP de la session. Le format est le suivant : dialogue;balise-départ;balise-destination.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Heure à laquelle l’utilisateur a joint le serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Heure à laquelle l’utilisateur a quitté le serveur de conférence.  <br/> |
   

