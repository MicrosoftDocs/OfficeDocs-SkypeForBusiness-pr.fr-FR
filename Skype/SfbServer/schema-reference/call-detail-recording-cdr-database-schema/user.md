---
title: Affichage utilisateur
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vue User stocke des informations sur les utilisateurs qui ont participé à des appels ou sessions qui possèdent des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831694"
---
# <a name="user-view"></a>Affichage utilisateur
 
La vue User stocke des informations sur les utilisateurs qui ont participé à des appels ou sessions qui possèdent des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI de l’utilisateur.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Client de l’utilisateur. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
   

