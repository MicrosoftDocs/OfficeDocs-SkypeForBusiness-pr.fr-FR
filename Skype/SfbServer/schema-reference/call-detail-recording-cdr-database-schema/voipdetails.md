---
title: Vue de VoIPDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vue VoIPDetails stocke des informations sur les sessions d’homologue à homologue, où au moins un utilisateur est un utilisateur de VoIP. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a>Vue de VoIPDetails
 
La vue VoIPDetails stocke des informations sur les sessions d’homologue à homologue, où au moins un utilisateur est un utilisateur de VoIP. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue VoIPDetails contient toutes les colonnes dans la [vue de le SessionDetails](sessiondetails-0.md) en outre les colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a démarré la session du téléphone.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a rejoint la session du téléphone.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a déconnecté la session. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Clients de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a déconnecté la session du téléphone.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a démarré la session.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a rejoint la session.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a démarré la session.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a rejoint la session.  <br/> |
   

