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
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La table Users est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un utilisateur impliqué dans des appels ou des sessions qui ont des enregistrements dans la base de données.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831614"
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
   

