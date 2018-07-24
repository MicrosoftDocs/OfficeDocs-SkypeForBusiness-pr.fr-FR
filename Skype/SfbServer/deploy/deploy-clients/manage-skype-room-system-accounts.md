---
title: Gestion des comptes Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
description: Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.
ms.openlocfilehash: 502e9c3e7036abef832bf051513b11dff4c3becc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20999631"
---
# <a name="manage-skype-room-system-accounts"></a>Gestion des comptes Skype Room System
 
Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System. 

> [!NOTE]
> Systèmes de salle Skype v2 est un produit différents avec des dépendances différents et des procédures de déploiement. Pour plus d’informations sur les systèmes de salle Skype v2, voir systèmes de salle Skype v2 [Présentation de la gestion](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Déplacer le compte de système de salle Skype entre pools

Si vous devez déplacer le compte système local de Skype à partir d’un seul Skype pour le pool de serveurs d’entreprise à un autre (par exemple, pendant les mises à jour), utilisez la commande suivante pour déplacer le pool de compte Skype salle système : 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Désactiver le compte de système de salle Skype pour Skype pour les services

Si vous devez désactiver un système de salle Skype compte existant à partir de Skype pour les services sur un Skype pour le pool de serveurs d’entreprise, utilisez la commande suivante pour désactiver le compte : 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facultatif : Créer un groupe d’administrateurs système de salle Skype dans Active Directory

Chaque client Skype salle système qui rejoint le domaine pouvant être entièrement géré par un utilisateur de domaine disposant de droits d’administrateur local sur l’appliance Skype salle système PC. Par conséquent, vous pouvez créer le groupe des administrateurs dédié dans Active Directory et abandonner cette droits d’administration du groupe de définition du nouvel ordinateur Skype salle système.
  

