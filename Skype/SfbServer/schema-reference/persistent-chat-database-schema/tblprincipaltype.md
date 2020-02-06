---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal.
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812932"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, pas null  <br/> |ID de type principal.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), pas null  <br/> |Description du type.  <br/> |
|ptypeIsSystemUser  <br/> |bit, pas null  <br/> |True si le type correspond aux éléments principaux utilisés à des fins internes.  <br/> |
|ptypeIsUser  <br/> |bit, pas null  <br/> |True si le type est un type d’utilisateur.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|ptypeID  <br/> |Clé primaire.  <br/> |
   
**Valeurs principales**

|**ID**|**Rôle**|**Description**|**User**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Indifférente  <br/> |Principal générique sans type connu. Non utilisé dans la table tblPrincipal.  <br/> ||
|deuxième  <br/> |AnyUser  <br/> |Principal générique de type d’utilisateur. Non utilisé dans la table tblPrincipal.  <br/> |Oui  <br/> |
|3  <br/> |AnyGroup  <br/> |Principal générique avec la sémantique de groupe. Non utilisé dans la table tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Principal utilisé par le serveur de chat permanent.  <br/> ||
|5  <br/> |Utilisateur  <br/> |Utilisateur ordinaire.  <br/> |Oui  <br/> |
|version8  <br/> |CD  <br/> |Contrôleur de domaine Active Directory Domain Services.  <br/> ||
|09  <br/> |Groupe  <br/> |Groupe de sécurité Active Directory.  <br/> ||
|0,10  <br/> |Folder  <br/> |Conteneur Active Directory ou unité d’organisation.  <br/> ||
   
## <a name="see-also"></a>Voir aussi

[tblPrincipal](tblprincipal.md)
