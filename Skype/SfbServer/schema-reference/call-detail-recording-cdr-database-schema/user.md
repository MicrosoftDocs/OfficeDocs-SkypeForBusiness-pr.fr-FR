---
title: Affichage utilisateur
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 6508bac1b40ca88429cc0504982ed9d2464ee5d2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777734"
---
# <a name="user-view"></a>Affichage utilisateur
 
La vue User stocke des informations sur les utilisateurs qui ont participé à des appels ou sessions qui possèdent des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI de l’utilisateur.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Client de l’utilisateur. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
   

