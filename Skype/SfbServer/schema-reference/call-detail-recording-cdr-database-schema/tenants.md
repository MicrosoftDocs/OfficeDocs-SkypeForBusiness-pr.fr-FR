---
title: Table Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table clients est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814852"
---
# <a name="tenants-table"></a>Table Tenants
 
La table clients est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
  
> [!NOTE]
> Dans le cadre d’un déploiement local, le CDR utilise l’ID de locataire intégré pour indiquer un type d’authentification différent, tel que la connectivité de messagerie instantanée publique, fédéré et anonyme. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**IDClient** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet ID de client.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  00000000-0000-0000-0000-000000000000-entreprise <br/>  00000000-0000-0000-0000-000000000001-Federated <br/>  00000000-0000-0000-0000-000000000002-anonyme <br/>  00000000-0000-0000-0000-000000000003-connectivité PIC (Public IM Connectivity) <br/> |
   

