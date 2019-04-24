---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des Services de domaine Active Directory.
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212431"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des Services de domaine Active Directory.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|prinAffiliationsDirty  <br/> |bit, non null  <br/> |True si le principal affiliations doivent être actualisés.  <br/> |
|prinAttributesDirty  <br/> |bit, non null  <br/> |True si les principaux attributs doivent être actualisés.  <br/> |
|prinDeleted  <br/> |bit, non null  <br/> |True si le principal a été supprimé.  <br/> |
|tryCount  <br/> |int  <br/> |Nombre de tentatives d’actualisation de l’entité de sécurité de domaine Active Directory ayant eu lieu jusqu'à présent.  <br/> |
|lastTry  <br/> |DateHeure  <br/> |Horodatage de la dernière tentative d’actualisation. Peut être null si aucune actualisation n’a été tentée encore.  <br/> |
|nextTry  <br/> |DateHeure  <br/> |Horodatage de l’actualisation planifiée suivante. Peut être une valeur null si aucune actualisation a été planifiée.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

