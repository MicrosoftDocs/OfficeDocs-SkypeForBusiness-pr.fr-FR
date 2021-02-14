---
title: Affichage VoIPDetails
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813074"
---
# <a name="voipdetails-view"></a>Affichage VoIPDetails
 
La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue VoIPDetails contient toutes les colonnes dans la vue [SessionDetails](sessiondetails-0.md) en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur qui a initié la session.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur qui a rejoint la session.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Type de URI de l’utilisateur qui a déconnecté la session. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur qui a déconnecté la session.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a initié la session.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a rejoint la session.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a initié la session.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a rejoint la session.  <br/> |
   

