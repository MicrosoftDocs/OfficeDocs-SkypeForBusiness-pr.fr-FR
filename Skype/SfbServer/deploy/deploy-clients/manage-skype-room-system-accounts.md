---
title: Gérer les comptes de système de salle Skype
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lisez cette rubrique pour découvrir comment gérer Skype comptes Room System.
ms.openlocfilehash: 2ae91a977a837e2b1b54db8d127551b5f53bb1a8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864451"
---
# <a name="manage-skype-room-system-accounts"></a>Gérer les comptes de système de salle Skype
 
Lisez cette rubrique pour découvrir comment gérer Skype comptes Room System. 

> [!NOTE]
> Salles Microsoft Teams est un produit différent avec différentes dépendances et procédures de déploiement. Pour plus d’informations Salles Microsoft Teams, voir la vue d’ensemble Salles Microsoft Teams [gestion des données.](/microsoftteams/rooms/rooms-manage)
  
## <a name="move-the-skype-room-system-account-between-pools"></a>Déplacer le compte Skype Room System entre les pools

Si vous devez déplacer le compte Skype Room System d’un pool Skype Entreprise Server vers un autre (par exemple, pendant les mises à niveau), utilisez la commande suivante pour déplacer le pool de comptes Skype Room System : 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>Désactiver le compte Skype Room System pour les services Skype Entreprise client

Si vous devez désactiver un compte Skype Room System existant des services Skype Entreprise sur un pool Skype Entreprise Server, utilisez la commande suivante pour désactiver le compte : 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>Facultatif : créer un groupe d Skype de salle de réunion dans Active Directory

Chaque client Skype Room System qui joint le domaine peut être entièrement géré par un utilisateur de domaine ayant des droits d’administrateur local sur le PC Skype Room System Appliance. Par conséquent, vous pouvez créer un groupe d’administrateurs dédié dans Active Directory et accorder à ce groupe des droits d’administration lors de la mise en place de la nouvelle machine Skype Room System.
