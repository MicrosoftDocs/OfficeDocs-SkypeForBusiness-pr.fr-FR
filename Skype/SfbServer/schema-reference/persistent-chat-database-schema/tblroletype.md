---
title: tblRoleType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de choix statique contenant des types de rôles et leurs jeux d’autorisations.
ms.openlocfilehash: 2b03473b6f89e0dd2f572e2462b607bc72a2a2eb5f83aa18d2d779f9f66ee220
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318677"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType est une table de choix statique contenant des types de rôles et leurs jeux d’autorisations.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, non null  <br/> |ID de type de rôle.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), non null  <br/> | Description de type de rôle. Les quatre rôles disponibles sont : <br/>  Membre : membre de la salle de conversation <br/>  Responsable : responsable de la salle de conversation <br/>  Membre sonore : présentateur de la salle de conversation de type auditorium <br/>  Créateur : peut créer des salles de conversation <br/> |
|rtypeAllowedPermSet  <br/> |bigint, non null  <br/> | Définition de l’autorisation du rôle. Les bits utilisés sont : <br/>  2 : True si le rôle peut gérer des nœuds. <br/>  4 : True si le rôle peut créer des nœuds enfants. <br/>  7 : True si le rôle peut rejoindre une salle de conversation (ou les salles de conversation enfants d’une catégorie). <br/>  8 : True si le rôle peut converser dans une salle de conversation (ou les salles de conversation enfants d’une catégorie). <br/>  10 : True si le rôle peut lire l’historique d’une conversation même s’il n’a pas rejoint une salle de conversation. <br/>  11 : True si le rôle peut voir la salle de conversation. (Les facteurs tels que l’étendue et la visibilité permettent d’affiner davantage). <br/>  12 : True si le rôle peut converser dans la salle de conversation de type auditorium. <br/>  13 : True si le rôle peut contourner les règles de visibilité lors de la visualisation des nœuds. <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|rtypeID  <br/> |Clé primaire.  <br/> |
   

