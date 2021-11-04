---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisé à partir des services de domaine Active Directory.
ms.openlocfilehash: c5e8a4464b025b2e1d1b5775ca139b76a95ce633
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756183"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contient les principaux qui doivent être actualisé à partir des services de domaine Active Directory.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID de principal.  <br/> |
|prinAffiliationsDirty  <br/> |bit, non null  <br/> |True si les affiliations de principaux doivent être actualisées.  <br/> |
|prinAttributesDirty  <br/> |bit, non null  <br/> |True si les attributs de principaux doivent être actualisés.  <br/> |
|prinDeleted  <br/> |bit, non null  <br/> |True si le principal doit être supprimé.  <br/> |
|tryCount  <br/> |int  <br/> |Nombre de tentatives d’actualisation à partir des services AD DS ayant eu lieu jusqu’à maintenant.  <br/> |
|lastTry  <br/> |DateHeure  <br/> |Horodatage de la dernière tentative d’actualisation du principal. Peut être null si aucune actualisation n’a encore été tentée.  <br/> |
|nextTry  <br/> |DateHeure  <br/> |Horodatage de la prochaine actualisation planifiée. Peut être null si aucune actualisation supplémentaire n’a été planifiée.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

