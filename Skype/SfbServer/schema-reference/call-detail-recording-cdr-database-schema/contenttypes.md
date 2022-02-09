---
title: Table ContentTypes dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La table ContentTypes est une table annexe qui stocke la liste des types de contenu utilisés dans les sessions d’égal à égal et dans les sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
ms.openlocfilehash: f545355a00c37bf5df5f3b849aa29b6bee572c4f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417457"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Table ContentTypes dans Skype Entreprise Server 2015
 
La table ContentTypes est une table annexe qui stocke la liste des types de contenu utilisés dans les sessions d’égal à égal et dans les sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification du type de contenu.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nom du type de contenu.  <br/> |
   

