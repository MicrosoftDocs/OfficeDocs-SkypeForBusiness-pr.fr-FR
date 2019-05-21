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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrouillage de l’administrateur requis pour exécuter certaines commandes administrateur.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295523"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contient le verrouillage de l’administrateur requis pour exécuter certaines commandes administrateur.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DATEHEURE, pas null  <br/> |Verrouillage de la date et de l’heure d’expiration. Le propriétaire peut prolonger cette valeur périodiquement.  <br/> |
|lockServerID  <br/> |ent, non null  <br/> |ID du serveur propriétaire du verrou.  <br/> |
|lockActorID  <br/> |ent, non null  <br/> |ID de l’entité propriétaire du verrou.  <br/> |
   

