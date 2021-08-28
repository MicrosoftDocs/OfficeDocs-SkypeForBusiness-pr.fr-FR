---
title: Table Users
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
ms.localizationpriority: medium
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La table Users est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans des appels ou des sessions qui ont des enregistrements dans la base de données.
ms.openlocfilehash: b2f7dad297a085d3fb5b8dc77c86feb07b094e7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598628"
---
# <a name="users-table"></a>Table Users
 
La table Users est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans des appels ou des sessions qui ont des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> ||Horodat pour une utilisation interne.  <br/> |
|**UserId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI de l’utilisateur.  <br/> |
|**TenantId** <br/> |int  <br/> |Étranger  <br/> |ID de locataire de cet utilisateur. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|**UriTypeId** <br/> |int  <br/> |Étranger  <br/> |Type d’URI de cet utilisateur. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
   

