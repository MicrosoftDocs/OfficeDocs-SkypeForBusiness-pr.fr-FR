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
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La table users est une table de prise en charge. Chaque enregistrement de la table stocke des informations relatives à un utilisateur impliqué dans des appels ou des sessions ayant des enregistrements dans la base de données.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295698"
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
   

