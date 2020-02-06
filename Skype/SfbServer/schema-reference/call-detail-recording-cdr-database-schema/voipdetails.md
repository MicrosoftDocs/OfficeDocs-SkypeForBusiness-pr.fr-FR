---
title: Affichage VoIPDetails
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Le mode VoIPDetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814772"
---
# <a name="voipdetails-view"></a>Affichage VoIPDetails
 
Le mode VoIPDetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Le mode VoIPDetails contient toutes les colonnes de la [vue SessionDetails](sessiondetails-0.md) , en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)  <br/> |URI du téléphone de l’utilisateur qui a démarré la session.  <br/> |
|**À la une** <br/> |nvarchar (450)  <br/> |URI de téléphone de l’utilisateur qui a rejoint la session.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a déconnecté la session. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a déconnecté la session.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |URI de téléphone de l’utilisateur qui a déconnecté la session.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a démarré la session.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur ayant rejoint la session.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a démarré la session.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur ayant rejoint la session.  <br/> |
   

