---
title: Table Users
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Le tableau utilisateurs est une table de prise en charge. Chaque enregistrement dans la table stocke des informations sur un utilisateur impliqué dans les appels ou les sessions qui ont des enregistrements dans la base de données.
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a>Table Users
 
Le tableau utilisateurs est une table de prise en charge. Chaque enregistrement dans la table stocke des informations sur un utilisateur impliqué dans les appels ou les sessions qui ont des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> ||Horodatage pour un usage interne.  <br/> |
|**ID utilisateur** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant l’utilisateur.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI de l’utilisateur.  <br/> |
|**TenantId** <br/> |int  <br/> |Étrangère  <br/> |Cet ID de client. du utilisateur Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**UriTypeId** <br/> |int  <br/> |Étrangère  <br/> |Type d’URI de cet utilisateur. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

