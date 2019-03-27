---
title: Vue voipdetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vue voipdetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875552"
---
# <a name="voipdetails-view"></a>Vue voipdetails
 
La vue voipdetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue voipdetails contient toutes les colonnes dans la [vue SessionDetails](sessiondetails-0.md) en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur ayant démarré la session.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur ayant participé à la session.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a déconnecté la session. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur qui a déconnecté la session.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur ayant démarré la session.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur ayant participé à la session.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur ayant démarré la session.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur ayant participé à la session.  <br/> |
   

