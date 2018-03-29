---
title: tblSkippedAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lue (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contient les affiliations qui n’a pas peuvent être lue (généralement en raison d’erreurs d’accès aux Services de domaine Active Directory).
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID d’entité de sécurité.  <br/> |
|affDescription  <br/> |nvarchar (256), non null  <br/> |Chaîne identifiant l’affiliation.  <br/> Le format est : guid : uri de _{0}_ : _{1}_> id : _{2}_ <br/> |
|updatedBy  <br/> |int, non null  <br/> |ID de l’entité de sécurité mise à jour de cette ligne. Il est toujours 1 (utilisateur du système) car la synchronisation Active Directory est la seule source pour ces écritures.  <br/> |
   
**Clés**

|**Colonne (s)**|**Description**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipal.prinID.  <br/> |
   

