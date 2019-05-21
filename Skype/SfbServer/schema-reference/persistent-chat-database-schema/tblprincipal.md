---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contient l’ensemble des principaux, y compris des utilisateurs, des dossiers et des groupes.
ms.openlocfilehash: 5a0b6535ace344951b75f7c5c9488f56a18564ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295362"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contient l’ensemble des principaux, y compris des utilisateurs, des dossiers et des groupes.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |ent, non null  <br/> |ID du principal.  <br/> |
|prinGuid  <br/> |GUID, pas null  <br/> |GUID principal. Cette opération est globalement utilisée comme clé primaire alternative, car sa signification croise l’espace des services de domaine Active Directory. (Le GUID d’un principal mis en cache est égal au GUID d’objet Active Directory correspondant.)  <br/> |
|prinUri  <br/> |nvarchar (256), pas null  <br/> |URI principal. Le schéma SIP est utilisé pour les utilisateurs et ma-GRP est utilisé pour presque tout le reste.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nom usuel. Utilisées uniquement par les types d’utilisateurs.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nom d’affichage. Utilisées uniquement par les types d’utilisateurs.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nom de la société. Utilisées uniquement par les types d’utilisateurs.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Messagerie. Utilisées uniquement par les types d’utilisateurs.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nom de domaine de l’objet Active Directory dont le principal est une version mise en cache. Il peut s’agir de valeurs NULL pour les types qui ne sont pas des objets Active Directory (par exemple, utilisateurs système).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nom d’utilisateur principal (UPN) de l’utilisateur. Utilisé uniquement par les types d’utilisateurs normaux.  <br/> |
|prinDisabled  <br/> |smallint, pas null  <br/> | 0: le principal est actif. <br/>  1: le principal est désactivé car les fonctionnalités SIP de l’utilisateur sont désactivées. <br/>  2: le principal est supprimé, car l’objet publicitaire associé a été supprimé. <br/> |
|prinTypeID  <br/> |smallint, pas null  <br/> |Type principal (issu de la table tblPrincipalType)  <br/> |
|prinPoolID  <br/> |Ent  <br/> |Attribution du pool de clients Skype entreprise pour le principal.  <br/> |
|prinPolicyID  <br/> |Ent  <br/> |Valeur de la stratégie de serveur de chat permanent pour l’utilisateur, si la stratégie de type balise est présente.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID principal du créateur.  <br/> |
|prinAddedOn  <br/> |bigint, pas null  <br/> |Horodatage de l’heure de création.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID de l’entité de confiance qui a mis à jour pour la dernière fois.  <br/> |
|prinUpdatedOn  <br/> |bigint, pas null  <br/> |Horodatage de la dernière mise à jour.  <br/> |
|prinVerifiedOn  <br/> |DATEHEURE, pas null  <br/> |Date et heure de la dernière actualisation de la synchronisation Active Directory de l’utilisateur principal.  <br/> |
   
**Permettent**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinTypeID  <br/> |Clé étrangère avec recherche dans la table tblPrincipalType. ptypeID.  <br/> |
   

