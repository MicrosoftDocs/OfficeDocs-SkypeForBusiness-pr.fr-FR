---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lues (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212606"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lues (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|affDescription  <br/> |nvarchar (256), non null  <br/> |Chaîne identifiant l’affiliation.  <br/> Le format est : guid : _{0}_ uri : _{1}_> id :_{2}_ <br/> |
|updatedBy  <br/> |int, non null  <br/> |ID du principal ayant mis à jour cette ligne. Il est toujours 1 (utilisateur système), car la synchronisation Active Directory est la seule source pour ces entrées.  <br/> |
   
**Clés**

|**Colonnes**|**Description**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal.prinID.  <br/> |
   

