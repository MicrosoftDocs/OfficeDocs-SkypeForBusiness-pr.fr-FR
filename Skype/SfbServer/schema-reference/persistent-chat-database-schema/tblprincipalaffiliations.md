---
title: tblPrincipalAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des endroits, y compris les groupes de sécurité de Services de domaine Active Directory, dans des conteneurs Active Directory, dans des domaines.
ms.openlocfilehash: 4e5529590a6a636c28c801392953c7fd69e9f649
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des endroits, y compris les groupes de sécurité de Services de domaine Active Directory, dans des conteneurs Active Directory, dans des domaines.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|principalID  <br/> |int, non null  <br/> |ID de l’entité de sécurité liée.  <br/> |
|affiliationID  <br/> |int, non null  <br/> |ID de l’entité de sécurité représentant l’affiliation. Chaque entité de sécurité (à l’exception du système-utilisateur-types) possède une affiliation de Self ainsi.  <br/> |
|index  <br/> |int, non null  <br/> |Index. La valeur d’affiliations Self est -1, et pour les autres affiliations augmente séquentiellement à partir de 1 dans chaque \<principalID, affiliationId\> pot.  <br/> |
|updatedBy  <br/> |int, non null  <br/> |Entité de sécurité qui ont fait de la dernière mise à jour. Il s’agit généralement de 1, ce qui signifie que la synchronisation Active Directory.  <br/> |
   
**Clés**

|**Colonnes**|**Description**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clé primaire.  <br/> |
|principalID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.  <br/> |
   

