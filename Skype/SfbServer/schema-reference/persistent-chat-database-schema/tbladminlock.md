---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrouillage de l’administrateur requis pour exécuter certaines commandes administrateur.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814692"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contient le verrouillage de l’administrateur requis pour exécuter certaines commandes administrateur.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DATEHEURE, pas null  <br/> |Verrouillage de la date et de l’heure d’expiration. Le propriétaire peut prolonger cette valeur périodiquement.  <br/> |
|lockServerID  <br/> |ent, non null  <br/> |ID du serveur propriétaire du verrou.  <br/> |
|lockActorID  <br/> |ent, non null  <br/> |ID de l’entité propriétaire du verrou.  <br/> |
   

