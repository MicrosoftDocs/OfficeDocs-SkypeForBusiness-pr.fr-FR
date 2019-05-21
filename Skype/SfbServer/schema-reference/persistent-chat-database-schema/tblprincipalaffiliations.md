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
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances aux emplacements, y compris les groupes de sécurité des services de domaine Active Directory (AD FS) dans les conteneurs Active Directory, dans les domaines.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295313"
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
   

