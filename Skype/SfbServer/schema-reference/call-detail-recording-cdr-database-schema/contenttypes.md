---
title: Table ContentTypes dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 98e360f218de3cd3e998ae09e5bc4abd83d5b28b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744010"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Table ContentTypes dans Skype Entreprise Server 2015
 
La table ContentTypes est une table annexe qui stocke la liste des types de contenu utilisés dans les sessions d’égal à égal et dans les sessions de conférence. Chaque enregistrement de la table représente un type de contenu.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification du type de contenu.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nom du type de contenu.  <br/> |
   

