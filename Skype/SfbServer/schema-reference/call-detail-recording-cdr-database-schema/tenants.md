---
title: Table Tenants
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La table de locataires est une table de support qui stocke une liste des locataires différents. Chaque enregistrement de la table représente un locataire.
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a>Table Tenants
 
La table de locataires est une table de support qui stocke une liste des locataires différents. Chaque enregistrement de la table représente un locataire.
  
> [!NOTE]
> Dans un déploiement sur site, CDR utilise le nom de build locataire pour indiquer le type d’authentification, telles que la connectivité PIC, fédéré et anonyme. 
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Principal  <br/> |Numéro unique qui identifie ce code de client.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  00000000-0000-0000-0000-000000000000-entreprise <br/>  00000000-0000-0000-0000-000000000001-fédéré <br/>  Valeur 00000000-0000-0000-0000-000000000002 - anonyme <br/>  00000000-0000-0000-0000-000000000003-la connectivité PIC <br/> |
   

