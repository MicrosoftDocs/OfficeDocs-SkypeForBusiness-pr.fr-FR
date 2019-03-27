---
title: Table Users
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Le tableau utilisateurs est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans les appels ou des sessions disposant d’enregistrements dans la base de données.
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885560"
---
# <a name="users-table"></a>Table Users
 
Le tableau utilisateurs est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans les appels ou des sessions disposant d’enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> ||Horodatage pour utilisation interne.  <br/> |
|**Nom d’utilisateur** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI de l’utilisateur.  <br/> |
|**ID client sur** <br/> |int  <br/> |Étrangère  <br/> |Cet ID de client. du utilisateur Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**UriTypeId** <br/> |int  <br/> |Étrangère  <br/> |Type d’URI de cet utilisateur. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

