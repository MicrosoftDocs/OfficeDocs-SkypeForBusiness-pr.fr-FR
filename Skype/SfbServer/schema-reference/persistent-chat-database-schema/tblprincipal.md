---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contient tous les principaux, y compris les utilisateurs, les dossiers et les groupes.
ms.openlocfilehash: 50d20aee156a4a919effac26ff29c371ec2cf886c12300ecd07268576730ae49
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338022"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contient tous les principaux, y compris les utilisateurs, les dossiers et les groupes.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|prinID  <br/> |int, non null  <br/> |ID de principal.  <br/> |
|prinGuid  <br/> |GUID, non null  <br/> |ID de principal. Il est largement utilisé comme clé primaire de remplacement, car sa signification croise l’espace Services de domaine Active Directory. (Le GUID d’un principal mis en cache est égal au GUID d’objet Active Directory correspondant.)  <br/> |
|prinUri  <br/> |nvarchar (256), non null  <br/> |ID de principal. Le modèle SIP est utilisé pour les utilisateurs et ma-grp est utilisé pour presque tout le reste.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nom commun. Utilisé uniquement par les types d’utilisateurs.  <br/> |
|prinDisplayName  <br/> |Nvarchar(256)  <br/> |Nom complet. Utilisé uniquement par les types d’utilisateurs.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nom de société. Utilisé uniquement par les types d’utilisateurs.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Adresse de messagerie. Utilisée uniquement par les types d’utilisateurs.  <br/> |
|prinADPath  <br/> |nvarchar(384)  <br/> |Nom de domaine de l’objet Active Directory dont le principal est une version mise en cache. Peut être Null pour les types qui ne sont pas des objets Active Directory (tels que les utilisateurs système).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nom d’utilisateur principal (UPN) de l’utilisateur. Utilisé uniquement par les types d’utilisateurs réguliers.  <br/> |
|prinDisabled  <br/> |smallint, non null  <br/> | 0 : le principal est actif. <br/>  1 : le principal est désactivé car les fonctionnalités SIP de l’utilisateur sont désactivées. <br/>  2 : le principal est supprimé car l’objet AD associé a été supprimé. <br/> |
|prinTypeID  <br/> |smallint, non null  <br/> |Type de principal (tiré de la table tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Skype Entreprise’affectation du pool client pour le principal.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Valeur de stratégie de serveur de conversation permanente pour l’utilisateur, si la stratégie de type de balise est présente.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID de principal du créateur.  <br/> |
|prinAddedOn  <br/> |bigint, non null  <br/> |Horodatage de la création.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID du principal ayant effectué la dernière mise à jour.  <br/> |
|prinUpdatedOn  <br/> |bigint, non null  <br/> |Horodatage de la dernière mise à jour.  <br/> |
|prinVerifiedOn  <br/> |datetime, non null  <br/> |Date et heure de la dernière actualisation de synchronisation Active Directory pour le principal.  <br/> |
   
**Keys**

|**Colonne**|**Description**|
|:-----|:-----|
|prinID  <br/> |Clé primaire.  <br/> |
|prinTypeID  <br/> |Clé étrangère avec recherche dans la table tblPrincipalType.ptypeID.  <br/> |
   

