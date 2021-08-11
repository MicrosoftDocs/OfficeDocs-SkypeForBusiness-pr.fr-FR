---
title: tblPrincipalMeta
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
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisé à partir des services de domaine Active Directory.
ms.openlocfilehash: a2cc7ef5313be8abdf50c6cebc5bb8999bf153eeeba0a188cd2d34d2c4608546
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289422"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contient les principaux qui doivent être actualisé à partir des services de domaine Active Directory.
  
**Columns**

|**Colonne**|**Type**|**Description**|
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
   

