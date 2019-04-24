---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent des appartenances dans les emplacements incluant les groupes de sécurité Active Directory Domain Services, dans les conteneurs Active Directory dans les domaines.
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212501"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contient les affiliations principales qui décrivent des appartenances dans les emplacements incluant les groupes de sécurité Active Directory Domain Services, dans les conteneurs Active Directory dans les domaines.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|principalID  <br/> |int, non null  <br/> |ID du principal affilié.  <br/> |
|affiliationID  <br/> |int, non null  <br/> |ID du principal qui représente l’affiliation. Chaque entité (à l’exception du système-utilisateur-types) possède une affiliation Self également.  <br/> |
|index  <br/> |int, non null  <br/> |Index. La valeur d’affiliations Self est -1, et pour les autres affiliations augmente en séquence de 1 au sein de chaque \<principalID, affiliationId\> compartiment.  <br/> |
|updatedBy  <br/> |int, non null  <br/> |Principal ayant effectué la dernière mise à jour. Il s’agit généralement de 1, ce qui signifie que la synchronisation Active Directory.  <br/> |
   
**Clés**

|**Colonnes**|**Description**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clé primaire.  <br/> |
|principalID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

