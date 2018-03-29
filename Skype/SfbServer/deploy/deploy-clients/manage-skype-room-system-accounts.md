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
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="7c546-103">Gestion des comptes Skype Room System</span><span class="sxs-lookup"><span data-stu-id="7c546-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="7c546-104">Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7c546-104">Read this topic to learn how to manage Skype Room System accounts.</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="7c546-105">Déplacer le compte système local de Skype entre pools</span><span class="sxs-lookup"><span data-stu-id="7c546-105">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="7c546-106">Si vous devez déplacer le compte système local de Skype à partir d’un seul Skype pour un pool de serveurs d’entreprise à un autre (par exemple, lors de la mise à niveau), utilisez la commande suivante pour déplacer le pool de compte système local de Skype :</span><span class="sxs-lookup"><span data-stu-id="7c546-106">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="7c546-107">Désactiver le compte système local de Skype pour Skype pour les services</span><span class="sxs-lookup"><span data-stu-id="7c546-107">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="7c546-108">Si vous devez désactiver un système de salle Skype compte existant à partir de Skype pour les services sur un Skype pour un pool de serveurs d’entreprise, utilisez la commande suivante pour désactiver le compte :</span><span class="sxs-lookup"><span data-stu-id="7c546-108">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="7c546-109">Facultatif : Créez un groupe d’administrateurs système de salle Skype dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="7c546-109">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="7c546-110">Chaque client Skype espace système qui rejoint le domaine pouvant être entièrement géré par un utilisateur de domaine disposant de droits d’administrateur local sur la solution matérielle-logicielle Skype espace système PC.</span><span class="sxs-lookup"><span data-stu-id="7c546-110">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="7c546-111">Par conséquent, vous pouvez créer le groupe Administrateurs dédié dans Active Directory et abandonner cette droits administratifs du groupe lors du nouvel ordinateur de système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="7c546-111">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

