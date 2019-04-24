---
title: Affichage de l’utilisateur
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: L’affichage utilisateur stocke des informations sur les utilisateurs qui ont participé à des appels ou des sessions disposant d’enregistrements dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213178"
---
# <a name="user-view"></a>Affichage de l’utilisateur
 
L’affichage utilisateur stocke des informations sur les utilisateurs qui ont participé à des appels ou des sessions disposant d’enregistrements dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|Nom d’utilisateur  <br/> |int  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI de l’utilisateur.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Client de l’utilisateur. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

