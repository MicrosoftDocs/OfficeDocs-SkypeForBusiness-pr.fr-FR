---
title: Affichage FocusJoinsAndLeaves
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
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La vue FocusJoinsAndLeaves stocke des informations sur la participation à une conférence ainsi qu’à son abandon. Chaque conférence est représentée dans cette vue par un enregistrement renseigné chaque fois qu’un utilisateur rejoint et quitte la conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 30e6535461c8887a832fec39bfd14c51976260d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821664"
---
# <a name="focusjoinsandleaves-view"></a>Affichage FocusJoinsAndLeaves
 
La vue FocusJoinsAndLeaves stocke des informations sur la participation à une conférence ainsi qu’à son abandon. Chaque conférence est représentée dans cette vue par un enregistrement renseigné chaque fois qu’un utilisateur rejoint et quitte la conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de l’instance de conférence. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau Conférences dans Skype Entreprise [Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification de l’instance de conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau Conférences dans Skype Entreprise [Server 2015.](conferences.md) <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locataire de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version de client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées. Pour plus d’informations, voir le [tableau UserAgentDef.](useragentdef.md) <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est un utilisateur interne ou non.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Si un utilisateur est connecté sur plusieurs ordinateurs ou périphériques en même temps, la colonne UserInstance permet d’identifier de manière unique la combinaison utilisateur/périphérique.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de dialogue SIP de la session. Le format est le suivant : dialogue;balise-départ;balise-destination.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Heure à laquelle cet utilisateur a rejoint la conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Heure à laquelle cet utilisateur a quitté la conférence.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Rôle de l’utilisateur dans la conférence, tel que présentateur ou participant.  <br/> |
   

