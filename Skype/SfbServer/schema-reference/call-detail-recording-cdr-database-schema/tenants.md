---
title: Table Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table clients est une table de prise en charge qui stocke une liste de ces locataires différents. Chaque enregistrement de la table représente un client.
ms.openlocfilehash: 68050ce76cc41d3fd66931fbdc0b0d3168786bc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930205"
---
# <a name="tenants-table"></a>Table Tenants
 
La table clients est une table de prise en charge qui stocke une liste de ces locataires différents. Chaque enregistrement de la table représente un client.
  
> [!NOTE]
> Dans un déploiement sur site, CDR utilise l’ID de client intégré pour indiquer différents types d’authentification, telles que la connectivité PIC, fédérés et anonymes. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ID client sur** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet ID de client.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  00000000-0000-0000-0000-000000000000-entreprise <br/>  00000000-0000-0000-0000-000000000001-fédéré <br/>  Valeur 00000000-0000-0000-0000-000000000002 - anonyme <br/>  00000000-0000-0000-0000-000000000003-la connectivité PIC <br/> |
   

