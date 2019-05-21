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
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table clients est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295768"
---
# <a name="tenants-table"></a>Table Tenants
 
La table clients est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.
  
> [!NOTE]
> Dans le cadre d’un déploiement local, le CDR utilise l’ID de locataire intégré pour indiquer un type d’authentification différent, tel que la connectivité de messagerie instantanée publique, fédéré et anonyme. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**IDClient** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet ID de client.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valeurs autorisées: <br/>  00000000-0000-0000-0000-000000000000-entreprise <br/>  00000000-0000-0000-0000-000000000001-Federated <br/>  00000000-0000-0000-0000-000000000002-anonyme <br/>  00000000-0000-0000-0000-000000000003-connectivité PIC (Public IM Connectivity) <br/> |
   

