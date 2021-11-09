---
title: Affichage FocusJoinsAndLeaves
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La vue FocusJoinsAndLeaves stocke des informations sur la participation à une conférence ainsi qu’à son abandon. Chaque conférence est représentée dans cette vue par un enregistrement renseigné chaque fois qu’un utilisateur rejoint et quitte la conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 8dcc82fe641b451190236f813f432c237e7fa2e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845057"
---
# <a name="focusjoinsandleaves-view"></a>Affichage FocusJoinsAndLeaves
 
La vue FocusJoinsAndLeaves stocke des informations sur la participation à une conférence ainsi qu’à son abandon. Chaque conférence est représentée dans cette vue par un enregistrement renseigné chaque fois qu’un utilisateur rejoint et quitte la conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de l’instance de conférence. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau [Conferences Skype Entreprise Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification de l’instance de conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau [Conferences Skype Entreprise Server 2015.](conferences.md) <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locataire de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées. Pour plus [d’informations, voir le tableau Tenants.](tenants.md) <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version de client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées. Pour plus d’informations, voir la [table UserAgentDef.](useragentdef.md) <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est un utilisateur interne ou non.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Si un utilisateur est connecté sur plusieurs ordinateurs ou périphériques en même temps, la colonne UserInstance permet d’identifier de manière unique la combinaison utilisateur/périphérique.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de dialogue SIP de la session. Le format est le suivant : dialogue;balise-départ;balise-destination.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Heure à laquelle cet utilisateur a rejoint la conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Heure à laquelle cet utilisateur a quitté la conférence.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Rôle de l’utilisateur dans la conférence, tel que présentateur ou participant.  <br/> |
   

