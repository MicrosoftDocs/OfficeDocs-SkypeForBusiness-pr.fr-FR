---
title: Affichage de l’utilisateur
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: L’affichage utilisateur stocke des informations sur les utilisateurs qui ont été impliqués dans les appels ou les sessions qui ont des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a>Affichage de l’utilisateur
 
L’affichage utilisateur stocke des informations sur les utilisateurs qui ont été impliqués dans les appels ou les sessions qui ont des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|ID utilisateur  <br/> |int  <br/> |Numéro unique identifiant l’utilisateur.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI de l’utilisateur.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Clients de l’utilisateur. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Type d’utilisateur URI. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

