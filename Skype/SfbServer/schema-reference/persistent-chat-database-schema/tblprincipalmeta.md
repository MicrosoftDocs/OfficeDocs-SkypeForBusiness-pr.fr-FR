---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory (AD FS).
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813572"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory (AD FS).
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |ent, non null  <br/> |ID du principal.  <br/> |
|prinAffiliationsDirty  <br/> |bit, pas null  <br/> |True si les affiliations principales doivent être actualisées.  <br/> |
|prinAttributesDirty  <br/> |bit, pas null  <br/> |True si les attributs principaux doivent être actualisés.  <br/> |
|prinDeleted  <br/> |bit, pas null  <br/> |True si l’objet principal a été supprimé.  <br/> |
|tryCount  <br/> |int  <br/> |Nombre de tentatives d’actualisation du principal à partir d’AD DS qui est déjà en passe.  <br/> |
|lastTry  <br/> |DateHeure  <br/> |Horodatage de la dernière tentative d’actualisation du principal. Il peut s’agir de la valeur null s’il n’y a pas encore de tentative d’actualisation.  <br/> |
|nextTry  <br/> |DateHeure  <br/> |Horodatage de la prochaine actualisation planifiée. Peut être null s’il n’y a pas de planification ultérieure.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal. prinID.  <br/> |
   

