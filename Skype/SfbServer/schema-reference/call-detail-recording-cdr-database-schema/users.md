---
title: Table Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La table users est une table de prise en charge. Chaque enregistrement de la table stocke des informations relatives à un utilisateur impliqué dans des appels ou des sessions ayant des enregistrements dans la base de données.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814802"
---
# <a name="users-table"></a>Table Users
 
La table users est une table de prise en charge. Chaque enregistrement de la table stocke des informations relatives à un utilisateur impliqué dans des appels ou des sessions ayant des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateHeure  <br/> ||Horodatage pour un usage interne.  <br/> |
|**UserId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet utilisateur.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |URI de l’utilisateur.  <br/> |
|**IDClient** <br/> |int  <br/> |Externes  <br/> |ID de client de cet utilisateur. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**UriTypeId** <br/> |int  <br/> |Externes  <br/> |Type d’URI de cet utilisateur. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
   

