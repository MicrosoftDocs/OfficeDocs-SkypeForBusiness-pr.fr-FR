---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison des erreurs d’accès aux services de domaine Active Directory).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812012"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations contient les affiliations qui n’ont pas pu être lues (généralement en raison des erreurs d’accès aux services de domaine Active Directory).
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |ent, non null  <br/> |ID du principal.  <br/> |
|affDescription  <br/> |nvarchar (256), pas null  <br/> |Chaîne identifiant l’affiliation.  <br/> Le format est : GUID : _{0}_ uri : _{1}_> ID :_{2}_ <br/> |
|updatedBy  <br/> |ent, non null  <br/> |ID de l’objet principal qui a mis à jour cette ligne. Il est toujours 1 (utilisateur système), car la synchronisation Active Directory est la seule source de ces entrées.  <br/> |
   
**Permettent**

|**Colonne (s)**|**Description**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Clé primaire.  <br/> |
|prinID  <br/> |Clé étrangère avec recherche dans la table tblPrincipal. prinID.  <br/> |
   

