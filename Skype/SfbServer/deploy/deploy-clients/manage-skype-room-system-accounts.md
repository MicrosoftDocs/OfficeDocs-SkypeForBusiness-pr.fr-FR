---
title: Gestion des comptes Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.
ms.openlocfilehash: ab82780617ba8fc6304bb97f56a319c7898bff44
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774895"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="22c88-103">Gestion des comptes Skype Room System</span><span class="sxs-lookup"><span data-stu-id="22c88-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="22c88-104">Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="22c88-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="22c88-105">Microsoft teams Room est un produit différent présentant différentes dépendances et procédures de déploiement.</span><span class="sxs-lookup"><span data-stu-id="22c88-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="22c88-106">Pour plus d’informations sur les salles de Microsoft Teams, voir la [vue d’ensemble](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)de la gestion de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22c88-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="22c88-107">Déplacer le compte système de salle Skype entre les regroupements</span><span class="sxs-lookup"><span data-stu-id="22c88-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="22c88-108">Si vous avez besoin de déplacer le compte du système de salle Skype d’un pool de serveurs Skype entreprise vers un autre (par exemple, lors des mises à niveau), utilisez la commande suivante pour déplacer la liste de comptes système de salle Skype :</span><span class="sxs-lookup"><span data-stu-id="22c88-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="22c88-109">Désactiver le compte système de salle Skype pour les services Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="22c88-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="22c88-110">Si vous avez besoin de désactiver un compte local de salle Skype pour les services Skype entreprise sur un pool de serveurs Skype entreprise, utilisez la commande suivante pour désactiver le compte :</span><span class="sxs-lookup"><span data-stu-id="22c88-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="22c88-111">Facultatif : créer un groupe d’administrateurs de systèmes de salle Skype dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="22c88-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="22c88-112">Chaque client de système de salle Skype qui rejoint le domaine peut être entièrement géré par un utilisateur du domaine avec des droits d’administrateur local sur le PC du système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="22c88-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="22c88-113">Par conséquent, vous pouvez créer un groupe d’administrateurs dédié dans Active Directory et octroyer ces droits d’administration au groupe lors de la mise en place de la nouvelle machine sur le système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="22c88-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

