---
title: tblRoleType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de recherche statiques avec les types de rôles et de leurs jeux d’autorisations associés.
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType est une table de recherche statiques avec les types de rôles et de leurs jeux d’autorisations associés.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, non null  <br/> |ID de type de rôle.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), non null  <br/> | Description du type de rôle. Il existe quatre rôles disponibles : <br/>  : Membres salle de conversation <br/>  : Gestionnaire salle de conversation <br/>  Voisé : Le présentateur pour une salle de conversation auditorium <br/>  Créateur : Peut créer des salles de conversation <br/> |
|rtypeAllowedPermSet  <br/> |bigint, non null  <br/> | Jeu d’autorisations pour le rôle. Les bits utilisés sont les suivants : <br/>  2 : true si le rôle peut gérer des nœuds. <br/>  4 : true si le rôle peut créer des nœuds enfants. <br/>  7 : true si le rôle peut rejoindre une salle de conversation (ou salles de conversation enfants d’une catégorie). <br/>  8 : true si le rôle peut discuter dans une salle de conversation (ou dans les salles de conversation enfants d’une catégorie). <br/>  10 : true si le rôle peut lire l’historique de conversation même si ne pas connecté à une salle de conversation. <br/>  11 : true si le rôle peut voir la salle de conversation. (Il est affiné par des facteurs tels que la portée et visibilité.) <br/>  12 : true si le rôle peut discuter dans une salle de conversation auditorium. <br/>  13 : true si le rôle peut ignorer les règles de visibilité lors de l’affichage de nœuds. <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|rtypeID  <br/> |Clé primaire.  <br/> |
   

