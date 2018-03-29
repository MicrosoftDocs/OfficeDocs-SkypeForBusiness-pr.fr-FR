---
title: tblPrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contient toutes les entités, y compris les utilisateurs, les dossiers et les groupes.
ms.openlocfilehash: 847af7f719b15161738d488408ac11b81d9c57a3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contient toutes les entités, y compris les utilisateurs, les dossiers et les groupes.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID d’entité de sécurité.  <br/> |
|prinGuid  <br/> |GUID, pas null  <br/> |GUID de l’entité de sécurité. Cela est largement utilisé comme une autre clé primaire car sa signification à cheval sur l’espace des Services de domaine Active Directory. (Le GUID pour une entité de sécurité mis en cache est égal à l’objet Active Directory correspondant GUID).  <br/> |
|prinUri  <br/> |nvarchar (256), non null  <br/> |URI de l’entité de sécurité. Le schéma SIP est utilisé pour les utilisateurs, et ma-grp est utilisé pour pratiquement tout le reste.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nom commun. Utilisé uniquement par les types d’utilisateur.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nom d’affichage. Utilisé uniquement par les types d’utilisateur.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nom de la société. Utilisé uniquement par les types d’utilisateur.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Messagerie. Utilisé uniquement par les types d’utilisateur.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nom de l’objet Active Directory que le principal est une version mise en cache du domaine. Peut avoir la valeur Null pour les types qui ne sont pas des objets Active Directory (par exemple, les utilisateurs du système).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Utilisateur principaux (UPN) l’utilisateur. Utilisé uniquement par les types d’utilisateur normal.  <br/> |
|prinDisabled  <br/> |smallint, non null  <br/> | 0 : principal est actif. <br/>  1 : entité de sécurité est désactivée car les fonctions SIP de l’utilisateur sont désactivées. <br/>  2 : principal est supprimé, car l’objet d’Active Directory associé a été supprimé. <br/> |
|prinTypeID  <br/> |smallint, non null  <br/> |Type de principal (à partir de table de tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype Business client d’affectation de pool pour l’entité de sécurité.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Valeur de stratégie serveur Chat permanente pour l’utilisateur, si la stratégie de type de balise est présent.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID principal du créateur.  <br/> |
|prinAddedOn  <br/> |bigint, non null  <br/> |Horodatage de l’heure de création.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID de l’entité de sécurité qui a mis à jour ce.  <br/> |
|prinUpdatedOn  <br/> |bigint, non null  <br/> |Horodatage de la dernière mise à jour.  <br/> |
|prinVerifiedOn  <br/> |DateTime, non null  <br/> |Date et heure de la dernière synchronisation de répertoire Active Actualiser pour l’entité de sécurité.  <br/> |
   
**Clés**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinTypeID  <br/> |Clé étrangère avec la recherche dans la table de tblPrincipalType.ptypeID.  <br/> |
   

