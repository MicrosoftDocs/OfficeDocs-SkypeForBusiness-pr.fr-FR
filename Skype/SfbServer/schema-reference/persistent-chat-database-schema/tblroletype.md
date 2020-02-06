---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de recherche statique avec les types de rôles et leurs jeux d’autorisations associés.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812902"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType est une table de recherche statique avec les types de rôles et leurs jeux d’autorisations associés.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|rtypeID  <br/> |ent, non null  <br/> |ID du type de rôle.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), pas null  <br/> | Description du type de rôle. Il existe quatre rôles disponibles : <br/>  Membre : membres de salle de conversation <br/>  Manager : gestionnaire de salle de conversation <br/>  Voix : présentateur pour une salle de conversation Auditorium <br/>  Créateur : peut créer des salles de conversation <br/> |
|rtypeAllowedPermSet  <br/> |bigint, pas null  <br/> | Autorisation définie pour le rôle. Les bits utilisés sont les suivants : <br/>  2 : true si le rôle peut gérer des nœuds. <br/>  4 : true si le rôle peut créer des nœuds enfants. <br/>  7 : true si le rôle peut rejoindre une salle de conversation (ou des salles de conversation enfant d’une catégorie). <br/>  8 : true si le rôle peut discuter dans une salle de conversation (ou dans des salles de conversation enfant d’une catégorie). <br/>  10 : true si le rôle peut lire l’historique des conversations même en l’absence de participation à une salle de conversation. <br/>  11 : true si le rôle peut voir la salle de conversation. (Cette valeur est améliorée par des facteurs tels que Scope et Visibility.) <br/>  12 : true si le rôle peut discuter dans une salle de conversation Auditorium. <br/>  13 : true si le rôle peut ignorer les règles de visibilité lors de la consultation des nœuds. <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|rtypeID  <br/> |Clé primaire.  <br/> |
   

