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
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295243"
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
|2  <br/> |AnyUser  <br/> |Principal générique de type d’utilisateur. Non utilisé dans la table tblPrincipal.  <br/> |Oui  <br/> |
|3  <br/> |AnyGroup  <br/> |Principal générique avec la sémantique de groupe. Non utilisé dans la table tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Principal utilisé par le serveur de chat permanent.  <br/> ||
|5  <br/> |Utilisateur  <br/> |Utilisateur ordinaire.  <br/> |Oui  <br/> |
|version8  <br/> |CD  <br/> |Contrôleur de domaine Active Directory Domain Services.  <br/> ||
|09  <br/> |Groupe  <br/> |Groupe de sécurité Active Directory.  <br/> ||
|0,10  <br/> |Folder  <br/> |Conteneur Active Directory ou unité d’organisation.  <br/> ||
   
## <a name="see-also"></a>Voir aussi

[tblPrincipal](tblprincipal.md)
