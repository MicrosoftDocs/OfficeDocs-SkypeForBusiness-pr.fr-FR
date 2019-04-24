---
title: tblPrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contient tous les principaux, y compris les utilisateurs, les dossiers et les groupes.
ms.openlocfilehash: adeb4e52ea9bd276de09d90945443431fb3be94f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212515"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contient tous les principaux, y compris les utilisateurs, les dossiers et les groupes.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID principal.  <br/> |
|prinGuid  <br/> |GUID, non null  <br/> |GUID principal. Il est largement utilisé comme une autre clé primaire, car sa signification chevauche l’espace de Services de domaine Active Directory. (Le GUID pour une entité de sécurité mis en cache est égal à l’objet Active Directory correspondant GUID).  <br/> |
|prinUri  <br/> |nvarchar (256), non null  <br/> |URI de l’entité de sécurité. Le schéma SIP est utilisé pour les utilisateurs et ma-groupe est utilisé pour presque tout le reste.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nom commun. Utilisé uniquement par les types d’utilisateur.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nom complet. Utilisé uniquement par les types d’utilisateur.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nom de la société. Utilisé uniquement par les types d’utilisateur.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |email. Utilisé uniquement par les types d’utilisateur.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nom de domaine de l’objet Active Directory que le principal est une version de mise en cache. Peut être Null pour les types qui ne sont pas des objets Active Directory (tels que les utilisateurs du système).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nom d’utilisateur principal son (UPN). Utilisé uniquement par les types d’utilisateur régulier.  <br/> |
|prinDisabled  <br/> |smallint, non null  <br/> | 0 : principal est actif. <br/>  1 : principal est désactivé car les fonctionnalités SIP de l’utilisateur sont désactivées. <br/>  2 : principal est supprimé, car l’objet AD associé a été supprimé. <br/> |
|prinTypeID  <br/> |smallint, non null  <br/> |Type de principal (de table tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype Business client d’affectation de pool pour le principal.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Valeur de stratégie de serveur de conversation permanente pour l’utilisateur, si la stratégie de type de balise est présente.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID principal du créateur.  <br/> |
|prinAddedOn  <br/> |bigint, non null  <br/> |Horodatage de l’heure de création.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID du principal qui dernière mise à jour.  <br/> |
|prinUpdatedOn  <br/> |bigint, non null  <br/> |Horodatage de la dernière mise à jour.  <br/> |
|prinVerifiedOn  <br/> |DateTime, non null  <br/> |Date et heure de la synchronisation Active Directory dernière actualisation pour le principal.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinTypeID  <br/> |Clé étrangère avec recherche dans la table tblPrincipalType.ptypeID.  <br/> |
   

