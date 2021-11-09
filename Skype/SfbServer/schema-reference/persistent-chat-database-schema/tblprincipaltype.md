---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: La table tblPrincipalType contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal.
ms.openlocfilehash: cf55ba04afe3688d3ecfd397dc4ffcbe50da2c19
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844067"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
La table tblPrincipalType contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, non null  <br/> |ID de type Principal.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), non null  <br/> |Description du type.  <br/> |
|ptypeIsSystemUser  <br/> |bit, non null  <br/> |Vrai si le type correspond aux principaux qui sont utilisés pour des fonctions internes.  <br/> |
|ptypeIsUser  <br/> |bit, non null  <br/> |Vrai si le type est un type utilisateur.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|ptypeID  <br/> |Clé primaire.  <br/> |
   
**Valeurs principales**

|**ID**|**Role**|**Description**|**Utilisateur**|
|:-----|:-----|:-----|:-----|
|1  <br/> |N’importe lequel  <br/> |Principal générique sans type connu. Inutilisé dans la table tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Principal générique de type utilisateur. Inutilisé dans table tblPrincipal.  <br/> |Oui  <br/> |
|3  <br/> |AnyGroup  <br/> |Principal générique avec sémantique de groupe. Inutilisé dans table tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Principal utilisé en interne par le serveur de conversation permanente.  <br/> ||
|5  <br/> |Utilisateur  <br/> |Utilisateur régulier.  <br/> |Oui  <br/> |
|8   <br/> |DC  <br/> |Contrôleur de domaine des services de domaine Active Directory.  <br/> ||
|9   <br/> |Group  <br/> |Groupe de sécurité Active Directory.  <br/> ||
|10  <br/> |Folder  <br/> |Conteneur ou unité d’organisation Active Directory.  <br/> ||
   
## <a name="see-also"></a>Voir aussi

[tblPrincipal](tblprincipal.md)
