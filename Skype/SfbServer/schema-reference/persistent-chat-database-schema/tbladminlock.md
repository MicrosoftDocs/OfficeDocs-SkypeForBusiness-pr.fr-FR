---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
ms.openlocfilehash: ad3b2543e2715462b953c611c8b5f24ea7885a6cb910931aa5b832b8196856eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351943"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, not null  <br/> |Date et heure d’expiration du verrou. Le propriétaire peut étendre cette valeur de manière périodique.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID du serveur qui détient le verrou.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID du principal qui détient le verrou.  <br/> |
   

