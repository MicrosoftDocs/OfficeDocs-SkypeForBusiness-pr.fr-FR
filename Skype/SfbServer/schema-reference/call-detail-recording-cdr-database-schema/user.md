---
title: Affichage utilisateur
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vue User stocke des informations sur les utilisateurs qui ont participé à des appels ou sessions qui possèdent des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 46ce45644d66d0268a0fc57b81df50b018dccf2a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854138"
---
# <a name="user-view"></a>Affichage utilisateur
 
La vue User stocke des informations sur les utilisateurs qui ont participé à des appels ou sessions qui possèdent des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI de l’utilisateur.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Client de l’utilisateur. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
   

