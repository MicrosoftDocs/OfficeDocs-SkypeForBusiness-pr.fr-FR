---
title: Affichage FocusJoinsAndLeaves
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
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: Le mode FocusJoinsAndLeaves stocke des informations sur la participation et la conservation des informations pour une conférence. Chaque conférence est représentée dans cette vue par un enregistrement écrit chaque fois qu’un utilisateur rejoint et quitte la Conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 771685a5546ef5b462a3ce3955406eb535f4c3eb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815192"
---
# <a name="focusjoinsandleaves-view"></a>Affichage FocusJoinsAndLeaves
 
Le mode FocusJoinsAndLeaves stocke des informations sur la participation et la conservation des informations pour une conférence. Chaque conférence est représentée dans cette vue par un enregistrement écrit chaque fois qu’un utilisateur rejoint et quitte la Conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Durée de l’instance de conférence. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a capturé les informations de conférence jointes.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a capturé les informations de conférence jointes. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a capturé des informations de conférence jointes. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**UserEndpointId** <br/> |identificateur  <br/> |Identificateur unique de l’utilisateur qui a capturé les informations de conférence jointes.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur et qui a capturé les informations de conférence jointes.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur et qui a capturé des informations de conférence jointes. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nom de la catégorie du client utilisée par l’utilisateur et ayant capturé des informations de conférence.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est ou non un utilisateur interne.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Durée de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Si un utilisateur ouvre une session sur plusieurs ordinateurs ou appareils en même temps, UserInstance est utilisé pour identifier de façon unique la combinaison utilisateur/appareil.  <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |ID de la boîte de dialogue SIP de la session. Le format est : boîte de dialogue ; de-balise ; à balise.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Temps pendant lequel l’utilisateur a rejoint la Conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Temps pendant lequel l’utilisateur a quitté la Conférence.  <br/> |
|**Rôleutilisateur** <br/> |nvarchar(256)  <br/> |Le rôle de l’utilisateur dans la Conférence, tel que le présentateur ou le participant.  <br/> |
   

