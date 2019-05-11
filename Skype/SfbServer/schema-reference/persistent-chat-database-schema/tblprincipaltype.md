---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contient les types principaux pour classer les nouveautés dans la table tblPrincipal.
ms.openlocfilehash: 804997c0cb25dff6566d21a26626550982d0075f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924457"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contient les types principaux pour classer les nouveautés dans la table tblPrincipal.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, non null  <br/> |ID de type principal.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), non null  <br/> |Description du type.  <br/> |
|ptypeIsSystemUser  <br/> |bit, non null  <br/> |True si le type correspond aux principaux qui sont utilisés à des fins internes.  <br/> |
|ptypeIsUser  <br/> |bit, non null  <br/> |True si le type est un type d’utilisateur.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|ptypeID  <br/> |Clé primaire.  <br/> |
   
**Valeurs principales**

|**ID**|**Rôle**|**Description**|**User**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Indifférente  <br/> |Entité de sécurité générique avec aucun type connu. Pas utilisée dans la table tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Entité de sécurité générique de type utilisateur. Pas utilisée dans la table tblPrincipal.  <br/> |Oui  <br/> |
|3  <br/> |AnyGroup  <br/> |Entité de sécurité générique avec la sémantique de groupe. Pas utilisée dans la table tblPrincipal.  <br/> ||
|4  <br/> |Système  <br/> |Principal utilisé en interne par le serveur de conversation permanente.  <br/> ||
|5  <br/> |Utilisateur  <br/> |Utilisateur régulier.  <br/> |Oui  <br/> |
|8  <br/> |CONTRÔLEUR DE DOMAINE  <br/> |Contrôleur de domaine Active Directory Domain Services.  <br/> ||
|9  <br/> |Groupe  <br/> |Groupe de sécurité Active Directory.  <br/> ||
|10  <br/> |Dossier  <br/> |Unité d’organisation ou conteneur Active Directory.  <br/> ||
   
## <a name="see-also"></a>Voir aussi

[tblPrincipal](tblprincipal.md)
