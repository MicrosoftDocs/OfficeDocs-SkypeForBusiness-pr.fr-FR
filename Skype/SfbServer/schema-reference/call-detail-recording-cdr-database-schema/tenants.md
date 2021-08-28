---
title: Table Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table Tenants est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
ms.openlocfilehash: 2705b44830efef4a8f921bf9ccc9c7b8e49f72ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583788"
---
# <a name="tenants-table"></a>Table Tenants
 
La table Tenants est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
  
> [!NOTE]
> Dans les déploiement sur site, CDR utilise l’ID de client intégré pour indiquer différents types d’authentification, tels que la connectivité de messagerie instantanée publique, l’authentification fédérée et l’authentification anonyme. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cet ID de client.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  00000000-0000-0000-0000-000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - Fédéré <br/>  00000000-0000-0000-0000-000000000002 - Anonyme <br/>  00000000-0000-0000-0000-00000000003 - Connectivité DE MESSAGERIE INSTANTANÉE publique <br/> |
   

