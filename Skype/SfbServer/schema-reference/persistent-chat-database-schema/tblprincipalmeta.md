---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des Services de domaine Active Directory.
ms.openlocfilehash: a13fdcf705075188ae4febd5a2e0c3bc93a4738f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924541"
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
   

