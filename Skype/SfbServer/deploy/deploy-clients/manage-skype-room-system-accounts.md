---
title: Gérer les comptes de système de salle Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Lisez cette rubrique pour découvrir comment gérer les comptes Skype Room System.
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805554"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="4780d-103">Gérer les comptes de système de salle Skype</span><span class="sxs-lookup"><span data-stu-id="4780d-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="4780d-104">Lisez cette rubrique pour découvrir comment gérer les comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="4780d-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="4780d-105">Salles Microsoft Teams est un produit différent avec différentes dépendances et procédures de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4780d-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="4780d-106">Pour plus d’informations sur les salles Microsoft Teams, voir la vue d’ensemble de la gestion des [salles](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4780d-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="4780d-107">Déplacer le compte Skype Room System entre les pools</span><span class="sxs-lookup"><span data-stu-id="4780d-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="4780d-108">Si vous devez déplacer le compte Skype Room System d’un pool Skype Entreprise Server vers un autre (par exemple, pendant les mises à niveau), utilisez la commande suivante pour déplacer le pool de comptes Skype Room System :</span><span class="sxs-lookup"><span data-stu-id="4780d-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="4780d-109">Désactiver le compte Skype Room System pour les services Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4780d-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="4780d-110">Si vous devez désactiver un compte Skype Room System existant à partir des services Skype Entreprise sur un pool Skype Entreprise Server, utilisez la commande suivante pour désactiver le compte :</span><span class="sxs-lookup"><span data-stu-id="4780d-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="4780d-111">Facultatif : créer un groupe d’administrateurs Skype Room System dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="4780d-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="4780d-112">Chaque client Skype Room System qui joint le domaine peut être entièrement géré par un utilisateur de domaine avec des droits d’administrateur local sur le PC d’appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="4780d-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="4780d-113">Par conséquent, vous pouvez créer un groupe d’administrateurs dédié dans Active Directory et accorder à ce groupe des droits d’administration lors de la mise en place de la nouvelle machine Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="4780d-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

