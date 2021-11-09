---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des emplacements, y compris les groupes de sécurité des services de domaine Active Directory, dans les conteneurs Active Directory, dans les domaines.
ms.openlocfilehash: f3625a9877fffdf024131e4a0f1611018d972660
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864601"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des emplacements, y compris les groupes de sécurité des services de domaine Active Directory, dans les conteneurs Active Directory, dans les domaines.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|principalID  <br/> |int, non null  <br/> |ID du principal affilié.  <br/> |
|affiliationID  <br/> |int, non null  <br/> |ID du principal représentant l’affiliation. Chaque principal (sauf system-user-types) possède également une auto-affiliation.  <br/> |
|Index  <br/> |int, non null  <br/> |Index. La valeur pour les auto-affiliations est -1, et pour les autres affiliations, elle augmente séquentiellement de 1 dans chaque \<principalID, affiliationId\> compartiment.  <br/> |
|updatedBy  <br/> |int, non null  <br/> |Principal qui a effectué la mise à jour la plus récente. Il s’agit généralement de 1, ce qui signifie Active Directory Sync.  <br/> |
   
**Keys**

|**Colonnes**|**Description**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clé primaire.  <br/> |
|principalID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

