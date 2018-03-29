---
title: tblPrincipalType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contient les principaux types pour classer les nouveautés dans la table tblPrincipal.
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contient les principaux types pour classer les nouveautés dans la table tblPrincipal.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, non null  <br/> |Code de type d’entité de sécurité.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), non null  <br/> |Description du type.  <br/> |
|ptypeIsSystemUser  <br/> |bits, non null  <br/> |True si le type correspond aux entités qui sont utilisées à des fins internes.  <br/> |
|ptypeIsUser  <br/> |bits, non null  <br/> |True si le type est un type d’utilisateur.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|ptypeID  <br/> |Clé primaire.  <br/> |
   
**Valeurs de l’entité de sécurité**

|**ID**|**Rôle**|**Description**|**Utilisateur**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Indifférente  <br/> |Entité de sécurité générique avec aucun type connu. Non utilisé dans la table de tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Entité de sécurité générique du type d’utilisateur. Non utilisé dans la table de tblPrincipal.  <br/> |Oui  <br/> |
|3  <br/> |AnyGroup  <br/> |Entité de sécurité générique avec la sémantique de groupe. Non utilisé dans la table de tblPrincipal.  <br/> ||
|4  <br/> |Utilisateur système  <br/> |Entité utilisée en interne par le serveur de conversation persistant.  <br/> ||
|5  <br/> |Utilisateur  <br/> |Utilisateur normal.  <br/> |Oui  <br/> |
|8  <br/> |CONTRÔLEUR DE DOMAINE  <br/> |Contrôleur de domaine Active Directory des Services de domaine.  <br/> ||
|9  <br/> |Groupe  <br/> |Groupe de sécurité Active Directory.  <br/> ||
|10  <br/> |Dossier  <br/> |Conteneur Active Directory ou l’unité d’organisation.  <br/> ||
   
## <a name="see-also"></a>Voir aussi

#### 

[tblPrincipal](tblprincipal.md)

