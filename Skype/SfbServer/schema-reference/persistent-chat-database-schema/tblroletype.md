---
title: tblRoleType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de choix statique avec les types de rôles et leurs jeux d’autorisations.
ms.openlocfilehash: 6b5e545306c402fbfb89094a19799fe3ff6d2e34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212410"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType est une table de choix statique avec les types de rôles et leurs jeux d’autorisations.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, non null  <br/> |ID de type de rôle.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), non null  <br/> | Description du type de rôle. Il existe quatre rôles disponibles : <br/>  : Membres salle de conversation <br/>  : Gestionnaire salle de conversation <br/>  Membre sonore : Le présentateur pour une salle de conversation de type auditorium <br/>  Créateur : Peut créer des salles de conversation <br/> |
|rtypeAllowedPermSet  <br/> |bigint, non null  <br/> | Jeu d’autorisations pour le rôle. Les fichiers binaires utilisés sont les suivants : <br/>  2 : true si le rôle peut gérer des nœuds. <br/>  4 : true si le rôle peut créer des nœuds enfants. <br/>  7 : true si le rôle peut rejoindre une salle de conversation (ou les salles de conversation enfants d’une catégorie). <br/>  8 : true si le rôle peut converser dans une salle de conversation (ou dans les salles de conversation enfants d’une catégorie). <br/>  10 : true si le rôle peut lire l’historique des conversations même lorsque ne pas lié à une salle de conversation. <br/>  11 : true si le rôle peut voir la salle de conversation. (Il est affiné par facteurs, tels que l’étendue et la visibilité.) <br/>  12 : true si le rôle peut converser dans une salle de conversation de type auditorium. <br/>  13 : true si le rôle peut contourner les règles de visibilité lors de l’affichage des nœuds. <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|rtypeID  <br/> |Clé primaire.  <br/> |
   

