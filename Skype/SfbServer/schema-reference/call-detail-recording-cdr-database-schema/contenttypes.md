---
title: Tableau de types de contenus dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Le tableau de types de contenus est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions de peer-to-peer et des sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tableau de types de contenus dans Skype pour Business Server 2015
 
Le tableau de types de contenus est une table de prise en charge qui stocke une liste des types de contenu utilisés dans les sessions de peer-to-peer et des sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le type de contenu.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nom du type de contenu.  <br/> |
   

