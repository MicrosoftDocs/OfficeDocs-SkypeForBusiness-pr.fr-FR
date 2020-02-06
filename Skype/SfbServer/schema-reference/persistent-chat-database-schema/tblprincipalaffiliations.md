---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances aux emplacements, y compris les groupes de sécurité des services de domaine Active Directory (AD FS) dans les conteneurs Active Directory, dans les domaines.
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814472"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances aux emplacements, y compris les groupes de sécurité des services de domaine Active Directory (AD FS) dans les conteneurs Active Directory, dans les domaines.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|principalID  <br/> |ent, non null  <br/> |ID du principal affilié.  <br/> |
|affiliationID  <br/> |ent, non null  <br/> |ID de l’objet principal qui représente l’affiliation. Chaque identité (à l’exception des types d’utilisateur système) possède également une auto-affiliation.  <br/> |
|index  <br/> |ent, non null  <br/> |Index. La valeur de auto-affiliations est-1, et pour les autres affiliations, elle augmente séquentiellement de 1 dans \<chaque principalID,\> compartiment affiliationId.  <br/> |
|updatedBy  <br/> |ent, non null  <br/> |Principal ayant effectué la dernière mise à jour. Il s’agit généralement de la méthode de synchronisation Active Directory.  <br/> |
   
**Permettent**

|**Celles**|**Description**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clé primaire.  <br/> |
|principalID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal. prinID.  <br/> |
|affiliationID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal. prinID.  <br/> |
   

