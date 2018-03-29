---
title: Gestion des comptes Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.
ms.openlocfilehash: c47765b617e0856d1db25c7ed4902fe0af9924f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-system-accounts"></a>Gestion des comptes Skype Room System
 
Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Déplacer le compte système local de Skype entre pools

Si vous devez déplacer le compte système local de Skype à partir d’un seul Skype pour un pool de serveurs d’entreprise à un autre (par exemple, lors de la mise à niveau), utilisez la commande suivante pour déplacer le pool de compte système local de Skype : 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Désactiver le compte système local de Skype pour Skype pour les services

Si vous devez désactiver un système de salle Skype compte existant à partir de Skype pour les services sur un Skype pour un pool de serveurs d’entreprise, utilisez la commande suivante pour désactiver le compte : 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facultatif : Créez un groupe d’administrateurs système de salle Skype dans Active Directory

Chaque client Skype espace système qui rejoint le domaine pouvant être entièrement géré par un utilisateur de domaine disposant de droits d’administrateur local sur la solution matérielle-logicielle Skype espace système PC. Par conséquent, vous pouvez créer le groupe Administrateurs dédié dans Active Directory et abandonner cette droits administratifs du groupe lors du nouvel ordinateur de système de salle de Skype.
  

