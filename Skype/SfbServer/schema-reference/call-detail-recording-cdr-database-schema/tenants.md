---
title: Table Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table Tenants est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
ms.openlocfilehash: 37387fe3bbb4bae7b09a0898ee65373f5342c488
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863331"
---
# <a name="tenants-table"></a>Table Tenants
 
La table Tenants est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
  
> [!NOTE]
> Dans les déploiement sur site, CDR utilise l’ID de client intégré pour indiquer différents types d’authentification, tels que la connectivité de messagerie instantanée publique, l’authentification fédérée et l’authentification anonyme. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cet ID de client.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  00000000-0000-0000-0000-000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - Fédéré <br/>  00000000-0000-0000-0000-000000000002 - Anonyme <br/>  00000000-0000-0000-0000-00000000003 - Connectivité DE MESSAGERIE INSTANTANÉE publique <br/> |
   

