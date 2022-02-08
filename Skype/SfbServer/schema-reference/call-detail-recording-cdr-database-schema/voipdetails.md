---
title: Affichage VoIPDetails
ms.reviewer: ''
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 5804f32dfebb2fe8c6844acb0bcd343c5b6ead21
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385402"
---
# <a name="voipdetails-view"></a>Affichage VoIPDetails
 
La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue VoIPDetails contient toutes les colonnes de l’affichage [SessionDetails](sessiondetails-0.md) en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur qui a initié la session.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur qui a rejoint la session.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Type de URI de l’utilisateur qui a déconnecté la session. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI du téléphone de l’utilisateur qui a déconnecté la session.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a initié la session.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a rejoint la session.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a initié la session.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a rejoint la session.  <br/> |
   

