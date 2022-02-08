---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison d’erreurs d’accès aux services de domaine Active Directory).
ms.openlocfilehash: b0996e3208e760c55b1b9d621d00e92a8e7a7112
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394786"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison d’erreurs d’accès aux services de domaine Active Directory).
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|affDescription  <br/> |nvarchar (256), non null  <br/> |Chaîne identifiant l’affiliation.  <br/> Le format est : guid:  _{0}_ uri : _{1}_> id :  _{2}_ <br/> |
|updatedBy  <br/> |int, non null  <br/> |ID du principal qui a mis à jour cette ligne. Il s’agit toujours d’1 (utilisateur système) car la synchronisation Active Directory est la seule source pour ces entrées.  <br/> |
   
**Keys**

|**Colonne(s)**|**Description**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

