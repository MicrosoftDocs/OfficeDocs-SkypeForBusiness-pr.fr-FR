---
title: Gestion des comptes Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.
ms.openlocfilehash: 2a45fc8507b9b09b777e6aa91c47fff2b3dfc3d2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234072"
---
# <a name="manage-skype-room-system-accounts"></a>Gestion des comptes Skype Room System
 
Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System. 

> [!NOTE]
> Microsoft teams Room est un produit différent présentant différentes dépendances et procédures de déploiement. Pour plus d’informations sur les salles de Microsoft Teams, voir la [vue d’ensemble](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de la gestion de Microsoft Teams.
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Déplacer le compte système de salle Skype entre les regroupements

Si vous avez besoin de déplacer le compte du système de salle Skype d’un pool de serveurs Skype entreprise vers un autre (par exemple, lors des mises à niveau), utilisez la commande suivante pour déplacer la liste de comptes système de salle Skype: 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Désactiver le compte système de salle Skype pour les services Skype entreprise

Si vous avez besoin de désactiver un compte local de salle Skype pour les services Skype entreprise sur un pool de serveurs Skype entreprise, utilisez la commande suivante pour désactiver le compte: 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facultatif: créer un groupe d’administrateurs de systèmes de salle Skype dans Active Directory

Chaque client de système de salle Skype qui rejoint le domaine peut être entièrement géré par un utilisateur du domaine avec des droits d’administrateur local sur le PC du système de salle Skype. Par conséquent, vous pouvez créer un groupe d’administrateurs dédié dans Active Directory et octroyer ces droits d’administration au groupe lors de la mise en place de la nouvelle machine sur le système de salle Skype.
  

