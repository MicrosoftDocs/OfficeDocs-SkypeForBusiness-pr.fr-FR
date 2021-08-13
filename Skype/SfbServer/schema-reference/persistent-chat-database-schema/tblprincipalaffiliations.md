---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des emplacements, y compris les groupes de sécurité des services de domaine Active Directory, dans les conteneurs Active Directory, dans les domaines.
ms.openlocfilehash: 5eb67681e5823b8549deb01b44e0bcb771e26882a2cd713d9cf598ae0670335b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341669"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations contient les affiliations principales qui décrivent les appartenances à des emplacements, y compris les groupes de sécurité des services de domaine Active Directory, dans les conteneurs Active Directory, dans les domaines.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|principalID  <br/> |int, non null  <br/> |ID du principal affilié.  <br/> |
|affiliationID  <br/> |int, non null  <br/> |ID du principal représentant l’affiliation. Chaque principal (sauf system-user-types) possède également une auto-affiliation.  <br/> |
|Index  <br/> |int, non null  <br/> |Index. La valeur pour les auto-affiliations est -1, et pour les autres affiliations, elle augmente séquentiellement de 1 dans chaque \<principalID, affiliationId\> compartiment.  <br/> |
|updatedBy  <br/> |int, non null  <br/> |Principal qui a effectué la mise à jour la plus récente. Il s’agit généralement de 1, ce qui signifie Active Directory Sync.  <br/> |
   
**Keys**

|**Columns**|**Description**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Clé primaire.  <br/> |
|principalID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

